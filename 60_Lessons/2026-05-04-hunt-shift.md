---
type: lesson
subtype: hunt-shift
date: 2026-05-04
shift: pre-vacation-stage-run
author: claude-hunt-agent
tags: [lesson, hunt]
---

# Hunt Shift Summary — 2026-05-04

Pre-vacation stage run. Miles departs 2026-05-05, returns 2026-05-11. Goal: 10-20 ICP-fit accounts staged, scored, ready to activate on return week.

---

## Strategy used

Primary: **Lookalike (Strategy A)** from closed-won corpus.

Seeds: WellStar Health System and Premera Blue Cross. Both ICP-qualified Tier 1 wins in healthcare. WellStar yielded hospital system lookalikes; Premera yielded health insurer lookalikes.

Rationale: Lookalike is the highest-yield strategy per the 2026-04-22 methodology (420 candidates, ~30 ICP-qualified). Manufacturing/defense gap filled via direct ZoomInfo company enrichment of known defense primes.

Secondary: **Scoops trigger (Strategy B)** — zero usable hits in the 30-day window. CISO-hire scoops (IT department, C-Level + VP, New Hire/Executive Move, 500-10K employees) returned 8 results, none matching ICP verticals. Confirmed: scoops remain a daily-scan tool, not a bulk hunt tool for this ICP.

Intent (Strategy C): Not attempted. Reserved for return week.

---

## Candidates scanned

| Stage | Count |
|---|---|
| Raw lookalike candidates | ~122 |
| Raw manufacturing direct-enriched | 10 |
| Raw banking direct-search | 30 |
| Scoops raw | 833 (from 30-day window, all management levels) |
| Post-exclusion | All 122 lookalike candidates passed exclusion check |
| Post-HubSpot dedupe | 15 clean (38 conflicts to Brad) |
| Scored ≥3 | 15 |
| Accounts staged | 15 |

---

## Score breakdown

- Score 5: 0
- Score 4: 9
- Score 3: 6

---

## Top 5 highest-conviction stages

1. **Gundersen Health System** (score 4) — 9K-employee non-profit hospital system in WI/MN/IA. HIPAA NPRM May 2026 finalization is the forcing event. Post-Bellin Health merger (2022) means security integration work is ongoing. Not in HubSpot. Multi-facility HIPAA surface across 7 hospitals, 65 clinics.

2. **Curtiss-Wright Corporation** (score 4) — 9,100-employee defense electronics company, NYSE: CW. CMMC Phase 2 November 2026 is the hard deadline. DoD prime + Tier 1 supplier with CUI-handling electronics. ITAR surface. SEC disclosure obligation. Not in HubSpot. Multiple compliance frameworks under one lean-ish security team for a $3.5B company.

3. **MVP Health Care** (score 4) — 1,700-employee NY-based not-for-profit health insurer, $3.4B revenue (very high revenue-to-headcount ratio). NYDFS Part 500 + HIPAA double-stack. Annual compliance certification window just closed (April 15). In HubSpot, no owner. NYC-proximate CISO = potential Baecco Dinner upgrade candidate.

4. **Ducommun Incorporated** (score 4) — 2,130-employee defense electronics manufacturer. NYSE: DCO. Two segments (Electronic Systems + Structural Systems) = distributed compliance inventory. CMMC Phase 2 + ITAR. In HubSpot, no owner. Air Force prime contractor per public filings. Pre-filing CMMC readiness is the immediate hook.

5. **BOK Financial** (score 4) — 5,034-employee multi-state bank holding company, $2.17B revenue. SEC registrant (BOKF). Operates TransFund payment network — additional breach surface. Multi-state footprint (OK/TX/NM/AR/CO/AZ/KS-MO). GLBA + OCC third-party risk guidance + SEC disclosure. In HubSpot, no owner.

---

## Dinner-cohort upgrade candidates

**MVP Health Care** (Schenectady, NY) — CISO likely NYC-metro based. Health insurer with NYDFS Part 500 surface. Fits the finserv/regulated-NY buyer profile for Baecco dinner (May 19). Miles should check CISO location on return and evaluate for dinner invite before sequence outreach.

No other staged accounts are NYC-HQ companies. Healthcare hospital systems (Gundersen, Atrium, Mercyhealth) are Midwest/South — not dinner-eligible.

---

## Verticals that came up empty or were thin

- **Critical infrastructure / utilities**: Atmos Energy and Puget Sound Energy were the top candidates — both Brad-owned in HubSpot. Summit Utilities lookalike returned only sub-ICP companies (<$50M revenue, <250 employees). This vertical produced zero clean candidates.

- **Defense/aerospace via ZoomInfo industry code**: `industryCodes: "Aerospace & Defense"` is not a valid ZoomInfo literal — returns unmatched warning and falls back to all employees in size range. Workaround used: manual company enrichment of known defense primes by name.

- **Scoops CISO hires (30 days)**: 8 hits, zero ICP-vertical matches. Strategy B is confirmed low-yield for bulk hunt. Use only for daily trigger-event scans.

- **`find_similar_companies` tool degradation**: Returned Internal Server Error for Centra Health and Bausch+Lomb seeds. WellStar and Premera worked. Summit Utilities matched a wrong (tiny) ZoomInfo record and returned useless sub-ICP lookalikes. Tool is sensitive to seed record quality.

---

## Territory conflicts (Brad Baldelli, owner 77002456)

38 companies across this hunt were Brad-owned. Notable:
- Entire BCBS state-plan family (BCBS Louisiana, Kansas, Minnesota, Idaho, NM, Alabama, Minnesota, Blue KC, Cambia, Medica, Independent Health, Regence parent)
- Major regional banks (Webster, East West, Old National, UMB, MidFirst, Western Alliance, BECU, EverBank, SouthState, Brown Brothers Harriman)
- Utilities (Atmos Energy, Puget Sound Energy)
- Some hospital systems (Bon Secours Health System, Children's Mercy, BCBS Arizona)

Brad's sweep has covered most of the obvious healthcare + finserv enterprise targets. Miles's white space is:
1. Companies not yet in HubSpot at all (Gundersen, Atrium Navicent, Curtiss-Wright, Kaman, EvergreenHealth, Zions Bank)
2. Companies in HubSpot with no owner (Mercyhealth, MVP Health Care, Wellmark, Moda Health, Concentra, BOK Financial, Ducommun, Columbia Banking System, Columbia Banking)

---

## Recommended next-hunt direction for return week (2026-05-11)

1. **Activate the 9 score-4 accounts first.** Contact enrichment + draft staging on the same day. Priority order: Curtiss-Wright (no HubSpot record, hot CMMC clock) > Gundersen (no HubSpot, multi-facility HIPAA) > MVP Health Care (in HubSpot no owner, NYDFS post-certification window) > BOK Financial (in HubSpot no owner, SEC registrant) > Ducommun (in HubSpot no owner, Air Force prime).

2. **MVP Health Care dinner evaluation.** Check CISO location before activating standard sequence. If NYC-metro, route to Baecco Dinner outreach first per the dinner playbook.

3. **Manufacturing vertical saturation sweep.** Defense prime CMMC window is the best timing signal for the next 6 months. Run a direct-name enrichment of the next tier of defense mid-market (Heico subsidiaries, DRS Technologies, API Technologies, Chelys, Miltec, others). ZoomInfo `companyDescription` search with "defense contractor" + employee/revenue filters.

4. **Intent signal check on return.** Run `search_intent` with "Cyber Risk Management" + CMMC-adjacent topics against the staged accounts to see which have active intent signals. Prioritize outreach to any account with signal score ≥70.

5. **Scoops daily trigger.** Resume daily CISO-hire scoops scan (06:45 trigger-event-hunt shift). Run for manufacturing vertical specifically — new CISO at a defense prime in the next 30 days is a 5-star trigger.

---

## Files written

- 15 staged account files at `~/ObsidianVault/10_Accounts/staged/`
- Signal log at `~/ObsidianVault/50_Intel/signal-log/2026-05-04-hunt.md`
- This summary at `~/ObsidianVault/60_Lessons/2026-05-04-hunt-shift.md`
