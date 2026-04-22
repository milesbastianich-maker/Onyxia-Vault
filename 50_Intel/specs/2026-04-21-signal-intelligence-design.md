# Signal Intelligence Layer — Design Spec

**Date:** 2026-04-21
**Status:** Approved, pending implementation
**Goal:** Ingest 4 free signal feeds (SEC 8-K, HHS OCR, CISA KEV, NewsAPI), score fit, auto-draft outreach for Tier 1 hits, surface the rest in the morning brief.

---

## Architecture

Two n8n workflows:

### `07 — Signal Intelligence (Daily)`
- **Schedule:** 06:45 ET daily (runs before morning brief at 07:00)
- **Function:** Full pipeline. Fetches all 4 feeds for the past 24h, extracts companies, dedupes against HubSpot, scores fit, branches on outcome.
- **Output:** Queued morning brief items + auto-drafted emails posted to `#miles-ai-ops`

### `07b — Active Account Watchdog`
- **Schedule:** Every 2 hours, 08:00–16:00 ET (5 runs/day)
- **Function:** Lightweight. Checks SEC 8-K and HHS OCR feeds only. Matches company names against active HubSpot accounts. No scoring — if match, ping immediately.
- **Output:** Immediate Slack ping to `#miles-ai-ops` with filing link and account context

Both workflows route through `00 — Slack Notifier (CLI bridge)` for all Slack posts.

---

## Feed Specifics

### SEC EDGAR 8-K (Item 1.05 — Cybersecurity Incident)
- **Endpoint:** `https://efts.sec.gov/LATEST/search-index?q=%22cybersecurity+incident%22&forms=8-K&dateRange=custom&startdt={yesterday}&enddt={today}`
- **Auth:** None
- **Cost:** Free
- **Cadence:** Daily (07) + every 2h (07b)
- **Fields extracted:** company name, CIK, filing date, item type, excerpt
- **Filter:** Item 1.05 filings only (material incident disclosures)
- **Volume:** ~2–5 filings/day across all public companies

### HHS OCR Breach Portal (Healthcare)
- **Endpoint:** `https://ocrportal.hhs.gov/ocr/breach/breach_report.jsf` (CSV download)
- **Auth:** None
- **Cost:** Free
- **Cadence:** Daily (07) — HHS updates weekly, filter by `Breach Submission Date` within last 7 days
- **Fields extracted:** covered entity name, state, type of breach, individuals affected, date submitted
- **Filter:** individuals affected ≥ 500 (public disclosure threshold)
- **Note:** Every entry is a HIPAA-covered entity. Direct fuel for healthcare vertical.

### CISA Known Exploited Vulnerabilities (KEV)
- **Endpoint:** `https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json`
- **Auth:** None
- **Cost:** Free
- **Cadence:** Daily (07 only — not in watchdog)
- **Fields extracted:** CVE ID, vendor, product, description, dateAdded, dueDate
- **Filter:** `dateAdded` = today
- **Special logic:** Match affected vendor/product against ZoomInfo tech stack data for ICP prospects. Does not match on company name — matches on what software they run.

### NewsAPI
- **Endpoint:** `https://newsapi.org/v2/everything?q={query}&from={yesterday}&sortBy=publishedAt&apiKey={KEY}`
- **Auth:** Free developer API key (100 req/day)
- **Cost:** Free
- **Cadence:** Daily (07 only)
- **Queries (4 per run, well within 100/day limit):**
  1. `"data breach" AND ("healthcare" OR "hospital" OR "health system")`
  2. `"ransomware" AND ("financial services" OR "bank" OR "credit union")`
  3. `"HIPAA fine" OR "OCR settlement" OR "SEC cybersecurity"`
  4. `"data breach" AND ("manufacturing" OR "critical infrastructure" OR "utilities")`
- **Fields extracted:** source, title, company name (parsed from title/description), URL, publishedAt

---

## Branching Logic

Every signal from SEC, HHS, and NewsAPI goes through this pipeline in order. CISA KEV follows a parallel path (tech stack match, not company name match).

### Step 1 — Exclusion Check
Match company name against `~/.claude/projects/-Users-milesbastianich/memory/reference_onyxia_exclusions.md`.
- **Match:** Drop signal. Log to `70_Daily/YYYY-MM-DD.md` as dropped + reason.
- **No match:** Continue.

### Step 2 — HubSpot Dedupe
Look up company name in HubSpot.

| HubSpot Result | Action |
|---|---|
| Active account (`#active`) | Skip scoring. Flag for morning brief + immediate ping if 07b |
| Dormant or lost account | Surface in morning brief only. No auto-draft. |
| Not found | Proceed to fit scoring |

### Step 3 — Fit Scoring (new prospects only)
Enrich via ZoomInfo. Score 1–5 against ICP rubric in `50_Intel/icp.md`.

| Score | Action |
|---|---|
| ≥4 | Auto-draft cold email + post to `#miles-ai-ops` for approval |
| 2–3 | Morning brief mention only. No draft. |
| 1 | Drop. Log to daily note. |

### Step 4 — Auto-Draft (fit ≥4 only)
Claude generates a cold email. Trigger angle varies by feed:

| Feed | Email angle |
|---|---|
| SEC 8-K | Post-incident framing. Board pressure. Remediation urgency. "You just disclosed a material incident — here's how companies in your position close the exposure gap." |
| HHS OCR | HIPAA breach. OCR investigation risk. "Healthcare organizations in active breach response need to show the board a remediation path fast." |
| CISA KEV | Tech stack exposure. "You may be running [Product] — CISA flagged active exploitation. Here's the window before this becomes your next 8-K." |
| NewsAPI | Industry breach as social proof. Peer framing. |

All drafts follow voice rules from `00_Index/CLAUDE.md`: short sentences, no em dashes, no jargon, peer tone.

Draft posted to `#miles-ai-ops` with:
- Signal source + link
- Company name + fit score
- ZoomInfo enrichment summary (size, vertical, tech stack)
- Draft email body

Awaits Miles's ✅ / 👎 / ✏️ reaction.

### CISA KEV Parallel Path
1. Extract today's new CVEs: affected vendor + product
2. Query ZoomInfo for ICP prospects running that product in their tech stack
3. Each match runs through Steps 1–4 above (exclusion → HubSpot dedupe → fit score → branch)
4. If active account match → immediate Slack ping with CVE details + remediation deadline

---

## Vault Integration

### Active accounts (any feed)
Append to `10_Accounts/{Company}.md` timeline. Append-only, never rewrite.
```
2026-04-21: [Feed] — [one-line signal description]. [link]
```

### New fit ≥4 prospects
Create stub `10_Accounts/{Company}.md` from `90_Templates/tpl-account.md`.
Pre-fill frontmatter: company, vertical tag, fit score, signal source, `next_action_date: today`, status: `#active`.
MEDDPICC slots left blank.

### CISA KEV active account matches
Append risk note to `10_Accounts/{Company}.md`:
```
2026-04-21: CISA KEV — CVE-XXXX-XXXXX affects [Product] (vendor: [Vendor]). Required remediation by [dueDate].
```

### Daily log
All signals logged in `70_Daily/YYYY-MM-DD.md` regardless of outcome:
- Company name, feed source, outcome (drafted / briefed / dropped), reason if dropped

### Intelligence promotion
If the same CVE, breach type, or industry pattern appears across 3+ signals in a 7-day window, `auto-promote-intelligence.md` (EOD shift) flags it for promotion to `50_Intel/`:
- New trigger event type → `50_Intel/icp.md`
- New CVE pattern → `50_Intel/triggers/{vendor}.md`
- New vertical breach wave → `50_Intel/verticals/{vertical}.md`

---

## Schedule Summary

| Workflow | Time | Feeds | Action |
|---|---|---|---|
| `07 — Signal Intelligence` | 06:45 ET daily | All 4 | Full pipeline |
| `07b — Active Account Watchdog` | Every 2h, 08:00–16:00 ET | SEC + HHS | Active account match → immediate ping |

---

## Dependencies

| Dependency | Status |
|---|---|
| HubSpot MCP | Connected |
| ZoomInfo MCP | Connected |
| Slack (`#miles-ai-ops`) | Connected |
| `00 — Slack Notifier` n8n workflow | Active |
| NewsAPI key | Needs free signup at newsapi.org |
| SEC EDGAR | No auth required |
| HHS OCR | No auth required |
| CISA KEV | No auth required |

---

## Out of Scope
- Paid signal sources (Apollo, Bombora, HIBP domain search)
- Automated sending (all outreach requires Miles's explicit approval)
- LinkedIn signal monitoring
