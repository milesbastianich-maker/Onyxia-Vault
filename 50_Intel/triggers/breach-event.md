---
type: intel
subtype: trigger
trigger: breach-event
source: closed-won corpus + DBIR 2025 + SEC 8-K Item 1.05 activity
created: 2026-04-22
tags: [intel]
---

# Breach Event

The highest-converting trigger per [[../icp]]. Recent breach or incident at a Tier 1 ICP account collapses the "time frame" and "budget" objections. Pain is acute. Board is asking questions. GC and CFO are engaged. See [[../personas/general-counsel]] for the multi-thread angle.

## Detection pattern

- SEC 8-K Item 1.05 filing. Since 2023-12-18, public companies must file within four business days of materiality determination. As of late 2024, 24 filings on record. Source: [SEC.gov 2023-139](https://www.sec.gov/newsroom/press-releases/2023-139).
- State AG + HHS OCR breach-reporting portals. HHS "Wall of Shame" is real-time for healthcare entities over 500 individuals affected.
- Class-action filings on Pacer / Courtlistener.
- Settlement news (see [[settlement-event]]).
- Dark-web leak-site postings monitored via ZoomInfo / Recorded Future / news aggregators.
- RB2B spike on `/security` + `/incident-response` paths of our website from the affected domain.

## Response timing

- **Days 0-3:** do NOT reach out. They are in triage. Vendor email to a CISO mid-incident is a block-the-sender event.
- **Days 7-30:** peer-tone note to the CISO. "Not asking for a meeting today. Here if useful. Sivan is a former CISO." Short. No ask.
- **Days 30-90:** post-response rebuild window. CISO is building the forward program. This is when Onyxia's Automated Board Reporting ([[../product/features]] pillar 4) becomes the unlock. Lead with this window.
- **Days 90+:** if 8-K or settlement was filed, compliance-disclosure narrative matures. Multi-thread to GC + CFO. See [[settlement-event]].

## Historical win examples

- **Centra Health** won at $270K after inbound web traffic during post-incident awareness window. Fastest inbound healthcare win on record. See [[../playbook/closed-won-patterns]].
- **WellStar** won at $172K over 553 days. Long-cycle post-incident hospital system rebuild.
- **Premera Blue Cross** won at $170K, 169 days. Health insurance mid-cycle, post-prior-breach program maturity push.

## Historical loss examples

Vault-thin on "reached out during triage and got blocked" data points. Likely non-responsive losses in [[../playbook/closed-lost-patterns]] include some cases where Onyxia reached out too early. Propose: when a breach-response cold draft gets rejected, capture reason per [[../../40_Plays/rejection-feedback]] with "timing" tag.

## Active example

- [[../../10_Accounts/Medusind]] — post-settlement window ($5M paid 2026-04-10, 360,934 individuals impacted Dec 2023). Day 11 post-payment. This is inside the response rebuild window.

## Template reference

Use [[../../90_Templates/tpl-ciso-cold]]. Opener anchors on the post-incident rebuild window, NOT on the incident itself. Never say "sorry to hear about the breach" — patronizing and a block trigger.

## Language that lands

- "Rebuilding the program after an incident is a different job than running it steady. Sivan ran both. 20 minutes."
- "The 8-K materiality narrative lives or dies on documented governance. That's what we put in one place."
- "Your insurer and your regulator are both going to ask for program-maturity evidence. We make that one view."

## Cross-references

- [[10k-8k-filing]]
- [[settlement-event]]
- [[../icp]]
- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../personas/ciso]]
- [[../personas/general-counsel]]
- [[../industry/breach-report-synthesis]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../90_Templates/tpl-ciso-cold]]
