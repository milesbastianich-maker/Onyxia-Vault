---
type: intel
subtype: signal-log
play: reactivation-sweep
run_date: 2026-05-04
run_time: "20:00 ET"
tags: [intel, play]
---

# Reactivation Sweep — 2026-05-04

## Run summary

| Metric | Count |
|---|---|
| Total closed-lost corpus | 114 |
| Bucket 1 (non-responsive) mined | 68 |
| Bucket 2 (budget/time) mined | 25 |
| Bucket 3 (champion left) mined | 5 |
| Bucket 4 (old MQL, no deal) | 0 |
| Eligible after exclusions + territory check | ~35 |
| Enriched via ZoomInfo | 14 contacts across 12 accounts |
| Passed hard gate (accuracy ≥85) | 10 accounts |
| Drafts staged in Gmail | 3 |

## Exclusions applied

- Israeli entities: Coca-Cola Israel, WIX, AppsFlyer, Mesh Payments
- Security vendors: Rubrik, SolarWinds, Broadcom, Trustwave
- BigLaw (no warm path): Sullivan & Cromwell, Milbank, Lowenstein Sandler
- Sub-minimum deal size / low ICP: Ted Baker, PointHR, Drake Software, Richline Group, Sportradar
- Hard gate failures (ZI accuracy 0.0 or opted out): Troy Wilkinson/IPG, Paul Kreft/XPO, Alex Green/Delta Dental, Eric Sporre/Caterpillar
- Champions confirmed departed with no replacement found: Wayne Hilt/Huntington (now Truist), Nick Vigier/Oscar Health (now Amplifier Security), Peeyush Patel/XPO (now NextEra — see Rank 2 below)

## Champion-movement findings (action items)

| Contact | Left | Went to | Action |
|---|---|---|---|
| Peeyush Patel | XPO CISO | NextEra Energy CISO (May 2025) | Net-new account — draft staged, create HubSpot record |
| Vugar Zeynalov | Cleveland Clinic CISO | Community Health Systems VP/CIO (Nov 2024) | Net-new account opportunity — warm, above ICP ceiling but worth a cold note |
| Wayne Hilt | Huntington CISO | HCE Advisors / Truist (Oct 2024) | No CISO replacement found at Huntington; hold |
| Nick Vigier | Oscar Health CISO | Amplifier Security (approx Q1 2026) | No replacement CISO found at Oscar; hold |
| Troy Wilkinson | IPG CISO | Unknown — ZI 0.0, likely Omnicom merger cut | Manual LinkedIn check before next run |

## Top 15 ranked candidates

| Rank | Account | Bucket | ACV | Dormant | Trigger | Contact | Accuracy | Score |
|---|---|---|---|---|---|---|---|---|
| 1 | Main Line Health | Budget | $100K | 20mo | CISO published InfoRiskToday (Mar 2026): 60K devices, 24K microseg rules | Aaron Weismann, CISO | 95 | 7 |
| 2 | NextEra Energy | Bucket 3 (new acct) | n/a | n/a | Former XPO CISO now 12mo into NextEra CISO role, strategy window | Peeyush Patel, CISO | 98 | 7 |
| 3 | QBE Insurance | Non-responsive | $100K | 12mo | C-Suite hiring surge; insurer credibility angle (sells cyber, must model own program) | Jacob Thampi, Div. ISO | 98 | 6 |
| 4 | MTA | Non-responsive | $100K | 15mo | Penn Station Access + Interborough Express = major OT/IT expansion | Tariq Habib CISO (89) + Nitesh Vora Dir IT Security (98) | 98 | 6 |
| 5 | Healthfirst | Non-responsive | $100K | 18mo | Hiring Enterprise AI Architect (Feb 2026); AI/data security conversation | G.T. Sweeney CIO (98) + Latesh Nair Head Security (87) | 98 | 5 |
| 6 | Montefiore | Budget | $65K | 12mo | New CISO (joined March 2024), new FY budget cycle; contact modified 2026-05-02 | Mark Ballister, VP CISO | 92 | 5 |
| 7 | Digital Realty | Time frame | $70K | 20mo | 3-contact multi-thread; critical infra (global data centers) | Donald Freese, SVP Global CISO | 94 | 5 |
| 8 | Cleveland Clinic | Time frame | $70K | 18mo | Vugar Zeynalov left (Nov 2024, now CIO at CHS); Kevin Tambascio still active as Director | Kevin Tambascio, Dir Cybersecurity | 90 | 4 |
| 9 | Community Health Systems | Bucket 3 (new acct) | n/a | n/a | Vugar Zeynalov (ex-CC CISO) now VP/CIO; warm contact; above ICP headcount ceiling | Vugar Zeynalov, VP/CIO | 98 | 4 |
| 10 | Marsh | Non-responsive | $70K | 15mo | New title (Global CISO Marsh Business vs. Global CISO at Marsh) suggests restructuring | Daniel Bowden, Global CISO | 94 | 3 |
| 11 | IPG | Non-responsive | $150K | 15mo | Omnicom merger; 8,200 joint layoffs in 2025; security integration spend likely | Troy Wilkinson — ZI 0.0 | FAIL | 3 |
| 12 | Huntington Bank | Non-responsive | $100K | 16mo | New CRO Senthil Kumar (from BNY, March 2026); CISO vacancy since Oct 2024 | No CISO found | FAIL | 2 |
| 13 | Delta Dental | Time frame | $70K | 15mo | No trigger; Alex Green ZI 0.0 | Alex Green — ZI 0.0 | FAIL | 2 |
| 14 | Oscar Health | Non-responsive | $100K | 15mo | Nick Vigier left (now Amplifier Security); no replacement found | No CISO found | FAIL | 2 |
| 15 | Inspire Medical Systems | Non-responsive | $100K | 15mo | John Verplank not enriched this run; data governance signal from Apr 27 run still relevant | John Verplank, Sr Dir Info Security | NOT ENRICHED | 2 |

## Drafts staged

| Draft | To | Email | ZI Accuracy | Gmail Draft ID |
|---|---|---|---|---|
| "Your InfoRiskToday piece — 60K devices, 24K rules" | Aaron Weismann, CISO, Main Line Health | aweismann@mlh.org | 95 | r2227795213185992973 |
| "NextEra CISO — 12 months in" | Peeyush Patel, CISO, NextEra Energy | peeyush.patel@nexteraenergy.com | 98 | r4005885507286357392 |
| "QBE's own cyber program" | Jacob Thampi, Divisional ISO, QBE Insurance | jacob.thampi@us.qbe.com | 98 | r4204680070903801160 |

## Hard gate summary

Enriched 14 contacts. 10 passed (≥85 accuracy). 4 failed (ZI 0.0 or opt-out). Caterpillar Eric Sporre opted out of ZoomInfo; secondary contact (Carson Cole) resolved to wrong person (Material Handler, data error in HubSpot).

## Flags for next run

- **Aaron Weismann duplicate**: April 27 sweep also staged a draft to Weismann on the same InfoRiskToday trigger. Verify whether that draft was sent before approving this one. If sent, skip Weismann this week.
- **IPG**: M&A trigger is the strongest un-acted opportunity in the corpus ($150K). Need manual LinkedIn/ZoomInfo lookup for the current security leader post-merger. Worth 15 minutes of manual work.
- **Inspire Medical**: Enrich John Verplank before next run. Data governance RFP signal from April run still live.
- **Huntington**: CISO seat vacant since Oct 2024. New CRO is warm adjacent contact. Consider outreach to Senthil Kumar (CRO) if no CISO is named by next sweep.
- **Caterpillar**: Eric Sporre is ZI opt-out. Carson Cole HubSpot email (alma.cole@cat.com) resolves to wrong person. Fix email before any outreach.
- **NextEra + CHS**: Two net-new account opportunities discovered from champion tracking. Create HubSpot records for both before drafts are approved and sent.
- **Bucket 4**: HubSpot returned 0 MQL contacts with no deals. Filter issue confirmed (owner ID mismatch). Investigate manually.
- **Montefiore**: Mark Ballister contact modified 2026-05-02. Check if actively in play before approving any Montefiore outreach.

## Slack post

https://onyxia-workspace.slack.com/archives/C0AUB4DATP0/p1777853762579829
