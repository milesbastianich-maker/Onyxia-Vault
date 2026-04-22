---
type: intel
subtype: hunt-log
hunt_pattern: scoops-trigger + direct-search
vertical: critical-infrastructure + defense-aerospace
date: 2026-04-22
tags: [intel, hunt, v/ci, v/defense]
---

# 2026-04-22 Critical-Infra + DIB Hunt

Second hunt of the day after mfg. Focused on new-CISO/CIO scoops in CI (utilities, transit) + DIB (aerospace, defense services).

## Filters

- Industries: electric utilities, water, natural gas, pipeline, transit, airports, rail, energy, aerospace, defense
- Scoop types: New Hire / Executive Move / Lateral Move
- Management levels: C Level Exec, VP Level Exec
- Department: Information Technology
- Window: 180 days (2025-10-22 onwards)
- Geography: United States
- Employee range: 500-10,000

## Raw yield

- CI scoops: 24 results
- DIB scoops: 4 results
- Direct CI search (energy/utilities ranked by revenue): 632 total, top 40 pulled

## Pipeline

- 28 scoop hits → top 6 enriched (FirstEnergy, V2X, CenterPoint, SJI, JTA, AeroVironment)
- 6 enriched → HubSpot dedupe → 3 Brad-owned (V2X, CenterPoint, JTA) + 3 clean (FirstEnergy, SJI, AeroVironment)
- 3 clean → 9 contacts pulled + 8 enriched (Aniket Majumder email pending)
- 3 accounts staged + 9 contact files + 8 Gmail drafts queued via hardened onyxia-drafter

## Staged accounts

| Company | Fit | Trigger | Primary champion | Email | Expected ARR |
|---|---|---|---|---|---|
| [[../../10_Accounts/FirstEnergy]] | 5 | Brian Harrell new CSO 2026-03-23 (30 days) | Brian Harrell | brian.harrell@firstenergy.com | $175K |
| [[../../10_Accounts/SJI]] | 5 | Bhupesh Arora new CIO 2025-12-31 (4 months) | Patrick Finnegan (20-yr coach — Bhupesh email pending) | pfinnegan@sjindustries.com | $85K |
| [[../../10_Accounts/AeroVironment]] | 5 | Aniket Majumder promoted CIO + CMMC Nov 10 | Jan Mast (Global Director Cybersecurity — role match) | mast@avinc.com | $95K |

## Territory conflicts (log for potential Brad DM)

- **V2X Inc** — Brad-owned (77002456). Mike Uster new CIO 2026-04-02 (20 days) — HOT scoop. Worth DMing Brad given precedent on Eric Secules/SMBC.
- **CenterPoint Energy** — Brad-owned. Bradley Krol new CTO 2025-12-11. Warm.
- **Jacksonville Transportation Authority** — Brad-owned. James Ventimiglia promoted CIO 2026-02-28.

## Champion highlights

- **Jan Mast (AeroVironment)** — Global Director Cybersecurity. Literally the seat Onyxia serves. 3 years in + CMMC urgency.
- **Brian Harrell (FirstEnergy)** — 30 days in as CSO, high-profile ex-CISA + ex-Avangrid, peer-to-Sivan profile.
- **Sarah Brooks (SJI)** — Director Office of the CIO, reports directly to the new CIO Bhupesh. Entry angle.

## Gmail drafts queued

Via `onyxia-drafter` sub-agent with all gates (Level 3+ personalization, avoid-ai-writing, em-dash zero, Register-B grep, 8-criteria rubric). 8 drafts:

1. Brian Harrell / FirstEnergy
2. M. Scott Hipkins / FirstEnergy
3. Jason McCormick / FirstEnergy
4. Patrick Finnegan / SJI
5. Sarah Brooks / SJI
6. Michael Bizzoco / SJI
7. Jan Mast / AeroVironment
8. Scott Tasem / AeroVironment

Aniket Majumder / AeroVironment = email pending, not drafted this session.

## Next action

1. Review 8 drafts in Gmail drafts folder — Miles ✅ or ✏️.
2. Consider Brad DM for V2X (Mike Uster 20-days-new-CIO is the strongest of the conflict scoops).
3. Re-enrich Bhupesh Arora + Aniket Majumder in 30 days.
4. Touch-tracker rows for each send once drafts are approved.

## Cross-references

- [[../verticals/critical-infrastructure]]
- [[../verticals/defense-aerospace]]
- [[../icp]]
- [[../../40_Plays/sequences/critical-infrastructure/ciso-first-touch]]
- [[../../40_Plays/sequences/manufacturing/ciso-first-touch]] — CMMC variant for AeroVironment
