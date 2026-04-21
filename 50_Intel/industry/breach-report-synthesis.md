---
type: intel
subtype: industry
topic: breach report synthesis
source: Verizon DBIR 2025 + Mandiant M-Trends 2025
created: 2026-04-22
tags: [intel]
---

# Breach Report Synthesis (DBIR 2025 + M-Trends 2025)

The two reports CISOs cite. Headline findings compressed for cold-email anchors + meeting prep talking points. Always cite by name. Never fabricate a stat. Source links inline.

## Verizon DBIR 2025 — what CISOs are quoting

- **Third-party involvement doubled to 30% of breaches** (from ~15% prior year). Supply chain + vendor + fintech integration surface is the new center of gravity.
- **Credential abuse remains #1 initial access** (22% of breaches).
- **Vulnerability exploitation #2** (20%), up 34% YoY. Top exploited: edge devices + VPN software.
- **System intrusion breaches doubled in EMEA.**
- Source: [Verizon 2025 DBIR executive summary](https://www.verizon.com/business/resources/reports/2025-dbir-executive-summary.pdf). See also [Verizon announcement](https://www.verizon.com/about/news/2025-data-breach-investigations-report).

### Vertical cuts

- **Healthcare.** Espionage-motivated attacks rising sharply. Insider + error-related breaches dominate. Over-indexed on BAA / third-party risk. See [[../verticals/healthcare]].
- **Manufacturing.** **6x surge in espionage-motivated breaches (3% → 20% YoY).** IP theft + ransomware top. OT/ICS lag on basic controls. Source: [Verizon manufacturing snapshot](https://www.verizon.com/business/resources/infographics/2025-dbir-manufacturing-snapshot.pdf). See [[../verticals/manufacturing]].
- **Financial Services.** Heavy credential stuffing + phishing targeting. Fastest sector for breach detection. See [[../verticals/financial-services]].
- **Critical Infrastructure.** Edge + VPN exploits are the threat vector. See [[../verticals/critical-infrastructure]].

## Mandiant M-Trends 2025 — what CISOs are quoting

- **Global median dwell time: 11 days** (up from 10 in 2023).
- **5 days median** when adversary notified (i.e., ransomware).
- **10 days** when org-internal discovery.
- **26 days** when external entity notified.
- **45.1% of investigations detected within one week** (up from 43.3% YoY).
- **Top initial infection vectors:** exploits 33% (leader 5 years running), stolen credentials 16% (first time at #2), email phishing 14%, web compromises 9%, prior compromises 8%.
- **Most exploited vulnerabilities were in security products themselves.** Three of four top exploits were zero-days in security tools: CVE-2024-3400 (Palo Alto PAN-OS GlobalProtect), CVE-2023-46805 + CVE-2024-21887 (Ivanti Connect Secure), CVE-2023-48788 (Fortinet FortiClient EMS).
- Source: [M-Trends 2025 — Google Cloud blog](https://cloud.google.com/blog/topics/threat-intelligence/m-trends-2025) and [M-Trends 2025 PDF](https://services.google.com/fh/files/misc/m-trends-2025-en.pdf).

## What to say in a cold email

Anchor stats to vertical. Never drop a generic "DBIR says" line.

- **Healthcare.** "DBIR 2025 shows healthcare third-party breaches jumping. With BAA sprawl + OCR's Phase 3 audits active, the question is where your evidence trail actually lives."
- **Manufacturing.** "Verizon's DBIR shows espionage-motivated manufacturing breaches went from 3% to 20% in a year. Your OT stack and your corporate stack don't share a dashboard today. That's the gap."
- **Finserv.** "Finserv leads every industry on detection speed. That means your board + regulator are calibrated for a 10-day ceiling. M-Trends 2025 flagged stolen credentials as the new #2 access vector. IAM telemetry matters."
- **Critical Infra.** "Edge + VPN exploits are the top access vector per DBIR 2025. Your Stack Map needs to show that layer explicitly to the board."

## What to NOT say

- "The average breach costs $X." (IBM Cost of a Data Breach report. Not synthesized here yet. Vault silent.)
- "CISOs are the most stressed C-suite role." (marketing slop)
- "AI is weaponizing phishing." (too generic)

## Contradictions / clarifications vs our existing playbook

- Our [[../playbook/closed-lost-patterns]] notes Onyxia does not lose to competitors. The DBIR/M-Trends data reinforces that security vendors themselves are attack targets (zero-days in Palo Alto, Ivanti, Fortinet). This is an argument for Onyxia's "layer above" positioning — we don't ADD to the attack surface; we make the existing one visible. Useful counter to "dashboard fatigue" objection per [[../methodology/objections]] #8.
- No contradictions found vs existing vault claims.

## How this file gets updated

- Q2 2026: refresh when Verizon + Mandiant publish their 2026 reports (typically April for DBIR, April-May for M-Trends).
- Append specific vertical-cut findings as they surface in prospect conversations.

## Cross-references

- [[regulatory-calendar]]
- [[../triggers/breach-event]]
- [[../triggers/10k-8k-filing]]
- [[../triggers/sec-cyber-rule]]
- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../personas/ciso]]
- [[../personas/grc-director]]
- [[../methodology/objections]]
- [[../verticals/healthcare]]
- [[../verticals/financial-services]]
- [[../verticals/manufacturing]]
- [[../verticals/critical-infrastructure]]
- [[../product/positioning]]
- [[../../40_Plays/hunt/trigger-event-hunt]]
