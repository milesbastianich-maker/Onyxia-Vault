# Signal Intelligence Layer — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build two n8n workflows (`07 — Signal Intelligence` and `07b — Active Account Watchdog`) that ingest free breach/exploit signals, score prospect fit, auto-draft outreach for Tier 1 hits, and surface the rest in the morning brief.

**Architecture:** Cloud n8n at milesonyxia.app.n8n.cloud. Each workflow chains HTTP Request nodes (feed fetching) → Code nodes (parsing, exclusion, scoring, drafting) → HTTP Request to Slack Notifier webhook (output). HubSpot REST API handles CRM lookups. ZoomInfo authenticates via existing pattern from workflow 01. No local filesystem writes — Slack output is the handoff point; vault writes happen during operator shifts.

**Tech Stack:** n8n cloud, HubSpot CRM API, ZoomInfo API, Anthropic Claude API (sonnet-4-6), NewsAPI, SEC EDGAR EFTS, HHS OCR, CISA KEV JSON feed, Slack (via existing `00 — Slack Notifier` webhook).

---

## Context for the implementer

- n8n instance: `https://milesonyxia.app.n8n.cloud`
- Existing active workflows: 01 (Discovery), 02 (Enrichment), 03 (Sending Engine), 04 (Reply Monitor), 00 (Slack Notifier id: `gAKhtQ3Lp3i5vSVQ`), 99 (Error Handler)
- Slack channel for all output: `#miles-ai-ops` (ID: `C0AUB4DATP0`)
- HubSpot owner ID: `86806986`
- ZoomInfo auth pattern: see workflow 01 nodes `ZoomInfo Authenticate` → `ZoomInfo Search Tier 1`
- ICP fit rubric: `~/ObsidianVault/50_Intel/icp.md` (hardcode scoring logic from this file into Code nodes)
- Exclusion list: `~/.claude/projects/-Users-milesbastianich/memory/reference_onyxia_exclusions.md` (hardcode as array in Code node)
- Voice rules for drafts: short sentences, no em dashes, peer tone, no jargon. See `~/ObsidianVault/00_Index/CLAUDE.md`.
- NewsAPI key: stored in n8n as credential named `NewsAPI` (Header Auth, header name `X-Api-Key`)
- Claude API key: stored in n8n as credential named `Anthropic` (Header Auth, header name `x-api-key`)

---

## Pre-flight: Read before building

- [ ] Read `~/ObsidianVault/50_Intel/icp.md` — extract the fit scoring rubric (1–5 criteria). You will hardcode this into the Fit Score code node.
- [ ] Read `~/.claude/projects/-Users-milesbastianich/memory/reference_onyxia_exclusions.md` — extract the exclusion company list. You will hardcode as a string array in the Exclusion Check code node.
- [ ] Confirm the Slack Notifier webhook URL by fetching workflow `gAKhtQ3Lp3i5vSVQ` in full mode and reading the webhook path from the Webhook node parameters.

---

## Task 1: Store credentials in n8n

**What:** Create two Header Auth credentials in n8n — one for NewsAPI, one for Anthropic. These are referenced by name in HTTP Request nodes.

- [ ] **Step 1: Create NewsAPI credential**

Use `mcp__n8n-mcp__n8n_manage_credentials` with action `create`:
```json
{
  "action": "create",
  "credentialType": "httpHeaderAuth",
  "name": "NewsAPI",
  "data": {
    "name": "X-Api-Key",
    "value": "d415768396b64fdaa1d86e9f95da4cc2"
  }
}
```

- [ ] **Step 2: Create Anthropic credential**

```json
{
  "action": "create",
  "credentialType": "httpHeaderAuth",
  "name": "Anthropic",
  "data": {
    "name": "x-api-key",
    "value": "{{your Anthropic API key}}"
  }
}
```

Ask Miles for the Anthropic API key before this step if not already stored.

- [ ] **Step 3: Verify both credentials appear in n8n**

Use `mcp__n8n-mcp__n8n_manage_credentials` with action `list`. Confirm `NewsAPI` and `Anthropic` are present.

---

## Task 2: Build `07 — Signal Intelligence (Daily)` — Feed Fetchers

**What:** Create the workflow skeleton with a schedule trigger and four HTTP Request nodes that fetch raw data from each feed. Test each feed independently before wiring the rest of the pipeline.

**Node map:**
```
Schedule Trigger (06:45 ET)
  → Fetch SEC 8-K
  → Fetch HHS OCR
  → Fetch CISA KEV
  → Fetch NewsAPI (4 queries)
  → Merge All Signals
```

- [ ] **Step 1: Generate workflow skeleton**

Call `mcp__n8n-mcp__n8n_generate_workflow` with this prompt:

```
Create an n8n workflow named "07 — Signal Intelligence (Daily)" with:
1. A Schedule Trigger that fires at 06:45 ET every weekday (Monday–Friday)
2. Four HTTP Request nodes running in parallel after the trigger:
   - "Fetch SEC 8-K": GET https://efts.sec.gov/LATEST/search-index?q=%22Item+1.05%22+%22cybersecurity+incident%22&forms=8-K&dateRange=custom&startdt={{$now.minus(1,'day').toFormat('yyyy-MM-dd')}}&enddt={{$now.toFormat('yyyy-MM-dd')}} with header User-Agent: "Onyxia-Cyber-Sales noreply@onyxia.io"
   - "Fetch HHS OCR": GET https://ocrportal.hhs.gov/ocr/breach/breach_report.jsf with query params form.startdate={{$now.minus(7,'day').toFormat('MM/dd/yyyy')}}, form.enddate={{$now.toFormat('MM/dd/yyyy')}}, actionType=dtSearch
   - "Fetch CISA KEV": GET https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
   - "Fetch NewsAPI": GET https://newsapi.org/v2/everything with query params q="data breach" AND "healthcare", from={{$now.minus(1,'day').toFormat('yyyy-MM-dd')}}, sortBy=publishedAt, pageSize=10 — use credential "NewsAPI"
3. A Merge node that collects output from all four fetchers
Do not add any nodes after the Merge node yet.
```

- [ ] **Step 2: Create the workflow**

Use `mcp__n8n-mcp__n8n_create_workflow` with the generated JSON. Keep inactive.

- [ ] **Step 3: Test SEC 8-K fetch alone**

In n8n UI, manually execute just the "Fetch SEC 8-K" node. Confirm response contains a `hits` object with a `hits` array. If 403, add header `Accept: application/json` and retry.

- [ ] **Step 4: Test CISA KEV fetch alone**

Manually execute "Fetch CISA KEV". Confirm response contains `vulnerabilities` array with fields: `cveID`, `vendorProject`, `product`, `dateAdded`, `dueDate`.

- [ ] **Step 5: Test NewsAPI fetch alone**

Manually execute "Fetch NewsAPI". Confirm response contains `articles` array. If 401, verify `NewsAPI` credential header name is `X-Api-Key` (case-sensitive).

- [ ] **Step 6: Note HHS OCR response format**

HHS OCR JSF may return HTML rather than JSON. If the response is HTML:
- Switch the node to `POST` method
- Add form body: `form.startdate={{$now.minus(7,'day').toFormat('MM/dd/yyyy')}}&form.enddate={{$now.toFormat('MM/dd/yyyy')}}&actionType=dtSearch`
- Set Content-Type: `application/x-www-form-urlencoded`
If still HTML, replace the node with a NewsAPI query instead: `"HIPAA breach" OR "HHS OCR" AND "individuals affected"` as a 5th NewsAPI query (still within 100/day limit).

---

## Task 3: Signal Normalization Code Node

**What:** After the Merge node, add a Code node that reads raw output from all four feeds and produces a single normalized array of signal objects. Every downstream node works with this standard shape.

**Normalized signal shape:**
```javascript
{
  company: "Acme Health Systems",   // string, company name
  feed: "SEC_8K",                   // SEC_8K | HHS_OCR | CISA_KEV | NEWSAPI
  signal: "cybersecurity_incident", // what happened
  date: "2026-04-21",               // ISO date string
  link: "https://...",              // source URL
  excerpt: "...",                   // one-sentence description
  cveID: null,                      // string or null (CISA only)
  affectedProduct: null,            // string or null (CISA only)
}
```

- [ ] **Step 1: Add normalization Code node after Merge**

Add a Code node named `Normalize Signals`. Paste this JavaScript:

```javascript
const signals = [];
const today = new Date().toISOString().split('T')[0];

for (const item of $input.all()) {
  const raw = item.json;

  // SEC EDGAR
  if (raw.hits?.hits) {
    for (const hit of raw.hits.hits) {
      const src = hit._source || {};
      if (!src.entity_name) continue;
      signals.push({
        company: src.entity_name,
        feed: 'SEC_8K',
        signal: 'cybersecurity_incident',
        date: src.file_date || today,
        link: `https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=${src.file_num || ''}&type=8-K`,
        excerpt: `${src.entity_name} filed 8-K Item 1.05 — material cybersecurity incident on ${src.file_date || today}.`,
        cveID: null,
        affectedProduct: null,
      });
    }
  }

  // CISA KEV
  if (raw.vulnerabilities) {
    for (const vuln of raw.vulnerabilities) {
      if (vuln.dateAdded !== today) continue;
      signals.push({
        company: '', // CISA signals match on tech stack, not company name yet
        feed: 'CISA_KEV',
        signal: 'active_exploitation',
        date: vuln.dateAdded,
        link: `https://www.cisa.gov/known-exploited-vulnerabilities-catalog`,
        excerpt: `CISA KEV: ${vuln.cveID} — ${vuln.vendorProject} ${vuln.product}. Required remediation by ${vuln.dueDate}.`,
        cveID: vuln.cveID,
        affectedProduct: `${vuln.vendorProject} ${vuln.product}`,
        dueDate: vuln.dueDate,
      });
    }
  }

  // NewsAPI
  if (raw.articles) {
    for (const article of raw.articles) {
      // Extract company name: take the first proper noun cluster from title
      // Simple heuristic: words before "says", "reports", "confirms", "discloses"
      const titleWords = (article.title || '').split(/\s+/);
      const stopIdx = titleWords.findIndex(w =>
        ['says','reports','confirms','discloses','suffers','hit','struck','affected','impacted','fined','settles'].includes(w.toLowerCase())
      );
      const companyGuess = stopIdx > 0 ? titleWords.slice(0, Math.min(stopIdx, 4)).join(' ') : '';
      signals.push({
        company: companyGuess,
        feed: 'NEWSAPI',
        signal: 'breach_news',
        date: (article.publishedAt || today).split('T')[0],
        link: article.url || '',
        excerpt: article.title || '',
        cveID: null,
        affectedProduct: null,
      });
    }
  }

  // HHS OCR (CSV rows, if successfully fetched as JSON/CSV)
  if (raw.breaches || Array.isArray(raw)) {
    const rows = raw.breaches || raw;
    for (const row of rows) {
      const name = row['Name of Covered Entity'] || row.entity || '';
      if (!name) continue;
      signals.push({
        company: name,
        feed: 'HHS_OCR',
        signal: 'hipaa_breach',
        date: row['Breach Submission Date'] || today,
        link: 'https://ocrportal.hhs.gov/ocr/breach/breach_report.jsf',
        excerpt: `HIPAA breach: ${name} — ${row['Type of Breach'] || 'breach type unknown'}, ${row['Individuals Affected'] || '?'} individuals affected.`,
        cveID: null,
        affectedProduct: null,
      });
    }
  }
}

// Dedupe by company+feed+date
const seen = new Set();
const deduped = signals.filter(s => {
  const key = `${s.company}|${s.feed}|${s.date}`;
  if (seen.has(key)) return false;
  seen.add(key);
  return true;
});

return deduped.map(s => ({ json: s }));
```

- [ ] **Step 2: Test normalization with live data**

Run the workflow up through the Normalize node. Confirm output is an array of objects matching the shape above. Check that SEC hits have company names, CISA KEV items have `cveID` populated, NewsAPI items have some `company` value (even if imperfect).

---

## Task 4: Exclusion Check Code Node

**What:** Filter out any signal whose company name matches the hard-exclude list. Drop silently, do not draft or brief.

- [ ] **Step 1: Add Exclusion Check Code node after Normalize Signals**

Name it `Exclusion Check`. Paste this JavaScript, replacing the array with the full contents of `reference_onyxia_exclusions.md`:

```javascript
// Hard-exclude list — update when reference_onyxia_exclusions.md changes
const EXCLUSIONS = [
  'Solomon Rozental',
  'Hornblower',
  // ... paste full list from reference_onyxia_exclusions.md here
];

const excluded = new Set(EXCLUSIONS.map(e => e.toLowerCase().trim()));

return $input.all().filter(item => {
  const company = (item.json.company || '').toLowerCase().trim();
  if (!company) return true; // CISA KEV items have no company yet — pass through
  const isExcluded = EXCLUSIONS.some(ex => company.includes(ex.toLowerCase()));
  return !isExcluded;
});
```

- [ ] **Step 2: Test exclusion filter**

Temporarily add a known exclusion name to the test data (by editing the code node input). Confirm it's dropped. Remove test data. Confirm clean signals pass through.

---

## Task 5: HubSpot Dedupe + Branch

**What:** For each signal company, search HubSpot. Branch into three paths: (A) active account, (B) dormant/lost, (C) not found.

**Node map:**
```
Exclusion Check
  → HubSpot Company Search (HTTP Request)
  → IF: Active Account?  → [path A: flag for immediate alert]
  → IF: Known but cold?  → [path B: morning brief only]
  → [path C: new prospect → Fit Score]
```

- [ ] **Step 1: Add HubSpot Company Search HTTP Request node**

Name: `HubSpot Search Company`. Method: POST.
URL: `https://api.hubapi.com/crm/v3/objects/companies/search`
Auth: Bearer token (use existing HubSpot credential from workflow 01).
Body (JSON):
```json
{
  "filterGroups": [{
    "filters": [{
      "propertyName": "name",
      "operator": "CONTAINS_TOKEN",
      "value": "={{$json.company}}"
    }]
  }],
  "properties": ["name", "hs_lead_status", "dealstage", "hubspot_owner_id"],
  "limit": 1
}
```

- [ ] **Step 2: Add IF node — Active Account check**

Name: `IF Active Account`. Condition:
```
{{$json.results[0].properties.hs_lead_status}} equals "OPEN"
OR
{{$json.results[0].properties.dealstage}} exists
```
True → path A (immediate Slack alert, handled in Task 7).
False → next IF node.

- [ ] **Step 3: Add IF node — Known but cold**

Name: `IF Known Cold`. Condition:
```
{{$json.results.length}} greater than 0
```
True → path B (morning brief mention only, handled in Task 8).
False → path C (new prospect, proceed to fit scoring).

- [ ] **Step 4: Test branching with a known account**

Use a company name from your active HubSpot pipeline (e.g., "Medusind"). Confirm the signal routes to path A. Use a cold/unknown company name. Confirm it routes to path C.

---

## Task 6: Fit Score Code Node (Path C — New Prospects)

**What:** For new prospects not in HubSpot, enrich via ZoomInfo and score 1–5 against the ICP rubric. Drop score-1 signals. Queue 2–3 for morning brief. Route 4–5 to auto-draft.

- [ ] **Step 1: Read ICP rubric**

Open `~/ObsidianVault/50_Intel/icp.md`. Extract the 1–5 scoring criteria. You will hardcode this logic into the code node below.

- [ ] **Step 2: Add ZoomInfo Auth HTTP Request node (same pattern as workflow 01)**

Name: `ZoomInfo Auth (Signal)`. Copy the `ZoomInfo Authenticate` node configuration from workflow `oN4ND73TkvSD2tyX`. This returns an access token stored in the output.

- [ ] **Step 3: Add ZoomInfo Enrich HTTP Request node**

Name: `ZoomInfo Enrich Company`. POST to ZoomInfo's company search endpoint (same endpoint as workflow 01's `ZoomInfo Search Tier 1`). Pass `{{$json.company}}` as the company name. Retrieve: `employeeCount`, `industry`, `revenueRange`, `techStack`, `hqCountry`.

- [ ] **Step 4: Add Fit Score Code node**

Name: `Fit Score`. Paste this JavaScript, replacing the rubric with actual criteria from `50_Intel/icp.md`:

```javascript
const signal = $('Exclusion Check').first().json;
const zi = $input.first().json; // ZoomInfo enrichment result
const company = zi.data?.companyResults?.[0] || {};

let score = 0;

// Criterion 1: Vertical match (healthcare, fins, mfg, critical infra)
const industry = (company.industry || '').toLowerCase();
const verticalMatch = ['health', 'hospital', 'financial', 'bank', 'manufactur', 'utility', 'energy', 'insurance'].some(v => industry.includes(v));
if (verticalMatch) score += 2;

// Criterion 2: Company size (100-5000 employees = mid-market sweet spot)
const employees = company.employeeCount || 0;
if (employees >= 100 && employees <= 5000) score += 1;
else if (employees > 5000) score += 1; // enterprise still valid

// Criterion 3: US-based
if ((company.hqCountry || '').toLowerCase() === 'united states') score += 1;

// Criterion 4: Signal urgency boost — breach signal from regulated industry
if (['SEC_8K','HHS_OCR'].includes(signal.feed) && verticalMatch) score += 1;

// Cap at 5
score = Math.min(score, 5);

return [{
  json: {
    ...signal,
    fitScore: score,
    employeeCount: employees,
    industry: company.industry || '',
    hqCountry: company.hqCountry || '',
    techStack: company.techStack || [],
    ziEnriched: true,
  }
}];
```

- [ ] **Step 5: Add IF node — Score branch**

Name: `IF Score ≥4`. Condition: `{{$json.fitScore}} >= 4`
True → auto-draft (Task 7).
False → IF Score ≥2 → morning brief (Task 8). Score 1 → NoOp (drop).

- [ ] **Step 6: Test scoring with a real company name**

Use "First Horizon" (financial services, US, ~5000 employees). Confirm score comes back ≥3. Use a small international company. Confirm score comes back 1–2.

---

## Task 7: Auto-Draft Code Node + Slack Post (Path A + Path C fit ≥4)

**What:** Generate a cold email using Claude, then POST to the Slack Notifier webhook for approval in `#miles-ai-ops`.

- [ ] **Step 1: Add Claude Draft Code node**

Name: `Generate Draft`. Add after the `IF Score ≥4` true branch AND as a separate branch after `IF Active Account` true branch. Paste this JavaScript:

```javascript
const signal = $input.first().json;

const angleMap = {
  'SEC_8K': 'You filed an 8-K disclosing a material cybersecurity incident. Boards are watching. Regulators are watching. The window to show a remediation path is narrow.',
  'HHS_OCR': 'Your organization is navigating a HIPAA breach. OCR investigations move fast. The question your board will ask is what you\'re doing to close the exposure gap.',
  'CISA_KEV': `CISA flagged active exploitation of ${signal.affectedProduct || 'software in your environment'}. The remediation deadline is ${signal.dueDate || 'imminent'}.`,
  'NEWSAPI': 'Organizations in your sector are dealing with breaches that are making headlines. The pattern is consistent: exposure gaps that existed before the incident.',
};

const angle = angleMap[signal.feed] || angleMap['NEWSAPI'];
const company = signal.company || 'your organization';

const prompt = `Write a cold outreach email from Miles Bastianich, Enterprise AE at Onyxia Cyber, to the CISO or VP Security at ${company}.

Context: ${angle}

Onyxia Cyber helps security teams find and close data exposure gaps before they become incidents. The CEO is Sivan Tehila, former CISO — peer credibility, not vendor pitch.

Rules (hard):
- Short sentences. Maximum 3 sentences per paragraph.
- No em dashes. Use periods or commas.
- No words: leverage, synergy, ecosystem, robust, seamless, unlock, empower, streamline.
- Peer tone. Not a vendor. Not a pitch.
- Total length: under 100 words for the body.
- End with one low-commitment CTA: "Worth 15 minutes?"
- No subject line needed, just the body.

Output only the email body. Nothing else.`;

const response = await $http.request({
  method: 'POST',
  url: 'https://api.anthropic.com/v1/messages',
  headers: {
    'x-api-key': $credentials.Anthropic.value,
    'anthropic-version': '2023-06-01',
    'content-type': 'application/json',
  },
  body: JSON.stringify({
    model: 'claude-sonnet-4-6',
    max_tokens: 300,
    messages: [{ role: 'user', content: prompt }],
  }),
});

const draft = response.content?.[0]?.text || '';

return [{
  json: {
    ...signal,
    draft,
    slackMessage: [
      `*Signal: ${signal.feed}* | Fit: ${signal.fitScore || 'active account'}/5`,
      `*Company:* ${company}`,
      `*Trigger:* ${signal.excerpt}`,
      `*Source:* ${signal.link}`,
      ``,
      `*Draft:*`,
      '```',
      draft,
      '```',
      `React ✅ to approve and send | 👎 to reject | ✏️ to edit`,
    ].join('\n'),
  }
}];
```

- [ ] **Step 2: Add Slack Post HTTP Request node**

Name: `Post Draft to Slack`. POST to the Slack Notifier webhook URL (from Task pre-flight).
Body:
```json
{
  "channel": "C0AUB4DATP0",
  "text": "={{$json.slackMessage}}"
}
```

- [ ] **Step 3: Test with a synthetic signal**

Manually inject a test signal (company: "Test Health System", feed: "SEC_8K", fitScore: 5). Confirm a Slack message appears in `#miles-ai-ops` with a draft email body under 100 words.

- [ ] **Step 4: Verify voice rules in output**

Read the draft. Confirm: no em dashes, no jargon words, under 100 words body, ends with a CTA.

---

## Task 8: Morning Brief Queue (Path B + Path C fit 2–3)

**What:** For dormant/known-cold accounts (path B) and new prospects scoring 2–3 (path C low), aggregate into a single morning brief block rather than individual Slack posts.

- [ ] **Step 1: Add Aggregate Code node**

Name: `Aggregate Brief Items`. This node collects all path B and path C low-score signals, formats them as a single Slack block, and posts once.

```javascript
const items = $input.all().map(i => i.json);

if (items.length === 0) return [{ json: { skip: true } }];

const lines = items.map(s =>
  `• *${s.company || 'Unknown'}* [${s.feed}] score:${s.fitScore || '—'} — ${s.excerpt?.slice(0, 80) || ''}... <${s.link}|link>`
);

return [{
  json: {
    slackMessage: [
      `*Signal Intelligence — ${new Date().toISOString().split('T')[0]}*`,
      `${items.length} signal(s) below auto-draft threshold:`,
      ...lines,
    ].join('\n'),
  }
}];
```

- [ ] **Step 2: Add IF Skip node before Slack post**

Condition: `{{$json.skip}} is not true`. Only post if there are items.

- [ ] **Step 3: Add Slack Post HTTP Request node**

Name: `Post Brief Summary to Slack`. Same config as Task 7 Step 2.

- [ ] **Step 4: Test with a synthetic low-score signal**

Inject a company with fit score 2. Confirm it appears in the brief summary block, not as a draft.

---

## Task 9: CISA KEV Tech Stack Branch

**What:** CISA KEV signals don't have a company name — they have an affected product. This task adds a ZoomInfo technology query to find ICP prospects running the affected software, then runs each match through the main pipeline.

This task is separate from Tasks 5–8 and runs in parallel after Task 3 normalization — only on items where `feed === 'CISA_KEV'`.

- [ ] **Step 1: Add IF node after Normalize Signals to split CISA from name-based signals**

Name: `IF CISA KEV`. Condition: `{{$json.feed}} equals CISA_KEV`.
True → CISA tech stack path.
False → Exclusion Check (existing Task 4 path).

- [ ] **Step 2: Add ZoomInfo Tech Stack Query HTTP Request node**

Name: `ZoomInfo Find Companies Using Product`. POST to ZoomInfo company search with technology filter:
```json
{
  "searchCriteria": {
    "techCriteria": [{"categoryName": "={{$json.affectedProduct}}"}],
    "industryCriteria": [
      {"industryCode": "2062"},
      {"industryCode": "6020"},
      {"industryCode": "2000"},
      {"industryCode": "4911"}
    ],
    "employeeRangeLow": 100,
    "employeeRangeHigh": 10000,
    "countryCode": ["US"]
  },
  "maxResults": 10
}
```

- [ ] **Step 3: Add Code node to reshape ZoomInfo results into signal format**

Name: `Reshape CISA Matches`. Output one item per matched company, populating `company` from the ZoomInfo result, keeping `feed`, `cveID`, `affectedProduct`, `excerpt` from the original signal.

```javascript
const cisa = $('IF CISA KEV').first().json;
const ziResults = $input.first().json?.data?.companyResults || [];

return ziResults.map(company => ({
  json: {
    company: company.name,
    feed: 'CISA_KEV',
    signal: 'active_exploitation',
    date: cisa.date,
    link: cisa.link,
    excerpt: cisa.excerpt,
    cveID: cisa.cveID,
    affectedProduct: cisa.affectedProduct,
    dueDate: cisa.dueDate,
    industry: company.industry || '',
    employeeCount: company.employeeCount || 0,
    hqCountry: company.hqCountry || '',
  }
}));
```

- [ ] **Step 4: Connect Reshape output → Exclusion Check node (same as Task 4)**

Use n8n's node connection to route CISA matches into the same exclusion → HubSpot → scoring pipeline as other signals.

- [ ] **Step 5: Test CISA path**

Use a recent CISA KEV entry (e.g., a Cisco or Fortinet CVE). Confirm ZoomInfo returns companies, they flow through exclusion and HubSpot checks, and scoring runs correctly.

---

## Task 10: Activate and Smoke-Test Workflow 07

- [ ] **Step 1: Validate workflow via n8n**

Call `mcp__n8n-mcp__n8n_validate_workflow` with the workflow ID. Fix any errors returned.

- [ ] **Step 2: Run full workflow manually (dry run)**

In n8n UI, click "Execute workflow" on workflow 07 while it is still inactive. Watch execution log. Confirm:
- All 4 feeds return data
- Normalization produces ≥1 signal
- At least one signal reaches Slack (either draft or brief summary)
- No uncaught errors in Code nodes

- [ ] **Step 3: Check `#miles-ai-ops` in Slack**

Confirm a message appeared. Confirm format is correct: signal source, company, excerpt, draft (if applicable).

- [ ] **Step 4: Activate workflow 07**

Use `mcp__n8n-mcp__n8n_update_partial_workflow` to set `active: true`.

---

## Task 11: Build `07b — Active Account Watchdog`

**What:** Lightweight workflow. Runs every 2 hours. Fetches SEC 8-K and HHS OCR only. Matches company names against active HubSpot accounts. Immediate Slack ping on match.

**Node map:**
```
Schedule Trigger (every 2h, 08:00–16:00 ET)
  → Fetch Active HubSpot Accounts
  → Fetch SEC 8-K (last 2h)
  → Fetch HHS OCR (last 7 days)
  → Match Companies Code node
  → IF Match Found
    → Post Immediate Slack Alert
  → NoOp (no match)
```

- [ ] **Step 1: Generate workflow skeleton**

Call `mcp__n8n-mcp__n8n_generate_workflow`:

```
Create an n8n workflow named "07b — Active Account Watchdog" with:
1. Schedule Trigger: every 2 hours, restricted to 08:00–16:00 ET Monday–Friday
2. HTTP Request node "Fetch Active HubSpot Accounts": POST to https://api.hubapi.com/crm/v3/objects/companies/search with filter hs_lead_status = OPEN, properties: name, hs_lead_status, hubspot_owner_id, limit: 100. Use existing HubSpot credential.
3. HTTP Request node "Fetch SEC 8-K": GET https://efts.sec.gov/LATEST/search-index?q=%22Item+1.05%22+%22cybersecurity+incident%22&forms=8-K&dateRange=custom&startdt={{$now.minus(2,'hours').toISO()}}&enddt={{$now.toISO()}} with header User-Agent: "Onyxia-Cyber-Sales noreply@onyxia.io"
4. HTTP Request node "Fetch HHS OCR": same as workflow 07
5. Code node "Match Companies"
6. IF node "IF Match Found"
7. HTTP Request node "Post Slack Alert"
8. NoOp node "No Match"
Do not fill in the Code node or IF node logic yet.
```

- [ ] **Step 2: Create the workflow**

`mcp__n8n-mcp__n8n_create_workflow` with generated JSON. Keep inactive.

- [ ] **Step 3: Add Match Companies Code node logic**

```javascript
// Active HubSpot account names (lowercased for matching)
const hubspotResults = $('Fetch Active HubSpot Accounts').first().json;
const activeNames = (hubspotResults.results || [])
  .map(c => (c.properties?.name || '').toLowerCase().trim())
  .filter(Boolean);

// SEC 8-K company names
const secRaw = $('Fetch SEC 8-K').first().json;
const secHits = secRaw.hits?.hits || [];
const secCompanies = secHits.map(h => ({
  company: (h._source?.entity_name || '').toLowerCase().trim(),
  feed: 'SEC_8K',
  date: h._source?.file_date || '',
  link: `https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=${h._source?.file_num || ''}&type=8-K`,
  excerpt: `${h._source?.entity_name} filed 8-K Item 1.05 — material cybersecurity incident.`,
}));

// HHS OCR company names (if available)
const hhsRaw = $('Fetch HHS OCR').first().json;
const hhsRows = hhsRaw.breaches || hhsRaw || [];
const hhsCompanies = Array.isArray(hhsRows) ? hhsRows.map(r => ({
  company: (r['Name of Covered Entity'] || r.entity || '').toLowerCase().trim(),
  feed: 'HHS_OCR',
  date: r['Breach Submission Date'] || '',
  link: 'https://ocrportal.hhs.gov/ocr/breach/breach_report.jsf',
  excerpt: `HIPAA breach: ${r['Name of Covered Entity']} — ${r['Type of Breach'] || ''}, ${r['Individuals Affected'] || '?'} individuals.`,
})) : [];

const allSignals = [...secCompanies, ...hhsCompanies];

// Find matches
const matches = allSignals.filter(s =>
  s.company && activeNames.some(active =>
    active.includes(s.company) || s.company.includes(active)
  )
);

if (matches.length === 0) return [{ json: { matched: false } }];

return matches.map(m => ({ json: { ...m, matched: true } }));
```

- [ ] **Step 4: Set IF Match Found condition**

Condition: `{{$json.matched}} equals true`.

- [ ] **Step 5: Add Post Slack Alert HTTP Request node**

Name: `Post Immediate Alert`. POST to Slack Notifier webhook.
Body:
```json
{
  "channel": "C0AUB4DATP0",
  "text": ":rotating_light: *Active Account Signal* — {{$json.company}} | {{$json.feed}}\n{{$json.excerpt}}\n<{{$json.link}}|View filing>"
}
```

- [ ] **Step 6: Test watchdog with a known active account**

Temporarily inject a synthetic SEC response containing one of your active account names (e.g., "Medusind"). Confirm Slack alert fires. Remove synthetic data.

- [ ] **Step 7: Activate workflow 07b**

`mcp__n8n-mcp__n8n_update_partial_workflow` with `active: true`.

---

## Task 12: Wire 07 into Morning Brief (Handoff)

**What:** Ensure workflow 07's brief summary Slack post arrives before the 07:00 morning brief so the operator includes it. No new workflow needed — just timing confirmation.

- [ ] **Step 1: Confirm 07 schedule fires at 06:45 ET**

In n8n, view the Schedule Trigger node in workflow 07. Confirm timezone is set to `America/New_York` and time is `06:45`.

- [ ] **Step 2: Confirm morning brief (shift) reads `#miles-ai-ops`**

Open `~/ObsidianVault/40_Plays/shifts/morning-brief.md`. Confirm it instructs the operator to read `#miles-ai-ops` messages posted since midnight before composing the brief. If not, add: "Read all `#miles-ai-ops` posts since 06:00 ET. Include any Signal Intelligence items in the Top Signals section."

- [ ] **Step 3: Done**

Both workflows are active. The morning brief operator will pick up queued signals. Active account watchdog runs every 2h through the business day.

---

## Self-Review

**Spec coverage check:**
- ✅ SEC 8-K feed: Task 2 + 3
- ✅ HHS OCR feed: Task 2 + 3
- ✅ CISA KEV feed: Task 2 + 3 + 9
- ✅ NewsAPI feed: Task 2 + 3
- ✅ Exclusion check: Task 4
- ✅ HubSpot dedupe + 3-way branch: Task 5
- ✅ Fit scoring with ZoomInfo: Task 6
- ✅ Auto-draft for fit ≥4: Task 7
- ✅ Morning brief queue for fit 2–3: Task 8
- ✅ CISA tech stack matching: Task 9
- ✅ Active account immediate alert: Task 11 (07b)
- ✅ 06:45 ET daily schedule: Task 2 (07)
- ✅ Every-2h watchdog schedule: Task 11 (07b)
- ✅ Vault writes: deferred to operator shifts (noted in architecture — n8n is cloud-hosted, cannot write local filesystem directly)

**Open items before build:**
1. Miles needs to provide Anthropic API key for Task 1 Step 2
2. HHS OCR response format may require adjustment (Task 2 Step 6 handles this contingency)
3. ZoomInfo tech stack query field names should be verified against the ZoomInfo API schema used in workflow 02 — check `IE0HwcQvVaNiirEl` for exact field names before Task 9
