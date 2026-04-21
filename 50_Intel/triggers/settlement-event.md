---
type: intel
subtype: trigger
trigger: settlement-event
source: Medusind 2026-04 live example + class-action settlement patterns
created: 2026-04-22
tags: [intel]
---

# Settlement Event

Breach-related class action settlement approved, paid, or near-final. Specific post-breach sub-trigger. Compliance + board + GC attention all peaking at once. Distinct from the raw breach-event trigger because the litigation posture has resolved and the program-maturity narrative is now the board's main ask. See [[breach-event]] for the base pattern.

## Detection pattern

- Pacer docket alerts on class-action suits against Tier 1 ICP companies.
- Class-action settlement news (e.g., Top Class Actions, JD Supra).
- Court approval orders (preliminary + final).
- Settlement fund payment dates.
- Press releases from plaintiff firms.
- Company 10-K / 10-Q "legal proceedings" footnote updates.

## Response timing

- **Pre-preliminary approval:** do not engage. Litigation posture active.
- **Preliminary approval → final approval:** soft-touch if already in conversation. No new prospecting outreach.
- **Final approval → payment:** GC is preparing forward-looking program-maturity narrative. This is the unlock moment.
- **30-180 days post-payment:** sweet spot. Settlement terms often include ongoing security program reporting. Onyxia is that report.

## Historical win examples

Vault-silent on direct settlement-triggered wins. Hypothesis: Centra Health inbound during post-incident window is the closest historical match. Propose tracking settlement-event-triggered deals explicitly going forward so we have a clean data set.

## Active example

- [[../../10_Accounts/Medusind]] — $5M class-action settlement. Preliminary approval 2025 season, final court approval 2026-01-27, payments sent to class members 2026-04-10. 2023 breach impacted 360,934 individuals. Single-threaded today with [[Jigar Shah]] CISO. Multi-thread angle live on [[Megan Marshall]] GC per account MEDDPICC. See [[../personas/general-counsel]].

## Multi-thread pattern (GC unlock)

Settlement events are the GC's moment. The CISO is focused on forward-program execution. The GC is focused on:
1. Defensibility of ongoing compliance (settlement terms frequently mandate this).
2. Cyber insurance renewals post-settlement.
3. Board updates on risk remediation.

Onyxia gives all three a single evidence source. See [[../personas/general-counsel]] CTA section.

## Template reference

Use [[../../90_Templates/tpl-ciso-cold]] for CISO angle (post-response rebuild framing). A dedicated GC cold template is vault-silent today — propose `tpl-gc-cold.md` as a next-step note if the GC angle converts at Medusind.

## Language that lands

- "The settlement is paid. The forward story is program maturity. That's the board's next ask."
- "Settlement terms usually require ongoing security program reporting. Onyxia makes that report one-click."
- "Your cyber insurer is writing the next renewal off of your program posture. We document that posture continuously."

## Historical loss examples

Vault-thin. Most settlement-adjacent accounts have only been tracked post-2026. Weekly Friday synthesis will add examples here as they accumulate.

## Cross-references

- [[breach-event]]
- [[10k-8k-filing]]
- [[../icp]]
- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../personas/general-counsel]]
- [[../personas/ciso]]
- [[../methodology/objections]]
- [[../verticals/healthcare]]
- [[../verticals/financial-services]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../90_Templates/tpl-ciso-cold]]
