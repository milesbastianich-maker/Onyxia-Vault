---
type: intel
subtype: persona
persona: ciso
source: closed-won + closed-lost corpus + SEC disclosures + NYDFS governance changes
created: 2026-04-22
tags: [intel, p/ciso]
---

# CISO

Primary buyer for Onyxia. Technical champion and frequently the Economic Buyer in mid-market. In enterprise, CISO is champion, EB is CFO/CIO/GC. SEC rules and NYDFS Part 500 put personal liability on the CISO for disclosure and board reporting. That is the wedge. See [[../playbook/closed-won-patterns]].

## What they actually do day-to-day

- Own security strategy + budget defense to CFO/board.
- Answer to board on program maturity (now quarterly minimum at NYDFS shops; see [[../industry/regulatory-calendar]]).
- Sign off on incident materiality calls (SEC Item 1.05 filers).
- Manage a team drowning in tool telemetry. Typical report-cycle burn: 40-160 analyst hours/month on manual aggregation per [[../product/quotes]].

## Core pains (in their language)

- "I have 30+ tools and no single picture."
- "I spend half my week building a board deck, not running security."
- "The board keeps asking for a number and I don't have a defensible one."
- "If we have an incident, the 8-K narrative has to be airtight. It isn't."
- "I don't have the headcount to keep up with the new rules."

## What they DON'T want to hear

- Another dashboard. See [[../methodology/objections]] #8.
- A replacement for their SIEM / EDR / IAM. See [[../methodology/objections]] #1.
- A rip-and-replace proposal.
- Pricing without scope. See [[../methodology/objections]] #4.
- AI buzzwords with no substance.

## Language that lands with CISOs

- Peer framing, not vendor framing. "Sivan Tehila, our CEO, was a CISO before founding Onyxia." Reference [[../../40_Plays/sivan-peer-intro]].
- Time-saved in analyst hours ("160 hours a month" is the verbatim number from [[../product/quotes]]).
- Board-ready language. One-click report, framework overlay.
- Specific compliance anchor (HIPAA, SEC 1.05, NYDFS Part 500, CMMC Level 2, NIST CSF 2.0 Govern).

## Objections you will hear

Ordered by frequency in the 113-loss corpus:
1. Silence (60% of losses). Mitigation: multi-thread. See [[../methodology/objections]] #10.
2. "Time frame isn't right." Decode: no economic buyer, no forcing event. See [[../methodology/objections]] #2.
3. "We already have X tool." Reframe: we are the layer above. See [[../methodology/objections]] #1.
4. "Budget is frozen." Decode: EB not named. See [[../methodology/objections]] #3.
5. "Send pricing." Redirect to scoping. See [[../methodology/objections]] #4.
6. Champion job change. 3 deals died this way. See [[../methodology/objections]] #9 tie-in + [[../playbook/closed-lost-patterns]].

## CTA preferences (what they'll say yes to)

- 20-minute peer call with Sivan. Highest converter. No slides.
- 15-minute scoping call with clear agenda + exit option.
- 2-page business justification doc sent in advance of a board conversation.
- Peer-reference intro (Centra, WellStar, Premera contacts reachable via Karen/CS).

What they usually DECLINE:
- "Demo" requests (demo fatigue).
- 60-minute exploratory calls with no agenda.
- "Innovation Day" invites. They ignore these.

## Watch signals

- Position start date within last 180 days → [[../triggers/exec-hire]].
- Their company just filed an 8-K Item 1.05 → [[../triggers/breach-event]].
- Their company just paid a settlement → [[../triggers/settlement-event]].
- Their annual 10-K mentions cyber as a top risk factor → [[../triggers/10k-8k-filing]].
- Their company just closed M&A → [[../triggers/ma-activity]].

## Accounts where CISO is champion

- [[../../10_Accounts/Medusind]] — [[Jigar Shah]] — post-breach rebuild mode.
- [[../../10_Accounts/First Horizon Bank]] — [[Leilani Farol]] — brand-new, GRC-to-CISO path.
- [[../../10_Accounts/FMOL Health]] — [[Britani Tullier]] — multi-facility hospital.
- [[../../10_Accounts/Mitsubishi Heavy]] — Takao Tsukui (referenced) — global manufacturer.

## Cross-references

- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../product/positioning]]
- [[../product/quotes]]
- [[../methodology/objections]]
- [[../methodology/measurement-log]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../40_Plays/reply-intent-parser]]
- [[../../90_Templates/tpl-ciso-cold]]
