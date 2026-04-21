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
next_action: re-engage after MNDA forward, confirm MHI-US security owner
next_action_date: 2026-04-25
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
Single-threaded. Target 2-3 per multi-thread rule.
- _TBD primary contact who signed MNDA_ — pull from HubSpot associations
- MHI-US CISO / VP Security — _unknown, research needed_
- CIO / CFO at MHI-US sub — _unknown, research needed_

## Deal
- Amount: $75,000
- HubSpot stage: Appointment Scheduled (per backfill)
- HubSpot ID: _unknown - research needed_
- Close target: _unknown - research needed_

## Timeline
- 2025-04-01: Eisaku Ito becomes new CEO of Mitsubishi Heavy Industries
- 2026-04-20: Sivan's signed MNDA forwarded (first send was missed by the prospect)
- 2026-04-21: stub created from HubSpot backfill
- 2026-04-22: vault densification; no HubSpot access this session to pull the MNDA counterparty name

## Next
- [ ] Pull HubSpot: deal ID, owner, dealstage, associated contacts (the MNDA signer), last activity
- [ ] ZoomInfo enrich MHI-US CISO / CIO / security leaders
- [ ] Re-engage the primary contact after MNDA forward — 5 day waiting period, then pattern-break per [[../50_Intel/playbook/closed-lost-patterns]]
- [ ] Multi-thread to at least one additional contact within 30 days of first meeting

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
