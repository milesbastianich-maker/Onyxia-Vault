---
type: audit
audit: brain-systems
date: 2026-05-05
auditor: The Brain (Claude Code, opus-4-7)
scope: structural + capture + cross-link + plugins + roadmap
read_only: true
---

# Brain Audit — 2026-05-05

Vault state at audit time. Read-only audit. Every claim traces to a file path or a grep result. Every plugin recommendation traces to a cited last-update date. Proposals at the bottom; nothing in the vault has been edited.

If you only read three things in this file: P0-1, P0-2, P0-3 in section 9.

---

## 1. Vault Cartography

390 markdown files across 12 top-level directories. Counts:

| Folder | MDs | Health |
|---|---|---|
| `00_Index/` | 4 | MOC files exist, all use Dataview. No MOC for methodology, competitors, verticals, or personas. |
| `10_Accounts/` | 74 (51 active + 23 staged) | Average 5.0 outbound wikilinks/file. Frontmatter SCHEMA DRIFT (see §4). |
| `20_Contacts/` | 75 | Average 3.0 outbound wikilinks/file. 30+ contacts with zero `[[Account]]` backlink to their own deal. |
| `30_Contacts/staged/` | 22 | DUPLICATE TAXONOMY VIOLATION. CLAUDE.md says contacts live at `20_Contacts/`. The `30_Contacts/` folder shouldn't exist. Created 2026-05-04 during a hunt staging run. |
| `30_Meetings/` | 14 | 6.2 wikilinks/file (good). 7 of 14 are prep with NO matching debrief. |
| `40_Events/` | 3 + cohort | Baecco dinner spec + cohort drafts file + hunt research. |
| `40_Plays/` | 30 | Good structure. Hunt sub-folder, sequences sub-folder, shifts sub-folder. |
| `50_Intel/` | 101 | 13 methodology files, 11 competitor files, 4 personas, 10 verticals, 7 triggers, 25 signal-log files. The brain. |
| `60_Lessons/` | 16 | Daily rejections (3 files), daily replies (7 files), weekly review (1 file). |
| `70_Daily/` | 23 | Daily notes 2026-04-21 through 2026-05-05. Plus claude-activity sub-folder + drafts-awaiting-send + sessions. |
| `90_Templates/` | 11 | Templates exist. Most are not enforced — see §4. |
| `copilot/` | 15 | Copilot custom prompts. Out of taxonomy — should sit under `90_Templates/` or `00_Index/`. |

**Vault root pollution:** 4 files at `~/ObsidianVault/*` that should not be there:
- `2026-05-05.md` (empty, 0 bytes — autocreated by Daily Notes plugin to wrong folder)
- `Untitled.canvas`, `Untitled.base` (orphan canvas + base)
- `README.md` (158 bytes — bootstrap remnant)

**Top hub notes by inbound link count (capped at top 10):**

| Inbound | Note |
|---|---|
| 6 | `20_Contacts/Jigar Shah.md` |
| 4 | `50_Intel/playbook/closed-won-patterns.md` |
| 4 | `20_Contacts/Megan Marshall.md` |
| 4 | `10_Accounts/Medusind.md` |
| 4 | `10_Accounts/Elevate Textiles.md` |
| 3 | `50_Intel/playbook/closed-lost-patterns.md` |
| 3 | `50_Intel/methodology/pain-library.md` |
| 3 | `50_Intel/methodology/email-style-guide.md` |
| 3 | `50_Intel/methodology/cold-email-failure-modes.md` |
| 3 | `50_Intel/methodology/cold-email-canon.md` |

**Reading:** the cold-email methodology files Miles built last week are the highest-leverage assets in the vault and they sit at 3 inbound links each. They are written but not threaded. The drafter sub-agent reads them; account files do not. That is the single biggest cross-link debt in the system.

**Dead-end methodology files:** 7 of 13 methodology files have ZERO outbound wikilinks (verified by grep). The methodology folder is a peninsula, not a hub.

---

## 2. Capture Surface Audit

Every input channel into the vault, ranked by current reliability:

| Channel | Latency | Reliability | Format consistency | Gap risk |
|---|---|---|---|---|
| Manual writes via Claude Code agents (operator, hunter, drafter) | minutes | High | Schema drift (§4) | LOW |
| Daily notes (`70_Daily/`) | hourly via Periodic Notes | Medium | One-off vault-root leakage today (`2026-05-05.md` at root, empty) | MEDIUM |
| Granola (post-call source — primary) | manual paste today | LOW (manual paste) | Inconsistent — see Elevate Textiles debrief vs others | HIGH |
| HubSpot (deal stage / contact enrichment) | manual via agent | High when invoked | Agent-driven, mostly clean | MEDIUM (drift between vault `last_touch` and HubSpot reality) |
| ZoomInfo (contact enrichment) | manual via agent | High | Clean (zoominfo_id frontmatter standard) | LOW |
| RB2B visitor signals | Slack `#rb2b` only | Not in vault | n/a | HIGH — every RB2B hit dies in Slack, never lands in vault |
| Slack `#miles-ai-ops` | Not in vault | Not in vault | n/a | HIGH — shift outputs, drafter approvals, rejection reactions die in Slack |
| Gmail (replies + sent + drafts) | Manual via agent | MEDIUM | Inconsistent — some replies logged in `60_Lessons/replies/`, most not | HIGH |
| Calendar (meetings) | Manual via agent | Medium | `30_Meetings/` prep notes good, debriefs missing | HIGH (7 of 14 prep notes have no debrief) |
| Mobile / voice capture | None today | n/a | n/a | HIGH — vault has zero mobile capture path |
| iOS Shortcuts → Obsidian | None | n/a | n/a | n/a |

**Capture leaks identified (intel landing somewhere that isn't surfaced in the vault):**

1. **RB2B Slack feed.** Per `00_Index/CLAUDE.md` lines 196-201, every RB2B visit auto-posts to Slack. The vault has zero RB2B notes. Hot intent signals are evaporating into Slack scrollback.
2. **Slack `#miles-ai-ops` shift outputs.** Morning brief, midday signal check, EOD wrap, weekly synthesis all post to Slack per CLAUDE.md lines 165-174. The vault has only a `60_Lessons/2026-05-05-pre-vacation-brief.md` and Friday weekly reviews. Daily shift outputs are not durably stored.
3. **Granola call notes.** No automated sync. Pre-vacation brief explicitly flags "Touch-tracker last updated 2026-04-27" and "no debrief on file" for 7 post-Apr-29 prep notes. Granola has the call data; the vault doesn't.
4. **Gmail replies.** `60_Lessons/replies/` has 7 daily files (last 2026-05-04), but every other Gmail thread state lives only in Gmail. The reply-intent-parser play assumes Slack approval, not vault writeback.
5. **HubSpot deal stage drift.** Per CLAUDE.md HubSpot translation table, Onyxia's `dealstage` IDs are inverted from defaults. No vault validator catches this drift; agents are individually responsible.

---

## 3. Retrieval Path Audit

Five top operator queries, click/search paths simulated, friction flagged:

### Query 1: "What's the state of the Medusind deal?"

Path today: `Cmd-O` → type "Medusind" → land on `10_Accounts/Medusind.md`. **Three clicks. ✅ No friction.**

### Query 2: "What did Rick Scott say in Monday's demo?"

Path today: `Cmd-O` → type "Elevate" → choose between account file or debrief. Account file has good Timeline pointer. Debrief is at `30_Meetings/2026-05-05-elevate-textiles-debrief.md`. **3 clicks if you remember to look in Meetings. 5+ clicks if you guess wrong.** FRICTION: account file's Timeline does not link to the debrief file by wikilink (only mentions the date). Right click → backlinks works but is one extra step. ✋

### Query 3: "What's our positioning vs OneTrust?"

Path today: `Cmd-O` → "onetrust" → `50_Intel/competitors/onetrust.md`. **2 clicks. ✅** But: no MOC file at `00_Index/MOC_Competitors.md`, so if you don't know the file exists you can't browse the competitor stack. The competitor folder has a README; the README is fine but invisible from `00_Index/`.

### Query 4: "Healthcare vertical brief — what regulations matter this quarter?"

Path today: `Cmd-O` → "healthcare" → 3 hits (`50_Intel/verticals/healthcare.md`, account files, persona files). Right answer is verticals/healthcare. **FRICTION: no MOC for verticals.** Plus the regulatory calendar at `50_Intel/industry/regulatory-calendar.md` is a sibling file with overlapping data. Two files, one query, no link between them. ✋

### Query 5: "When does the SEC Item 1.05 disclosure deadline apply to a deal we just won?"

Path today: full-text search "Item 1.05" → 6+ hits across pain-library, methodology, account files. **FRICTION: no canonical regulatory landing page that aggregates regulation × deal-impact in one view.** A new agent or a non-Miles operator would burn 5-10 minutes here. ✋

### Query 6: "All my active deals with no champion named"

Path today: `00_Index/MOC_Pipeline.md` → Dataview "Missing champion" block. **Should work.** But Dataview filter is `WHERE !champion OR champion = ""`, and 7 active accounts have `champion: _unknown - research needed_` — that string is NOT empty, so the filter MISSES THEM. The MEDDPICC dashboard is producing a false-clean read on at least 7 deals. CRITICAL.

### Query 7: "Show me the cold email pattern that worked for the new-CISO trigger"

Path today: `Cmd-O` → "canon" → `50_Intel/methodology/cold-email-canon.md` → scroll for Pain #4 entry. **3 clicks if you know the file. 8+ clicks if you don't.** FRICTION: the brain map at `50_Intel/methodology/README.md` is excellent but lives one folder deep with no link from `00_Index/`. New agent / new operator does not know it exists.

**Retrieval friction summary:**
- 4 of 7 top queries hit friction (queries 2, 4, 5, 7).
- 1 of 7 produces SILENTLY WRONG answers (query 6 — placeholder strings bypass Dataview filters).
- The methodology brain map is invisible from `00_Index/`.

---

## 4. Taxonomy & Linking Health

### Frontmatter schema drift (account files)

Three distinct schemas in active use across `10_Accounts/`:

**Schema A** (~13 files, e.g., `AAR Corp.md`, `Cornell University.md`, `KRATOS.md`, `Shift4.md`):
```
company, domain, ticker, vertical, employees, revenue, fit_score, stage, lifecycle,
hubspot_owner_id, next_action, next_action_date, last_touch, tags
```

**Schema B** (~10 files, e.g., `AeroVironment.md`, `BioMarin.md`, `V2X.md`):
```
type, company, domain, ticker, vertical, account_tier, hubspot_id, arr_target, stage, status,
created, last_touch, next_action, next_action_date, tags, fit_score, trigger, employees, revenue, hq
```

**Schema C** (the canonical-template-aligned one — most Tier 1 active deals, e.g., `AKUVO.md`, `Medusind.md`, `Cherry Bekaert.md`):
```
type, company, domain, vertical, account_tier, hubspot_id, arr_target, stage, status,
created, last_touch, next_action, next_action_date, metrics, economic_buyer, champion, paper_process, tags
```

The template at `90_Templates/tpl-account.md` defines Schema C minus `account_tier` and `hubspot_id` (it uses `hubspot_id` as a frontmatter key but the template lists it generically). Schemas A and B come from older bulk hunts and never got migrated.

**Why this matters:**
- `MOC_Pipeline.md` queries on `champion`, `economic_buyer`, `paper_process`, `metrics`. Schemas A and B don't have those fields. **23 of 51 active accounts are silently invisible to the MEDDPICC dashboard.**
- Stage label values are mixed: `"discovery"`, `"scoping"`, `"poc"`, `"negotiation"`, `"closed"` — none of those are HubSpot internal IDs. Per CLAUDE.md HubSpot translation table, the vault uses semantic labels but the source-of-truth IDs in HubSpot are inverted. No vault file documents this mapping at the schema level.

### Tag vocabulary drift (CLAUDE.md says vocabulary is closed; it isn't)

CLAUDE.md lines 61-69 define a closed vocabulary:
- `#v/healthcare` `#v/fins` `#v/mfg` `#v/ci`

Actually in use:
- `#v/healthcare` ✅
- `#v/fins` ✅
- `#v/mfg` ✅
- `#v/ci` ✅
- `#v/defense` ❌ NEW — not in CLAUDE.md
- `v/manufacturing`, `v/banking`, `v/critical-infrastructure`, `v/insurance`, `v/life-sciences`, `v/edtech`, `v/education`, `v/construction` ❌ ALL NEW — synonyms for the canonical short forms
- `v/healthcare v/fins` (combined string) ❌

Plus an unsanctioned `hunt/*` tag tree: `hunt/2026-04-22`, `hunt/2026-04-22-ci`, `hunt/2026-04-22-open`, `hunt/icp-lookalike-hunt`, `hunt/intent-signal-hunt`, `hunt/trigger-event-hunt`. These exist on 16+ account files and were created during the staged-account hunts. They are useful BUT they are not in CLAUDE.md, so the next agent that reads CLAUDE.md will not know they exist and may either delete them or duplicate them.

### Frontmatter tag style drift

Some account files write `tags: [account, active]` (plain). Others write `tags: [account, "#active", "#stage/poc"]` (hash-prefixed inside YAML). The hash-prefix style breaks Dataview's `contains(tags, "active")` filter. Verified: 16 files use hash-prefix, 51 use plain. Some MOC dataview queries are returning false-clean results.

### Links to non-existent files (link rot sample)

Spot-check on `10_Accounts/Starboard Group.md`:
- `[[../50_Intel/verticals/other]]` — file does not exist. Should be `qsr-hospitality` or similar.
- `[[../50_Intel/triggers/pci-dss]]` — file does not exist. The `triggers/` folder has 7 files; pci-dss is not one.

Spot-check on `10_Accounts/AKUVO.md`:
- `[[../50_Intel/verticals/fins]]` — file does not exist. Actual file is `verticals/financial-services.md`.
- `[[../50_Intel/triggers/new-ciso-or-security-hire]]` — file does not exist. Actual file is `triggers/exec-hire.md` or `triggers/grc-hiring.md`.

This is broken-link rot. The agents are inventing target paths that match a guessed convention rather than reading the actual folder. Not catastrophic (Obsidian shows them as new-note placeholders), but the graph view is full of phantom nodes and clicking them creates duplicate empty files.

### MOC coverage gaps

`00_Index/` has 3 MOCs: Pipeline, Accounts, This_Week. **Missing:**
- `MOC_Competitors.md`
- `MOC_Verticals.md`
- `MOC_Personas.md`
- `MOC_Methodology.md` (or surface the existing `50_Intel/methodology/README.md` from the index)
- `MOC_Plays.md`
- `MOC_Triggers.md`

The methodology README is the right kind of file. It just isn't reachable from the front door.

---

## 5. Cross-Linking Quality (the threading question)

Verified by grep:

| Source folder | Targets `methodology/` | Targets `playbook/` | Targets `personas/` | Targets `verticals/` |
|---|---|---|---|---|
| `10_Accounts/` (51) | **1** | 15 | 18 | 33 |
| `30_Meetings/` (14) | 4 | 0 | 0 | 0 |
| `20_Contacts/` (75) | 0 | 0 | 0 | 0 |

**Reading:**

- The methodology brain (cold-email-canon, pain-library, email-style-guide, etc.) is the highest-built asset and is referenced by exactly 1 account file. The agents read the methodology before drafting; the account files don't tell future agents which spine pain was selected for which contact. A drafter that picks a pain today does not leave a trace at the account level. **The pain selection is not getting written back.**
- Contacts have ZERO links to methodology or personas. Every contact file should link to the persona file it maps to (CISO, GRC, VPSec, GC). This costs 5 minutes per contact and would unlock persona-based filtering.
- Meetings reference methodology only 4 of 14 times. The Elevate Textiles debrief (the strongest in the vault) does NOT link to email-style-guide, pain-library, or canon, even though the next outbound to Rick Scott will need them.

**The threading mandate (CLAUDE.md lines 217-244):** "Every observation must land where it will be read again." The methodology files are the read-again target. The account and meeting files are the observation source. The wires are not connected.

---

## 6. Plugin & Integration Gap Analysis

### Currently installed (verified `~/ObsidianVault/.obsidian/community-plugins.json`)

7 community plugins:
- `dataview` — used by all MOCs
- `obsidian-git` — sync via git push from CLAUDE.md ritual
- `periodic-notes` — daily/weekly note generation
- `obsidian-tasks-plugin` — present, not heavily used in active notes
- `templater-obsidian` — templates exist; enforcement spotty (see §4 schema drift)
- `copilot` — vault Q&A
- `smart-connections` — semantic embeddings + chat

Core plugins enabled: file-explorer, search, switcher, graph, backlinks, canvas, properties, daily-notes, templates, bookmarks, outline, sync, **bases** (✅).

### What's missing for THIS vault specifically

Each recommendation here is scoped to a real gap above, not a generic best-of list.

**1. QuickAdd** — last release v2.12.0 on 2026-03-05, actively maintained ([source](https://github.com/chhoumann/quickadd)). Why for THIS vault: the capture latency from "Granola call ended" to "vault has debrief" is currently HOURS to NEVER (7 of 14 prep notes have no debrief). QuickAdd + Templater can build a one-keystroke "new debrief from prep" macro that pulls the prep file, opens a debrief stub with frontmatter pre-filled, and links the two. Targets the §2 capture leak directly.

**2. Granola sync plugin (philfreo/obsidian-granola-plugin OR tomelliot/obsidian-granola-sync)** — philfreo last release v2.0.3 on 2026-03-16, actively maintained ([source](https://github.com/philfreo/obsidian-granola-plugin)). Why: per memory `reference_granola_mcp.md`, Granola is the primary post-call source as of 2026-04-27. Today there is no automated path from Granola to vault. This plugin auto-syncs meeting notes + transcripts + AI summaries via Granola's MCP API. Closes the #1 capture leak in §2. Two competing plugins exist (philfreo and tomelliot); pick philfreo for the MCP-API path.

**3. Linter (platers/obsidian-linter)** — actively maintained 2024-2026 ([source](https://github.com/platers/obsidian-linter)). Why: the schema drift across Schemas A/B/C (§4) is a daily hand-check problem. Linter can enforce frontmatter key order, required keys, tag format on every save. One-time config, daily payoff. The `tags: [account, active]` vs `tags: [account, "#active"]` style mismatch (16 vs 51 files) is exactly what Linter solves.

**4. Post Webhook (Masterb1234/obsidian-post-webhook)** — last release v1.2.5 ~Feb 2026, actively maintained ([source](https://github.com/Masterb1234/obsidian-post-webhook)). Why: the Onyxia Autopilot spec at `~/onyxia-autopilot/SPEC.md` is n8n-centric. A webhook plugin gives the vault an outbound channel to n8n without leaving Obsidian. Examples: highlight a Rick-Scott quote in the Elevate debrief → send to an n8n workflow that appends to `50_Intel/product/quotes.md` automatically. Closes the auto-promote-intelligence loop CLAUDE.md describes (lines 218-225).

**5. Bases (core, already enabled)** — Miles already has `bases: true` in core-plugins.json. Per [obsidian.rocks](https://obsidian.rocks/dataview-vs-datacore-vs-obsidian-bases/), Bases is faster than Dataview, GUI-driven, and good enough to replace Dataview for most use cases. Why: the MOC dashboards today break silently when frontmatter values are placeholder strings (query 6 in §3). Bases is GUI-filterable in real time and Miles can spot the false-clean before it ships. Not a new install — a workflow change. Migrate `MOC_Pipeline.md` and `MOC_Accounts.md` to Bases views first; keep Dataview for the long-tail queries.

**6. Datacore — DO NOT INSTALL YET.** The successor to Dataview, faster, but still in beta as of 2026 and the GitHub README explicitly says "work-in-progress" ([source](https://github.com/blacksmithgu/datacore)). [stale plugin risk if you adopt early]. Wait for v1.0 before migrating live MOCs.

**7. Omnisearch** — actively maintained ([source](https://github.com/scambier/obsidian-omnisearch)). Why: query 5 in §3 ("Item 1.05") returns 6+ hits with no relevance ranking in default search. Omnisearch is BM25-ranked, indexes PDFs and headings, returns the right note first. Marginal gain over default search but matters when looking up regulation content under time pressure. Note: this is BM25, not semantic — Smart Connections already gives semantic, the two are complementary.

**8. Whisper / iOS voice → Obsidian pipeline.** No single canonical plugin. Two patterns: (a) iOS Shortcut → Apple on-device transcription → write to Obsidian via Files app ([source](https://forum.obsidian.md/t/iphone-voice-memo-obsidian/63540)), or (b) DictaWiz on TestFlight, on-device Whisper, direct Obsidian export ([source](https://medium.com/obsidian-observer/using-obsidian-and-wispr-flow-for-lightning-quick-voice-to-text-notes-fc85bd66d8ac)). Why for Miles: the vault has no mobile capture path. Between meetings, walking, in cabs, the moment of "I just heard Rick Scott say something quotable" lives in the head until evening. By evening, it's lost. Voice → daily note section is the cheapest unblock for that. [uncertain] which path is best for Miles's iOS version; needs his test.

### What does NOT exist that the vault wants

- **No native Obsidian–HubSpot plugin.** Confirmed via search — the Obsidian forum thread requesting one is unanswered ([source](https://forum.obsidian.md/t/hubspot-integration/42609)). The path forward is n8n-mediated: vault → Post Webhook → n8n → HubSpot. The Onyxia Autopilot spec already covers this direction.
- **No native RB2B → Obsidian plugin.** Same answer: n8n in the middle. RB2B → Slack today; n8n can fork that to Obsidian via Post Webhook + a daily note `## RB2B hits` section.

---

## 7. Automation Gap Analysis

Cross-referenced against `~/onyxia-autopilot/SPEC.md` (referenced in `~/.claude/projects/-Users-milesbastianich/memory/project_onyxia_autopilot.md`) and the existing shift plays at `40_Plays/shifts/`.

| Manual today | Could be automated | Mechanism | Lift |
|---|---|---|---|
| Granola call → vault debrief | Auto-sync per Granola MCP plugin | philfreo plugin + Templater post-process to backlink to prep file | LOW (1 plugin install + 1 Templater script) |
| Slack `#miles-ai-ops` shift outputs → vault | Mirror to `60_Lessons/shifts/YYYY-MM-DD-{shift}.md` | n8n: Slack message → Post Webhook → vault file | MEDIUM (n8n flow + Post Webhook plugin) |
| RB2B Slack feed → vault daily note | Append RB2B hits to today's daily note | n8n: Slack → Post Webhook → daily note section | LOW |
| HubSpot stage drift detection | Daily diff `vault.stage` vs `HubSpot.stage` per CLAUDE.md translation table | n8n cron + onyxia-auditor | MEDIUM |
| Email reply intent classification → vault | Already specced in `40_Plays/reply-intent-parser.md` | Wire reply-intent-parser to write to `60_Lessons/replies/` automatically | LOW |
| Frontmatter schema enforcement | On-save Linter rule | Linter plugin config | LOW |
| MEDDPICC slot completion alerts | Bases view filtering on placeholder strings + active tag | Bases (already enabled) | LOW |
| Voice memo → vault | iOS Shortcut + Apple transcription + Files-app write | iOS Shortcut + a Templater script that ingests from Inbox folder | MEDIUM |
| Pain-spine selection writeback | Drafter writes the spine pain into the contact file frontmatter on every draft | Drafter sub-agent enhancement | LOW |
| Auto-promote intelligence (CLAUDE.md 218-225) | Already specced in `40_Plays/auto-promote-intelligence.md` | Wire to actually run nightly | MEDIUM |

---

## 8. Second-Brain Maturity Score

Using the CODE framework (Capture / Organize / Distill / Express).

| Axis | Score (1-10) | Evidence | What's needed for +1 |
|---|---|---|---|
| **Capture** | 4 | Manual paste from Granola; 7 of 14 prep notes have no debrief; vault root pollution; RB2B and Slack shift outputs leak; no mobile path. | Granola MCP plugin auto-sync. Post Webhook + n8n for Slack→vault. iOS voice path. Result: latency Granola→vault ≤ 5 min. |
| **Organize** | 6 | Folder taxonomy is sound. Templates exist. BUT three frontmatter schemas, tag-vocabulary drift (4 canonical tags, 12+ in use), broken wikilinks to phantom files, no MOCs for 5 of 7 top retrieval queries. | Linter + frontmatter migration to Schema C + a single MOC pass + delete the `30_Contacts/` duplicate folder. Result: closed vocabulary actually closed. |
| **Distill** | 7 | Methodology folder is genuinely strong (pain-library, canon, failure-modes, email-style-guide). Playbook closed-won/lost-patterns is 4 inbound each. Strong distillation work, just not reach. | Cross-link methodology back into account + meeting + contact files. Build the auto-promote loop. Result: every account file points to its current spine pain selection. |
| **Express** | 5 | Drafts ship. Drafter is wired to read methodology before writing. BUT the 35-draft discard on 2026-05-04 says express is fragile. Pain-spine selection happens at draft time and dies — it isn't written back to the contact or account file. | Make the spine-pain selection a vault artifact, not an in-flight computation. Drafter writes `current_spine_pain: Pain #4` to the contact frontmatter on every draft. Result: each future draft starts from the prior spine selection, not from scratch. |

**Composite: 5.5/10.** Healthy enough to operate. Visibly under-threaded.

---

## 9. Prioritized Roadmap (P0 → P2)

Scored by (impact 1-5) × (ease 1-5).

### P0 — ship this week (impact × ease ≥ 12)

**P0-1. Migrate the 23 Schema-A/B account files to Schema C and fix the false-clean MEDDPICC dashboard.** Impact 5, ease 3, score 15.
- Problem: 23 active accounts (45% of the active pipeline) are silently invisible to `MOC_Pipeline.md` because their frontmatter doesn't have `champion`, `economic_buyer`, `paper_process`, `metrics`. Plus: 7 active accounts have `champion: _unknown - research needed_`, and Dataview's `!champion OR champion = ""` filter MISSES that string. The dashboard reports a clean MEDDPICC pipeline when it's actually 30+ deals out of compliance.
- Fix: write a one-shot script that detects schema, migrates A/B → C, sets placeholders to `null` (not the literal string), and updates the Dataview filter to also catch `contains(string(champion), "unknown")`. Lift: half-day. Payoff: from "false-clean" to "actually-clean" pipeline visibility. Critical before next Friday review.
- Plugins/scripts: Linter + a one-time Templater migration script. Proposal listed in §10.

**P0-2. Cross-link methodology into account and meeting files (the threading sweep).** Impact 5, ease 4, score 20. **HIGHEST LEVERAGE THIS WEEK.**
- Problem: only 1 of 51 account files references the methodology folder. Drafter reads pain-library before writing; account files don't record which spine pain was selected. Every future draft starts cold.
- Fix: drafter sub-agent change — on every draft, the drafter writes `current_spine_pain`, `current_spine_pain_rationale`, and `last_draft_canon_match` into the contact file's frontmatter. Plus: a one-time backfill on the 9 active deals that have shipped drafts in the last 14 days. Plus: every meeting debrief gets a "## Methodology pointers" section with `[[../50_Intel/methodology/...]]` links to the canon entry that informed prep + the failure mode that worked.
- Lift: 1 hour to update the drafter sub-agent prompt; 2-3 hours to backfill 9 deals; 30 min to add the section to the debrief template. Payoff: every future draft inherits the prior spine selection. The methodology stops being a peninsula and becomes a hub.

**P0-3. Install Granola MCP plugin (philfreo) + wire one debrief-from-prep Templater macro.** Impact 5, ease 4, score 20.
- Problem: Granola is the primary post-call source as of 2026-04-27 per memory. Today, 7 of 14 prep files have no debrief. The Elevate Textiles debrief on 2026-05-05 was hand-written (high quality, but it took an hour). Eight days post-call is the half-life of a usable debrief; Spire Ortho, Cyber Diligent, AKUVO POC, Armstrong/TMF, IVISA prep notes are all past the half-life with no debrief.
- Fix: install philfreo's Granola plugin. Wire OAuth once. Add a Templater script that, on Granola sync, looks for a matching `30_Meetings/YYYY-MM-DD-{company}-prep.md` and creates a `*-debrief.md` stub that wikilinks back. Lift: 30 min install + 2 hours scripting. Payoff: zero-touch debriefs.

### P1 — ship this month (score 6-11)

**P1-4. MOC sweep — add MOC_Methodology, MOC_Competitors, MOC_Verticals, MOC_Personas, MOC_Plays, MOC_Triggers.** Impact 4, ease 4, score 16. (Pulled to P1 because P0-2 is more urgent — the methodology threading matters more than the methodology MOC.)
- Problem: 4 of 7 top retrieval queries hit friction because the front door (`00_Index/`) does not advertise the methodology, vertical, persona, or trigger files. The brain map at `50_Intel/methodology/README.md` is invisible from the index.
- Fix: 6 small MOCs, each ~10 lines, each Dataview-driven where possible. Lift: 1 hour. Payoff: zero-thought retrieval for any new agent or operator.

**P1-5. Install Linter + enforce one frontmatter schema (Schema C).** Impact 4, ease 3, score 12.
- Problem: 16 vs 51 split on hash-prefix tags. Three account schemas. Inconsistency creeps back even after P0-1 migration unless enforced on save.
- Fix: Linter plugin, configure YAML schema rules, on-save formatting. Lift: 2 hours config + test on 5 files. Payoff: drift stops.

**P1-6. Migrate `MOC_Pipeline.md` and `MOC_Accounts.md` from Dataview to Bases.** Impact 4, ease 3, score 12.
- Problem: Dataview filter ambiguity is what created the false-clean problem in P0-1. Bases is GUI-filterable, faster, and Miles can see the placeholder strings inline.
- Fix: build Bases views; keep Dataview MOCs as fallback for the long-tail queries. Lift: 2-3 hours. Payoff: ongoing pipeline truth.

**P1-7. Delete `30_Contacts/staged/` after migrating the 22 staged contacts to `20_Contacts/`.** Impact 3, ease 4, score 12.
- Problem: CLAUDE.md says contacts live at `20_Contacts/`. The `30_Contacts/staged/` folder exists with 22 hunt-staged contacts created 2026-05-04. This is taxonomy drift in real time.
- Fix: move 22 files to `20_Contacts/`, fix the wikilinks, delete the folder. Update the hunt sub-agent to write to `20_Contacts/` directly. Lift: 30 minutes. Payoff: no taxonomy ambiguity.

**P1-8. Wire Slack `#miles-ai-ops` shift outputs to `60_Lessons/shifts/YYYY-MM-DD-{shift}.md` via n8n + Post Webhook.** Impact 4, ease 2, score 8.
- Problem: morning brief, midday, EOD, watchdog all post to Slack only. Vault has only weekly synthesis. Daily shift state is ephemeral.
- Fix: install Post Webhook plugin (one-time), build n8n workflow (Slack RTM trigger → format → POST to webhook → vault file). Lift: 4-6 hours total. Payoff: full daily history of agent activity, queryable from Obsidian.

**P1-9. Backfill the 7 missing meeting debriefs (or kill the deals).** Impact 4, ease 2, score 8.
- Problem: IVISA, Spire Ortho, Cyber Diligent, AKUVO POC, Armstrong/TMF, Encora, and Cherry Bekaert all have prep but no debrief. Per `2026-05-05-pre-vacation-brief.md` these are at-risk threads.
- Fix: per-deal triage. For each: open Granola, write a 5-line debrief OR tag `#disqualified`. Lift: 2 hours. Payoff: pipeline truth.

### P2 — ship this quarter (score 4-5)

**P2-10. iOS voice → vault path (Apple on-device transcription via Shortcut, write to `70_Daily/inbox/`).** Impact 3, ease 2, score 6.
- Lift: half-day to set up the Shortcut + a Templater script that processes inbox files. Payoff: capture latency from "in a cab" → vault is < 5 min.

**P2-11. Move `copilot/` folder content into `90_Templates/copilot/` to align with template taxonomy.** Impact 2, ease 4, score 8.
- 15 files. Updates not breaking. Half-hour lift. Payoff: clean taxonomy.

**P2-12. Build `MOC_Quotes.md` aggregating verbatim customer quotes by spine pain.** Impact 3, ease 2, score 6.
- Problem: `50_Intel/product/quotes.md` exists but is one big file. Dataview-aggregated by `spine_pain` frontmatter would let the drafter find the right quote in one query.
- Lift: 2 hours to add quote-level frontmatter + build the MOC.

**P2-13. Standardize hunt/* tags into the closed vocabulary.** Impact 2, ease 3, score 6.
- Either officially add `#hunt/*` to CLAUDE.md or convert them to wikilinks per the CLAUDE.md rule "if you want to invent a new tag, use a wikilink instead."

---

## 10. Quick Wins (under 30 minutes, ship today)

**QW-1. Delete vault root garbage: `2026-05-05.md` (empty), `Untitled.canvas`, `Untitled.base`.** Already a 0-byte note in vault root from a misfired daily-notes-plugin run. 2 min.

**QW-2. Move `30_Contacts/staged/*.md` → `20_Contacts/` (22 files, no link breakage since none of them are linked from anywhere yet — verified by grep). Then `rm -r 30_Contacts/`.** 15 min.

**QW-3. Fix the Dataview "missing champion" filter in `MOC_Pipeline.md`.** Change the filter from `(!champion OR champion = "")` to `(!champion OR champion = "" OR contains(string(champion), "unknown"))`. Catches the 7 false-clean accounts. 5 min.

**QW-4. Add four lines to `00_Index/CLAUDE.md` "Where things live" table** for `40_Events/`, `50_Intel/methodology/`, `60_Lessons/rejections/`, `60_Lessons/replies/` so the next agent knows they exist. 5 min.

**QW-5. Add a single MOC stub at `00_Index/MOC_Methodology.md`** that just embeds `50_Intel/methodology/README.md`. Surfaces the brain-map from the front door. 5 min.

---

## 11. Proposals That Need Miles's Approval Before I Touch Anything

These are NOT done. Listed for sign-off:

1. **Approve P0-1: account schema migration** — touches 23 active account files' frontmatter. Risk: low (additive, no destructive renames), but it edits live deal records.
2. **Approve P0-2: drafter sub-agent enhancement to write `current_spine_pain` to contact frontmatter** — touches `~/.claude/agents/onyxia-drafter.md` (NOT a vault file, but a system change).
3. **Approve QW-2: delete `30_Contacts/` folder after migrating 22 files** — taxonomy correction.
4. **Approve P1-5: install Linter and configure auto-format-on-save** — changes how every save behaves going forward.
5. **Approve P1-6: migrate two MOCs from Dataview to Bases** — changes the daily dashboard format.
6. **Approve top-level taxonomy decisions:** keep `40_Events/` separate from `40_Plays/` (current state) or merge them. Keep `copilot/` at vault root or move to `90_Templates/copilot/`. Keep `30_Contacts/` deleted (recommended) or restore it as a real staging folder.

Per The Brain rules: I will not touch the top-level folder taxonomy (`00_Index`, `10_Accounts`, `20_Contacts`, `30_Meetings`, etc.) without your sign-off. Everything else above is recommendation only.

---

## 12. Sources Cited

- [QuickAdd v2.12.0 (2026-03-05) — chhoumann/quickadd](https://github.com/chhoumann/quickadd)
- [philfreo/obsidian-granola-plugin v2.0.3 (2026-03-16)](https://github.com/philfreo/obsidian-granola-plugin)
- [tomelliot/obsidian-granola-sync](https://github.com/tomelliot/obsidian-granola-sync)
- [blacksmithgu/datacore — work-in-progress, do not adopt yet](https://github.com/blacksmithgu/datacore)
- [Obsidian Bases vs Dataview vs Datacore — obsidian.rocks](https://obsidian.rocks/dataview-vs-datacore-vs-obsidian-bases/)
- [platers/obsidian-linter](https://github.com/platers/obsidian-linter)
- [Masterb1234/obsidian-post-webhook (~Feb 2026)](https://github.com/Masterb1234/obsidian-post-webhook)
- [scambier/obsidian-omnisearch](https://github.com/scambier/obsidian-omnisearch)
- [iPhone Voice Memo → Obsidian forum thread](https://forum.obsidian.md/t/iphone-voice-memo-obsidian/63540)
- [Obsidian + HubSpot integration request (unanswered)](https://forum.obsidian.md/t/hubspot-integration/42609)
- [Granola Sync Plus / philfreo plugin description](https://forum.obsidian.md/t/plugin-granola-meetings-simple-sync/111950)
- [Smart Connections vs Copilot comparison](https://smartconnections.app/obsidian-copilot/)

[uncertain] markers in the report flag claims that need Miles's local verification (iOS shortcut compatibility, Granola MCP behavior in Miles's Granola tier, Linter rule conflicts with existing templates).
