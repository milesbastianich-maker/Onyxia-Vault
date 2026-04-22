---
type: account
company: Mitsubishi Heavy Industries
domain: mhi.com
vertical: mfg
account_tier: 1
hubspot_id: _unknown - research needed_
arr_target: 75000
stage: scoping
status: active
created: 2026-04-21
last_touch: 2026-04-20
next_action: REVIEW Lucas Parker's MNDA (sent 2026-04-14) — he bumped Miles 2026-04-20 asking for review
next_action_date: 2026-04-23
blocker: miles-review-of-mhia-mnda
metrics: 
economic_buyer: _unknown - research needed_
champion: _unknown - research needed_
paper_process: MNDA signed (Sivan's MNDA forwarded 2026-04-20)
tags: [account, "#active", "#v/mfg", "#stage/scoping"]
---

# Mitsubishi Heavy

## Why they'd buy
Global industrial manufacturer. Japan HQ, major US operations (MHI America). Aerospace, power systems, commercial aviation, defense. Multi-jurisdiction compliance surface: ITAR + CMMC for US defense contracts + Japan/EU/global data residency rules. New CEO Eisaku Ito took office 2025-04-01 — one-year-in window. MNDA already signed with Sivan, which means prior engagement exists.

## Fit
Tier 1 per [[../50_Intel/icp]]: manufacturing vertical, aerospace/defense, multi-framework compliance (ITAR + CMMC + NIST). Massive employee count globally (well above 10K). Above the upper bound of Tier 1 size range but the compliance surface + [[../50_Intel/playbook/closed-won-patterns]] aerospace pattern (Metalex CMMC pattern, Port Authority critical infra) say this matches. Score: 4.

## MEDDPICC
- **Metrics** — _unknown - research needed_. Candidate: CMMC audit prep hours, DIB compliance gap count, multi-jurisdiction reporting burden.
- **Economic buyer** — _unknown - research needed_. Likely CIO or CFO at MHI-US entity. Global HQ approvals would slow everything down; scope to US sub.
- **Decision criteria** — _unknown - research needed_. Hypothesis: CMMC readiness, ITAR posture, consolidated reporting across business units.
- **Decision process** — _unknown - research needed_. Japanese parent decision-making is consensus-heavy (nemawashi); US sub can move faster on its own budget.
- **Paper process** — MNDA signed. Security review + procurement + legal still to come. Expect 90-180 day cycle minimum.
- **Identified pain** — _unknown - research needed_. Hypothesis: fragmented compliance reporting across MHI-US business units (aerospace, power, aviation).
- **Champion** — _unknown - research needed_. **First email missed; Sivan's MNDA forwarded on re-send 2026-04-20. Champion is implied but not named in vault.**
- **Competition** — _unknown - research needed_. Likely incumbent SIEM/EDR + "do nothing" per [[../50_Intel/playbook/closed-lost-patterns]].

## Threads
Single-threaded today. Target 2-3 per multi-thread rule.
- **Rank 1 (confirmed, active):** Lucas Parker — Head of Security, Mitsubishi Heavy Industries America. Email: lucas.parker@mhia.com. cc'd Brad + Sivan on follow-ups. He sent the MNDA 2026-04-14, bumped Miles for review 2026-04-20. ⚠️ Waiting on Miles.
- MHI-US CIO — unknown, research needed
- MHI-US CFO at sub entity — unknown, research needed

## Deal
- Amount: $75,000
- HubSpot stage: Appointment Scheduled (per backfill)
- HubSpot ID: _unknown - research needed_
- Close target: _unknown - research needed_

## Timeline
- 2025-04-01: Eisaku Ito becomes new CEO of Mitsubishi Heavy Industries
- 2026-04-09: Miles sent initial follow-up + next-steps email to Lucas Parker (lucas.parker@mhia.com), cc'd Brad + Sivan. Proposed 3 slots for technical deep-dive with Sivan + Vadim (Wed 4/22 10am ET, Thu 4/23 11:30am ET, Mon 4/28 TBD).
- 2026-04-14: Miles bumped Lucas. Lucas replied same day: "Attached is our MNDA. I'll get back to you on next steps after this is ironed out." **Lucas sent HIS MNDA. Ball in Miles's court to review.**
- 2026-04-20: Miles bumped casually ("sunburnt in FL, hope you had a great weekend"). Lucas replied 23 min later: **"Have you reviewed the Mutual NDA from the prior email?"** Clear signal — Lucas is waiting on Miles.
- 2026-04-20: Miles forwarded Sivan's MNDA back to Lucas (referenced in prior account notes, not seen in this thread pull).
- 2026-04-22 (today): NDA review STILL not acknowledged back to Lucas. This is the active blocker. Primary contact: Lucas Parker, Head of Security, Mitsubishi Heavy Industries America.
- 2026-04-22: vault densification; HubSpot deal ID still unknown this session.

## Next
- [ ] **BLOCKER — Miles to review Lucas's MNDA** (sent 2026-04-14, Lucas bumped 2026-04-20). Either (a) redline and send back, (b) have Onyxia legal review, or (c) confirm which MNDA (Lucas's or Sivan's) is the one moving forward. Action needed within 24-48h to avoid thread going cold.
- [ ] Reply to Lucas acknowledging NDA receipt + ETA on review even if full review is not done today.
- [ ] Pull HubSpot: deal ID, owner, dealstage, associated contacts, last activity (requires a Mitsubishi Heavy deal search).
- [ ] ZoomInfo enrich MHI-US CIO / CFO / security leaders for multi-thread.
- [ ] Multi-thread to at least one additional contact within 30 days of first meeting.

## Intel
Japan HQ (Tokyo). US sub: Mitsubishi Heavy Industries America. New CEO Eisaku Ito since 2025-04-01 (30-year MHI veteran). Business units: aerospace + defense + power systems + commercial aviation + compressor systems. CMMC-relevant defense work. Global employee count well above 10K.

## Pattern match
Closest aerospace/defense mfg win analog: none directly in [[../50_Intel/playbook/closed-won-patterns]] corpus — Millennium Print Pokemon ($45K, print mfg) and Bausch + Lomb ($58.5K, pharma/optics) are the closest mfg pattern matches. Critical infrastructure wins (Port Authority $135K, Summit Utilities $80K) apply the compliance-surface pattern. Multi-site industrial = slow cycle but big ARR when it lands.

## Risk flags
- Global Japanese parent — if they route decisions to Tokyo, cycle gets much longer.
- Single-threaded.
- Already missed the first send — re-engagement requires a reason, not a ping.

## Links
- [[../50_Intel/verticals/mfg]]
- [[../50_Intel/personas/ciso]]
- [[../50_Intel/triggers/cmmc-deadline]]
- [[../50_Intel/triggers/new-ceo]]
- [[../50_Intel/playbook/closed-won-patterns]]
- [[../50_Intel/playbook/closed-lost-patterns]]
- [[../50_Intel/icp]]
