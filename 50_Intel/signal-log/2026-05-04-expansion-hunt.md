---
type: intel
subtype: hunt-log
date: 2026-05-04
pattern: vertical-saturation
vertical_primary: insurance-pc-specialty
vertical_secondary: higher-education, life-sciences
candidates_raw: 131
candidates_post_exclusion: 131
candidates_post_hubspot_dedupe: 24
candidates_scored_geq_3: 8
accounts_staged: 8
contacts_enriched: 8
territory_conflicts: 18
tags: [intel, signal-log]
---

# Hunt Log — 2026-05-04 Expansion Hunt

Three-vertical expansion covering P&C/reinsurance/specialty insurance, higher education, and life sciences/pharma/biotech. Separate from the morning healthcare/banking/defense run.

## Verticals targeted

1. P&C / Specialty Insurance carriers (target: 3 contacts)
2. Higher Education — R1/R2 universities and academic medical centers (target: 2 contacts)
3. Life Sciences / Pharma / Biotech (target: 3 contacts)

## Strategy per vertical

All three verticals used **vertical-saturation** (direct search_companies + search_contacts by industry/size filter) as primary strategy, with **trigger-event enrichment** via search_scoops to surface CISO hires and M&A. Lookalike not used — no clean closed-won seeds in these three verticals per methodology.

## HubSpot territory conflicts

Total conflicts (Brad owner 77002456): 18 named companies eliminated

P&C Insurance conflicts: FM Global, The Hanover Insurance Group, TruStage, Kemper, Shelter Insurance, Federated Insurance, Ryan Specialty, Amica Mutual Insurance
Life Sciences conflicts: Organon, Biogen, Indivior, Alnylam Pharmaceuticals, Amneal Pharmaceuticals, Incyte, Neurocrine Biosciences
Higher Ed conflicts: University of Notre Dame, University of Rochester, Princeton University, Texas A&M University, Drexel University, Villanova University

## Staged accounts

| Company | Vertical | Score | HubSpot status | Trigger type |
|---|---|---|---|---|
| CSAA Insurance Group | P&C Insurance | 4 | Not in HubSpot | Regulation (NAIC Model Law CA) |
| Erie Indemnity | P&C Insurance | 4 | Not in HubSpot | 8-K / SEC Item 1.05 + board hire |
| Core Specialty | P&C Specialty | 4 | Not in HubSpot | Regulation (NAIC Model Law NJ) |
| Loyola University Chicago | Higher Education | 4 | In HubSpot, no owner | CISO hire (May 2024) + GLBA Safeguards |
| Augusta University | Higher Education | 4 | Not in HubSpot | Regulation (GLBA + HIPAA dual-framework) |
| Lantheus | Life Sciences | 4 | Not in HubSpot | CISO hire (Jan 2024) + 21 CFR + SEC Item 1.05 |
| Elanco | Life Sciences | 4 | Not in HubSpot | GxP / 21 CFR Part 11 + SEC Item 1.05 |
| Sarepta Therapeutics | Life Sciences | 4 | Not in HubSpot | 21 CFR gene therapy + SEC Item 1.05 + IP protection |

## Contacts enriched

| Contact | Company | Title | Tier | Email | Accuracy | Note |
|---|---|---|---|---|---|---|
| Joseph Kamau | CSAA Insurance Group | SVP & CISO | Tier 1 | joseph.kamau@csaa.com | 98 | Clean |
| Jamie Neumaier | Erie Indemnity | VP Information Security | Tier 1 | jamie.neumaier@erieinsurance.com | 99 | Clean |
| Mary Kotch | Core Specialty | EVP CTO/CISO | Tier 1 | mary.kotch@corespecialty.com | 98 | Clean |
| James Pardonek | Loyola University Chicago | Director InfoSec & CISO | Tier 3 | jpardonek@luc.edu | 98 | Clean |
| Heather Roszkowski | Augusta University | VP & CISO | Tier 1 | hroszkowski@augusta.edu | 99 | Clean |
| Robert Sherman | Lantheus | CISO | Tier 1 | shermanr@lantheus.com | 98 | Clean |
| Jody Woenker | Elanco | CSO | Tier 1 | jody.woenker@elancoah.com | 99 | Clean |
| Mary Ballard | Sarepta Therapeutics | Sr Director & CISO | Tier 1 | mballard@sarepta.com | 84 | CAUTION: valid date 2023-08-14; verify before activation |

## Cost notes

- ZoomInfo company enrichments: 12 (Cincinnati Insurance, CSAA, Erie Indemnity, Loyola, Ohio State, Lantheus, Elanco, Sarepta, Amica, Core Specialty, Augusta, UoC)
- ZoomInfo contact enrichments: 9 (Kamau, Neumaier, Pardonek, Biscay, Sherman, Woenker, Ballard, Kotch, Roszkowski)
- ZoomInfo search_contacts: 3 calls (higher-ed, insurance, pharma)
- ZoomInfo search_companies: 3 calls
- ZoomInfo search_scoops: 3 calls
- HubSpot company reads: 8 calls (read-only throughout)
- Total ZoomInfo enrichment credits burned: ~21 (12 company + 9 contact)

## Accounts eliminated (size out of ICP)

- Ohio State University: 49,325 employees, $8.7B revenue — score 2, rejected
- University of Cincinnati: 15,000 employees, $1.68B revenue — score 2, rejected
- University of South Carolina: 15,000 employees — score 2, rejected
- Cincinnati Insurance: $12.6B revenue (>$5B ICP ceiling) — score 2, rejected
