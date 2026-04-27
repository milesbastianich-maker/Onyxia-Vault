---
type: intel
subtype: signal-log
play: reactivation-sweep
run_date: 2026-04-27
run_time: "20:00 ET"
tags: [intel, play]
---

# Reactivation Sweep — 2026-04-27

## Run summary

| Metric | Count |
|---|---|
| Total closed-lost corpus | 114 |
| Bucket 1 (non-responsive) mined | 68 |
| Bucket 2 (budget/time) mined | 28 |
| Bucket 3 (champion left) mined | 3 |
| Bucket 4 (old MQL, no deal) | 0 |
| Eligible after exclusions + territory check | ~38 |
| Enriched via ZoomInfo | 15 |
| Drafts staged in Gmail | 3 |

## Exclusions applied

- Israeli entities: Coca-Cola Israel, AppsFlyer, Mesh Payments, Fireblocks
- Security vendors: Rubrik, SolarWinds, Broadcom, Trustwave
- BigLaw (no warm path): Sullivan & Cromwell, Milbank, Lowenstein Sandler
- Sub-minimum deal size (<$25K): Drake Software, PointHR, Ted Baker
- Brad's deals < 12 months dormant: Veterans United (9mo)

## Top 15 ranked candidates

| Rank | Account | Bucket | ACV | Dormant | Trigger | Contact | Accuracy | Score |
|---|---|---|---|---|---|---|---|---|
| 1 | IPG | Non-responsive | $150K | 14mo | Omnicom M&A integration, 8,200 layoffs | Samantha Mahan, CISO | 99 | +2 |
| 2 | DTCC | Time-frame | $100K | 15mo | New CISO (Jun 2025), IT Security Engineering hire | Laura Deaner, CISO | 98 | +1 |
| 3 | Main Line Health | Budget | $100K | 19mo | CISO published InfoRiskToday microsegmentation article (Mar 2026) | Aaron Weismann, CISO | 95 | +1 |
| 4 | QBE Insurance | Non-responsive | $100K | 12mo | New security leader (Aug 2025), compliance hiring spike | Josh Mueller, Group Head Security | 98 | +2 |
| 5 | HarbourVest | Non-responsive | $125K | 14mo | C-suite hiring sprint | Timothy Tom, VP Dep. CISO | 98 | +1 |
| 6 | Natixis CIB Americas | Non-responsive | $100K | 17mo | NYDFS 500 ongoing compliance pressure | Michael Kroupa, CISO | 98 | +1 |
| 7 | Inspire Medical | Non-responsive | $100K | 14mo | Data governance RFP + vendor eval (Apr 2026) | No CISO contact found | N/A | +2 |
| 8 | Oscar Health | Non-responsive | $100K | 14mo | IT hiring spike, HIPAA surface | Nicolas Vigier, CISO | 93 | +1 |
| 9 | Hoag | Time-frame | $100K | 18mo | IT + Oracle Fusion finance hiring | No contact found | N/A | +1 |
| 10 | MTA | Non-responsive | $100K | 14mo | Interborough Express, AT&T cellular infra expansion | No contact found | N/A | +1 |
| 11 | Healthfirst | Non-responsive | $100K | 17mo | Hiring active | Latesh Nair, Security Head | 94 | 0 |
| 12 | Cleveland Clinic | Time-frame | $70K | 17mo | HIPAA tailwind | No contact found | N/A | +1 |
| 13 | Marsh | Non-responsive | $70K | 14mo | No specific trigger | Jeffrey Lund, Global CISO | 93 | 0 |
| 14 | Montefiore | Budget | $65K | 12mo | Healthcare, 12mo window re-opening | No contact found | N/A | +1 |
| 15 | XPO Inc | Non-responsive | $100K | 12mo | No specific trigger | No contact found | N/A | 0 |

## Drafts staged

| Draft | To | Email | Gmail ID |
|---|---|---|---|
| "IPG + Omnicom integration security overhead" | Samantha Mahan, CISO | samantha.mahan@interpublic.com | r4294536912893027848 |
| "First year in the DTCC CISO seat" | Laura Deaner, CISO | ldeaner@dtcc.com | r3713924335924147505 |
| "Your InfoRiskToday piece on microsegmentation" | Aaron Weismann, CISO | aweismann@mlh.org | r16566209673463522 |

## Flags for next run

- Inspire Medical: best trigger of the batch (active data governance RFP, Apr 2026). No CISO-level contact in ZoomInfo. Search with CIO or VP IT angle before next run.
- Hoag: strong ICP, no security contact found. Try searching parent entity or CIO track.
- MTA: critical infra deal. Find CISO or Deputy CISO before next run.
- Bucket 4 (MQL): HubSpot returned 0 MQL contacts with no deals. Owner ID mismatch may be the cause (corpus owner is 828577255, not 86806986). Investigate filter.

## Slack post

https://onyxia-workspace.slack.com/archives/C0AUB4DATP0/p1777249549377849
