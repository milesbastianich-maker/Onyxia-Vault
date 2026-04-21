---
type: intel
subtype: vertical
vertical: ci
source: closed-won corpus + TSA directives + CISA CPGs + NIST CSF 2.0
created: 2026-04-22
tags: [intel, v/ci]
---

# Critical Infrastructure

Third-ranked vertical by dollars. Wins: Port Authority NY/NJ ($135K, transit, LinkedIn-sourced), Summit Utilities ($80K), Orange County Transportation Authority ($60K, 71 days). Pattern: government-adjacent buyers with compliance-driven budget + named champion. See [[../playbook/closed-won-patterns]].

## Regulatory surface

- **CISA Cross-Sector Cybersecurity Performance Goals (CPGs).** Voluntary baseline across 16 sectors. Used as reference for TSA directives.
- **TSA Security Directive Pipeline-2021-02F.** Effective 2025-05-03, expires 2026-05-02. Ongoing cyber threat to pipeline systems is TSA's stated basis. Covers incident reporting + cybersecurity coordinator + cybersecurity plan + annual assessment. Source: [TSA SD Pipeline-2021-02F](https://www.tsa.gov/sites/default/files/tsa-security-directive-pipeline-2021-02f-and-memo-508c.pdf).
- **TSA NPRM (November 2024)** — proposed permanent rule requiring cyber risk management programs for pipelines, freight rail, passenger rail, rail transit, higher-risk bus transit, over-the-road buses. Mandates incident reporting to CISA. Leverages NIST CSF + CISA CPGs. Source: [TSA press release 2024-11-06](https://www.tsa.gov/news/press/releases/2024/11/06/tsa-announces-proposed-rule-would-require-establishment-pipeline-and).
- **NIST CSF 2.0** — baseline for most critical-infra programs, including the new Govern function.
- **NERC CIP** — electric utilities specifically.
- **EPA Water Sector cybersecurity guidance** — post-2024 enforcement focus.

## What critical-infra CISOs care about

1. **Board + regulator-ready reporting.** CISA + TSA + sector-specific regulators all want program documentation.
2. **OT + IT normalized into one view.** SCADA, PLC, corporate IT don't share a dashboard natively.
3. **CPG / NIST CSF scoring over time.** Ability to show maturity trend to the board + funders.
4. **Funding defensibility.** Transit authorities, utilities, port authorities tap bond issuances + federal grants. Cyber program spend has to be defensible.

## Who wins the meeting

Primary: CISO, CSO, Head of Security, Director of Cybersecurity.
Secondary thread: CIO, COO, General Counsel, Chief Risk Officer, Chief Compliance Officer.
See [[../personas/ciso]], [[../personas/vp-security]].

## Attack vectors (DBIR 2025)

Critical-infrastructure-adjacent sectors see heavy OT-targeted intrusions + ransomware. Edge devices + VPN exploits are the top initial access vector in the broader set (vulnerability exploitation up 34% YoY). Source: [Verizon 2025 DBIR](https://www.verizon.com/business/resources/reports/dbir/).

## Play selection

- New CISO at transit/utility/port authority: [[../../40_Plays/sivan-peer-intro]].
- TSA SD expiration window (May 2026): [[../triggers/sec-cyber-rule]] (compliance deadline play adapts to TSA too).
- Post-incident peer in same sub-sector: [[../triggers/breach-event]].
- LinkedIn-sourced champion (Port Authority won this way): [[../../40_Plays/hunt/intent-signal-hunt]] + direct social touch.

## Closed-won references

- Port Authority NY/NJ ($135K, transit, LinkedIn-sourced).
- Summit Utilities ($80K, Maura-sold).
- Orange County Transportation Authority ($60K, 71 days — fast network-driven close).

## Closed-lost references

Vault-thin on critical-infra-specific losses. Most losses in the 113-deal corpus are healthcare, BigLaw, and mid-market SaaS. Critical-infra names that went non-responsive: check [[../playbook/closed-lost-patterns]] for any sector-specific account name matches. Propose adding a sub-section on critical-infra losses once more data points accumulate.

## Language that lands

- "CISA and TSA both want the same thing the board wants. A documented, defensible cyber program with a maturity trend line."
- "Your plant OT stack and your corporate SIEM don't share a dashboard today. We make that one view." (verbatim-style from [[../product/positioning]])
- "The TSA Pipeline SD expires in May 2026. The permanent rule is coming. Who owns your CSF-to-CPG crosswalk today?"

## Cross-references

- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../product/positioning]]
- [[../product/features]]
- [[../methodology/objections]]
- [[../industry/regulatory-calendar]]
- [[../industry/breach-report-synthesis]]
- [[../triggers/exec-hire]]
- [[../triggers/sec-cyber-rule]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../40_Plays/hunt/intent-signal-hunt]]
- [[../../90_Templates/tpl-ciso-cold]]
- [[../../90_Templates/tpl-vpsec-cold]]
