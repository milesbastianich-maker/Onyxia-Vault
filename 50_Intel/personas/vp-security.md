---
type: intel
subtype: persona
persona: vpsec
source: closed-won + closed-lost corpus + ZoomInfo persona patterns
created: 2026-04-22
tags: [intel, p/vpsec]
---

# VP Security

Common title in mid-market + in larger orgs where the CISO is more executive-facing. Often the operational owner of the security program. Buyer authority varies: in some shops functions as CISO, in others reports to CISO/CIO. Treat as primary buyer at companies that do not have a named CISO on record, and as champion where a CISO exists above them. See [[../playbook/closed-won-patterns]].

## What they actually do day-to-day

- Run the security operations program (SOC, IAM, AppSec, VM, DFIR coordination).
- Own vendor evaluations. Usually the "let's see it live" human.
- Produce the monthly report that rolls up to the CISO or board.
- Coordinate with IT, DevOps, Platform teams. Political surface is wide.

## Core pains (in their language)

- "I'm the one assembling the slide the CISO presents."
- "My engineers spend more time in spreadsheets than in the tools."
- "I can answer 'are we covered' for some assets. Not for all of them."
- "If the board asks me to benchmark against industry, I fake it."

## What they DON'T want to hear

- "Your CISO needs to see this." They are quite possibly the de facto CISO. Don't skip past them.
- Rip-and-replace. They chose the current stack. Replacing it is an admission they were wrong.
- Marketing language. VP Sec is often an ex-engineer. Peer-tone always.

## Language that lands

- "You're the one assembling the board slide. Onyxia auto-generates it." (maps to [[../product/features]] pillar 4)
- "Your Stack Map auto-renders on integration. You see gaps in 30 minutes, not 30 days."
- Benchmarking hook: "Compare your program maturity to average SLA in your industry." ([[../product/features]] pillar 5).
- Nexa query demo: "Ask your stack 'how many users logged in this week' and get the answer in one sentence." ([[../product/features]] Nexa examples from Brad's training doc).

## Objections you will hear

- "We already have SIEM + EDR + Identity tools." Reframe: Onyxia pulls from those via API, does not replace them. See [[../methodology/objections]] #1.
- "We need CISO sign-off." Good. Ask to co-brief. Multi-thread immediately.
- "Dashboard fatigue." See [[../methodology/objections]] #8. Anchor on Hashal Mehta quote from [[../product/quotes]].
- "Integration lift." Real concern. Counter: "Minutes to connect via API. Premera POC integrated in 2-4 weeks." See [[../product/features]] integration catalog.

## CTA preferences

- Live Stack Map render against their known tools.
- Nexa query demo against sample data.
- POC scoping call (they scope POCs for CISO sign-off).

## Watch signals

- Job change within 180 days → [[../triggers/exec-hire]].
- Company just closed M&A (they inherit the acquired stack) → [[../triggers/ma-activity]].
- New framework requirement (CMMC, ISO, SOC 2) → [[../triggers/sec-cyber-rule]].

## Accounts where VP Security is the entry point

Vault-thin on specifically-titled VP Security contacts today. Most current Tier 1 pipeline leads with CISO or Head/MD. Expand enumeration on the next [[../../40_Plays/hunt/icp-lookalike-hunt]] run by adding VP Security title filters to ZoomInfo query template.

## Cross-references

- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../product/features]]
- [[../product/quotes]]
- [[../methodology/objections]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../40_Plays/hunt/icp-lookalike-hunt]]
- [[../../90_Templates/tpl-vpsec-cold]]
