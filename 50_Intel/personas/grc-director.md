---
type: intel
subtype: persona
persona: grc
source: closed-won + closed-lost corpus + NYDFS governance + HIPAA risk analysis
created: 2026-04-22
tags: [intel, p/grc]
---

# GRC Director

Governance, Risk, Compliance lead. Reports to CISO or CIO. Lives in framework mappings, audit prep, policy exceptions, and vendor risk. High coach value. Frequently the actual daily user of Onyxia. GRC is where the NYDFS Part 500 annual certification actually gets produced. See [[../playbook/closed-won-patterns]].

## What they actually do day-to-day

- Map controls to frameworks (HIPAA, HITRUST, SOC 2, PCI, NIST CSF, ISO 27001, CMMC).
- Respond to customer + auditor + regulator questionnaires.
- Own the risk register and exception process.
- Coordinate third-party / vendor risk assessments.
- Prepare the cyber section of the annual board + audit committee pack.

## Core pains (in their language)

- "We recertify against four frameworks a year. Each one is a spreadsheet nightmare."
- "My evidence collection burns two weeks every quarter."
- "I can't tell the auditor we are 'covered' because I can't actually show coverage."
- "Vendor risk is a wall of PDFs."

## What they DON'T want to hear

- "Replace your GRC tool." Most GRC teams already bought Archer / ServiceNow IRM / OneTrust. See [[../methodology/objections]] #1.
- Pricing without scope. See [[../methodology/objections]] #4.
- "Another dashboard." See [[../methodology/objections]] #8.

## Language that lands with GRC directors

- "One-click framework overlay." That's a direct [[../product/features]] pillar 7 hook.
- "We pull from the stack you already have. Not another data entry job."
- Specific framework anchor: HIPAA Security Rule NPRM asset-inventory mandate, NYDFS Part 500 CISO-to-board written report, CMMC Level 2 scoring evidence.
- "Your auditor sees the same view you do."

## Objections you will hear

- "We already use [Archer / OneTrust / ServiceNow IRM]." Reframe: we sit above, pull from the stack, feed GRC tool with measured controls. See [[../methodology/objections]] #7.
- "This is the CISO's decision." True. Use GRC as coach to multi-thread to CISO. See [[../playbook/closed-lost-patterns]] multi-thread requirement.
- "We're building this in-house." See [[../methodology/objections]] #6. Reference the 160-hour and 40-hour quotes from [[../product/quotes]].

## CTA preferences

- Walk-through of the Security Stack Map auto-generation against their known stack.
- Evidence-collection demo against their upcoming audit framework.
- Joint call with CISO, positioned as "how we'd feed your existing GRC workflow, not replace it."

## Watch signals

- NYDFS 2026-04-15 certification deadline → [[../triggers/sec-cyber-rule]].
- HIPAA Security Rule final rule publication (target May 2026) → [[../triggers/sec-cyber-rule]] + [[../verticals/healthcare]].
- New framework adoption announcement (company now ISO 27001 cert in progress, etc.) → coach signal.
- Job change at GRC director level → [[../triggers/exec-hire]].

## Accounts where GRC is the coach

- [[../../10_Accounts/OCC]] — [[Jessica Kruse]], MD GRC Services.
- [[../../10_Accounts/First Horizon Bank]] — [[Leilani Farol]] prior Head of GRC at Fidelity, GRC-to-CISO path.

## Who wins when GRC is bought in

GRC is an excellent coach but rarely the EB. The CISO is the champion; the CFO or CIO is the EB. Multi-thread from GRC upward the day they nod. Single-threaded GRC deals drift and die (60% of closed-lost had 1 contact per [[../playbook/closed-lost-patterns]]).

## Cross-references

- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../product/features]]
- [[../product/positioning]]
- [[../methodology/objections]]
- [[../industry/regulatory-calendar]]
- [[../triggers/sec-cyber-rule]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../90_Templates/tpl-grc-cold]]
