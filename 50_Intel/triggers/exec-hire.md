---
type: intel
subtype: trigger
trigger: exec-hire
source: closed-won corpus + ZoomInfo positionStartDate patterns
created: 2026-04-22
tags: [intel]
---

# Exec Hire

New CISO or VP Security in the 90-180 day window. Strategy-setting period. Budget for net-new tools opens. Second-highest-converting trigger per [[../icp]]. Anchors the [[../../40_Plays/sivan-peer-intro]].

## Detection pattern

- ZoomInfo `positionStartDateMin` filter set to 180 days ago, job title includes CISO / Chief Information Security / VP Security / Head of Security.
- ZoomInfo Scoops auto-feed for "new hire" trigger events on Tier 1 vertical accounts.
- LinkedIn announcement posts (new CISO public announcements).
- Company press releases, usually filed within 2-4 weeks of start date.
- SEC 8-K Item 5.02 (departure / appointment of officers) for public companies.

## Response timing

- **Days 0-30 of new hire:** they are meeting everyone internally. Low reply rate. Acceptable to send opener but expect nurture.
- **Days 30-120:** sweet spot. They are setting the strategy, asking "what do I need?" Peer-intro play converts best here.
- **Days 120-180:** still reachable. Strategy is forming into initiatives. Budget conversations happening.
- **Day 180+:** window closing. Strategy is set; they are executing. Budget conversations end-of-fiscal.

## Historical win examples

- **Radiant Logic ($165K, 36 days to close).** Peer/referral-driven. Likely routed through Sivan's network during exec-hire or strategy-setting window.
- **OCTA ($60K, 71 days).** Network-driven + fast cycle.
- **Premera Blue Cross ($170K, 169 days).** Mid-cycle with a champion in place.
- **Centra Health ($270K, 137 days).** Inbound during a hiring cycle on their side.

## Historical loss examples

Champion-job-change was the failure mode in 3 losses (Drake Software, PointHR, Ted Baker). That's the inverse trigger: your champion leaves mid-cycle. Mitigation: multi-thread from day one per [[../playbook/closed-lost-patterns]]. See [[../methodology/objections]] #9.

## Active examples

- [[../../10_Accounts/First Horizon Bank]] — [[Leilani Farol]] started Feb 2026. Day ~70 as of 2026-04-21. Sweet spot.
- [[../../10_Accounts/OCC]] — [[Jessica Kruse]] started March 2026. Day ~30-60. Sweet spot beginning.
- [[../../10_Accounts/FMOL Health]] — [[Britani Tullier]] started July 2025. Past sweet spot but still inside year-one strategy window.
- [[../../10_Accounts/Mitsubishi Heavy]] — Takao Tsukui referenced as a new CISO angle.

## Template reference

Use [[../../90_Templates/tpl-ciso-cold]] (new-CISO variant). Core anchor from [[../../40_Plays/sivan-peer-intro]]:
> Congrats on the [role] at [company]. [vertical-specific transition pain].
> Sivan Tehila, our CEO and former CISO, built Onyxia specifically for [this moment / this problem].
> Curious if that's on your radar as you're setting strategy?

## Language that lands

- "First 90 days is for listening. After that, the board wants a plan."
- "Every new CISO I talk to says 'I don't have one source of truth on the program.' That's the gap we fill."
- "Sivan built Onyxia because she had this exact problem coming in as CISO. 20 minutes, peer to peer."

## Cross-references

- [[../icp]]
- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../personas/ciso]]
- [[../personas/vp-security]]
- [[../personas/grc-director]]
- [[../methodology/objections]]
- [[../verticals/financial-services]]
- [[../verticals/healthcare]]
- [[../verticals/manufacturing]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../40_Plays/hunt/trigger-event-hunt]]
- [[../../90_Templates/tpl-ciso-cold]]
