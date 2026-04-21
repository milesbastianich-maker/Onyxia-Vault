---
type: intel
subtype: product
topic: winning openers
source: HubSpot engagements on 23 closed-won deals (pending pull)
status: stub
created: 2026-04-22
updated: 2026-04-21
tags: [intel, product]
---

# Winning Openers

Verbatim winning subject lines + opening paragraphs from outbound that converted. Extract once, quote forever. No paraphrasing.

## Status

**Stub. Pull attempted 2026-04-21 and blocked.** The HubSpot MCP (`mcp__claude_ai_HubSpot__search_crm_objects`) was not connected in the attempted session. No engagement pulls completed. 0 of 23 deals extracted. Deal list and methodology below are ready; re-run when HubSpot MCP is available.

Execution plan when MCP is reachable:
1. For each deal ID in the corpus table, call `search_crm_objects` with `objectType: emails`, `filterGroups.associatedWith: objectType=deals objectIdValues=[deal_id]`, sort `hs_timestamp ASC`.
2. Walk results. First outbound (sender = Onyxia owner) in a thread with ≥1 inbound reply = winning opener.
3. Capture verbatim: `hs_email_subject`, first paragraph of `hs_email_text` (stop at first blank line), sender, date, deal vertical, deal amount.
4. Land under the correct vertical heading below. If thread subject was edited mid-thread, note both subject + timestamp.
5. Quality gate: if no outbound email found on a deal, write `_no cold-email engagement logged_` for that deal and move on. Do not fabricate.
6. Rate limit: back off between the 23 pulls. Partial coverage is acceptable; flag gaps explicitly.

## Corpus (23 deals, $1.77M)

### 20 direct wins (stage `closedlost` = "Closed Won")

| Deal | HubSpot ID | Amount | Owner ID | Vertical |
|---|---|---|---|---|
| Centra Health | 21137641741 | $270,000 | 828577255 | Healthcare |
| WellStar Health System | 17580317475 | $172,500 | 828577255 | Healthcare |
| Premera Blue Cross | 39015308946 | $170,000 | 77002456 | Health Insurance |
| Radiant Logic | 35742238216 | $165,000 | 77002456 | Identity (SaaS) |
| Port Authority NY/NJ | 18976438331 | $135,000 | 828577255 | Critical Infra / Transit |
| CCC Intelligent Solutions | 17855172696 | $120,000 | 828577255 | InsurTech |
| CWT | 16623577731 | $100,000 | 77002456 | Corporate Travel |
| Chipotle Mexican Grill | 13379402837 | $80,000 | 828577255 | QSR Retail |
| Summit Utilities | 23005589642 | $80,000 | 828577255 | Utilities |
| Orange County Transp. Authority | 35367262885 | $60,000 | 77002456 | Government / Transit |
| AXNY Group | 52864444073 | $60,000 | 77002456 | Staffing |
| Simpson Thacher & Bartlett | 18823952043 | $60,000 | 77002456 | BigLaw |
| Christiana Care Health | 15845496375 | $60,000 | 328493480 | Healthcare |
| Bausch + Lomb | 18358442881 | $58,500 | 828577255 | Pharma / Optics |
| Millennium Print (Pokemon) | 17546402117 | $45,000 | 569654559 | Print Manufacturing |
| Gaia Real Estate | 34629474981 | $37,500 | 328493480 | Real Estate |
| Vista Equity Partners | 32963382709 | $37,500 | 77002456 | Private Equity |
| Elite Technology | 33800353151 | $30,000 | 828577255 | Tech / SaaS |
| Adama | 50109905799 | $16,000 | 328493480 | Agri-Chemicals |
| Silverstein Properties | 14637893643 | $10,000 | 328493480 | Real Estate |

### 3 partner-pipeline wins (stage `252640014`)

| Deal | HubSpot ID | Owner ID |
|---|---|---|
| Alchemy Tech Group | 22813474874 | 828577255 |
| Consortium Networks | 22813844313 | 828577255 |
| World Wide Technology | 22813844097 | 828577255 |

## Extraction methodology

For each deal, pull the earliest outbound email engagement where `from = internal` AND the thread resulted in a replied-to conversation (`thread.messageCount > 1`). That is the winning opener.

1. Use HubSpot `search_crm_objects` with `objectType: emails` and `associatedWith.objectType: deals`, `objectIdValues: [<deal_id>]`.
2. Sort ascending by `hs_timestamp`. First outbound message with a same-thread inbound reply is the winning opener.
3. Capture verbatim: `hs_email_subject`, `hs_email_text` first paragraph, owner name, deal vertical, deal amount.

Land each win under the right vertical heading below. Do not paraphrase. If the subject was edited mid-thread, note both.

## By vertical

### Healthcare

_Pending pulls on: Centra Health, WellStar, Christiana Care._

### Health Insurance

_Pending pulls on: Premera Blue Cross._

### Financial Services (BigLaw + PE)

_Pending pulls on: Simpson Thacher, Vista Equity._

### Critical Infrastructure / Transit / Utilities

_Pending pulls on: Port Authority NY/NJ, Orange County Transp., Summit Utilities._

### Identity / SaaS / Tech

_Pending pulls on: Radiant Logic, Elite Technology, CCC Intelligent Solutions._

### Manufacturing / Pharma / Chemicals

_Pending pulls on: Bausch + Lomb, Millennium Print, Adama._

### Retail / Travel / Staffing

_Pending pulls on: Chipotle, CWT, AXNY Group._

### Real Estate

_Pending pulls on: Gaia Real Estate, Silverstein._

### Partner-pipeline

_Pending pulls on: Alchemy Tech Group, Consortium Networks, World Wide Technology._

## Rules for using this file

1. Quote verbatim. Paraphrase is an AI slop tell.
2. Match by vertical first. A healthcare opener that worked at WellStar is the seed for Medusind, not Chipotle.
3. Only reuse openers from wins owned by Maura, Brad, Sivan, or B. Fisher. Miles has zero direct closed-won deals in HubSpot yet; that is a data fact, not a judgment.
4. When the best-matching opener is from a different vertical, adapt the hook (trigger event + proof metric), keep the structure.
