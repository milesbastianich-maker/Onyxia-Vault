---
type: intel
subtype: vertical
vertical: fins
source: closed-won corpus + SEC rulemaking + NYDFS Part 500 + DBIR 2025
created: 2026-04-22
tags: [intel, v/fins]
---

# Financial Services

Second-ranked winning vertical by dollars. Wins: Premera ($170K, health insurance), CWT ($100K, corp travel adjacency), Simpson Thacher ($60K, BigLaw, 577-day cycle), Vista Equity ($37.5K, PE). Active Tier 1 pipeline: [[../../10_Accounts/OCC]], [[../../10_Accounts/RGA Reinsurance]], [[../../10_Accounts/First Horizon Bank]]. Pattern: regulated filers with multi-framework surface + named CISO or GRC director. See [[../playbook/closed-won-patterns]].

## Regulatory surface

- **SEC Cybersecurity Disclosure Rule (17 CFR 229.106, 17 CFR 249.308 Item 1.05 Form 8-K).** Effective 2023-12-18. Requires disclosure of material cybersecurity incidents on Form 8-K within four business days of materiality determination. Materiality determination must be made "without unreasonable delay." As of late 2024, 24 Item 1.05 disclosures filed. October 2024 settled enforcement actions against 4 companies for misleading 8-K cyber statements. Source: [SEC Press Release 2023-139](https://www.sec.gov/newsroom/press-releases/2023-139).
- **NYDFS 23 NYCRR Part 500 (Second Amendment).** Final requirements took effect 2025-11-01. Annual compliance certification due 2026-04-15 in Appendix A form. CISO now required to report at least annually in writing to the board. Expanded MFA, asset inventory, third-party vendor inventory + due diligence, explicit contract provisions. Penalties start $2,500/day per violation under NY Banking Law. Sources: [Hogan Lovells](https://www.hoganlovells.com/en/publications/nydfs-final-set-of-cybersecurity-requirements-under-amended-part-500-take-effect-november-1-2025), [HYPR](https://www.hypr.com/blog/the-cost-of-nydfs-cybersecurity-noncompliance).
- **OCC + FDIC interagency guidance** on third-party risk (2023).
- **PCI-DSS 4.0.1** — in effect.
- **SOC 2 Type II** — table stakes for SaaS finservs.
- **GLBA Safeguards Rule (amended 2021, FTC enforcement since 2023-06-09)** — for nonbank financial institutions.

## What finserv CISOs care about

1. **SEC Item 1.05 materiality defensibility.** If an incident happens, the documented risk analysis + governance trail determines whether the 8-K is defensible or draws SEC enforcement.
2. **Annual board reporting.** NYDFS now mandates it in writing. Onyxia's [[../product/features]] pillar 4 (Automated Board & Executive Reporting) maps directly.
3. **Third-party + vendor risk inventory.** DBIR 2025: third-party involvement doubled to 30% of breaches YoY.
4. **Credential stuffing + phishing defense metrics.** DBIR: finserv is top-hit + fastest detection.

## Who wins the meeting

Primary: CISO, CSO, Head of Information Security.
Secondary thread: GRC Director (NYDFS-heavy shops), CIO, Chief Risk Officer, GC (post-8-K), CFO (board reporting sponsor).
See [[../personas/ciso]], [[../personas/grc-director]], [[../personas/general-counsel]].

## Attack vectors (DBIR 2025)

Finserv is a top target for credential stuffing + phishing. Fastest industry for detection. Heavy third-party exposure (vendor + fintech integration surface). Source: [Verizon 2025 DBIR executive summary](https://www.verizon.com/business/resources/reports/2025-dbir-executive-summary.pdf).

## Play selection

- New CISO or MD GRC within 180 days: [[../../40_Plays/sivan-peer-intro]]. Live at [[../../10_Accounts/First Horizon Bank]] (Leilani Farol, Feb 2026) and [[../../10_Accounts/OCC]] (Jessica Kruse, March 2026).
- NYDFS April 15 certification window: [[../triggers/sec-cyber-rule]].
- BigLaw without warm intro: de-prioritize. See [[../playbook/closed-lost-patterns]] BigLaw section. Simpson Thacher is the exception and it took 577 days.
- 8-K filing on peer: [[../triggers/breach-event]].

## Accounts in play

- [[../../10_Accounts/OCC]] — world's largest equity derivatives clearing, SEC clearing-member cyber obligations.
- [[../../10_Accounts/First Horizon Bank]] — $84B-asset bank, new CISO Feb 2026.
- [[../../10_Accounts/RGA Reinsurance]] — reinsurance, Tier 1 finserv fit.

## Closed-won references

- Premera Blue Cross ($170K, 169 days) — health insurance / finserv adjacency.
- CWT ($100K, 585 days) — corp travel with finserv-grade compliance.
- Simpson Thacher & Bartlett ($60K, 577 days) — only BigLaw win, likely Sivan-peer-intro routed.
- Vista Equity Partners ($37.5K, 72 days) — PE, fast cycle, network-driven.
- Alchemy Tech Group, World Wide Technology, Consortium Networks — partner pipeline finserv-adjacent.

## Closed-lost references

IPG ($150K non-responsive), HarbourVest ($125K non-responsive), Lowenstein Sandler (budget), Fitch Group (budget), Sullivan & Cromwell + Milbank (BigLaw non-responsive). Common thread: 1 contact, no EB, no forcing event. See [[../playbook/closed-lost-patterns]].

## Language that lands

- "NYDFS-regulated entities owe the board a written cyber report at least annually. How is your team producing that today?"
- "Item 1.05 materiality determinations live or die on the governance trail. Onyxia puts that trail in one place."
- "Finserv is the fastest industry to detect breaches and also the most-hit for credential stuffing. What's your visibility into IAM telemetry across the stack?"

## Cross-references

- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../product/positioning]]
- [[../product/quotes]]
- [[../product/features]]
- [[../methodology/objections]]
- [[../industry/regulatory-calendar]]
- [[../industry/breach-report-synthesis]]
- [[../triggers/sec-cyber-rule]]
- [[../triggers/exec-hire]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../90_Templates/tpl-ciso-cold]]
- [[../../90_Templates/tpl-grc-cold]]
