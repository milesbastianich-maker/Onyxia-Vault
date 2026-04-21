---
type: intel
subtype: industry
topic: regulatory calendar
source: SEC + NYDFS + HHS OCR + NIST + TSA + DoD CMMC (pulls 2026-04-22)
created: 2026-04-22
tags: [intel]
---

# Regulatory Calendar 2026-2027

Forcing functions by vertical. Every deadline is a trigger. Map to [[../triggers/sec-cyber-rule]] + [[../triggers/10k-8k-filing]] + vertical files.

## Finserv

- **2026-04-15 — NYDFS Part 500 annual compliance certification due** (Appendix A form). Covers all covered entities under 23 NYCRR Part 500. Penalties start $2,500/day per violation under NY Banking Law. CISO must now report at least annually in writing to the board. Source: [Hogan Lovells](https://www.hoganlovells.com/en/publications/nydfs-final-set-of-cybersecurity-requirements-under-amended-part-500-take-effect-november-1-2025).
- **Rolling — SEC 8-K Item 1.05 material incident disclosure.** Four business days from materiality determination. Effective since 2023-12-18. 24 filings disclosed as of late 2024. Source: [SEC.gov 2023-139](https://www.sec.gov/newsroom/press-releases/2023-139).
- **Rolling — SEC 10-K Item 1C cybersecurity narrative.** Annual, on fiscal-year-end cycle. See [[../triggers/10k-8k-filing]].
- **Ongoing — PCI-DSS 4.0.1.** Migration deadline 2025-03-31 (already passed). Entities now in full-compliance mode.
- **Rolling — GLBA Safeguards Rule (FTC amended).** In effect since 2023-06-09 for nonbank financial institutions.

See [[../verticals/financial-services]].

## Healthcare

- **Target 2026-05 — HIPAA Security Rule final rule (OCR).** NPRM published 2025-01-06, comment period closed 2025-03-07, nearly 5,000 comments. OCR's Unified Regulatory Agenda milestone: May 2026. Finalization brings mandatory asset inventory + network map (every 12 months), encryption at rest + in transit, MFA, annual pen test, 72-hour restoration objective, 24-hour access-change notifications, annual compliance audit. Source: [HHS.gov NPRM fact sheet](https://www.hhs.gov/hipaa/for-professionals/security/hipaa-security-rule-nprm/factsheet/index.html).
- **Active — OCR Audits Phase 3.** Started March 2025. Initially ~50 covered entities + business associates. Focus on risk analysis + risk management requirements.
- **2025 anchor enforcement** — $1.5M Warby Parker OCR penalty for credential-stuffing-linked Security Rule failures. Precedent: risk analysis deficiencies carry material CMPs.
- **Rolling — state breach notification + state AG privacy enforcement.**

See [[../verticals/healthcare]].

## Manufacturing / Defense

- **2026-11-10 — CMMC Phase 2 begins.** Mandatory C3PAO Level 2 certification for applicable CUI contracts. ~80 C3PAOs serving ~80,000 contractors. Wait times will exceed 18 months for new clients by Q3 2026. Source: [Secureframe CMMC hub](https://secureframe.com/hub/cmmc/proposed-final-rule).
- **2027-11-10 — CMMC Phase 3.** Level 3 assessments introduced.
- **2028-11-10 — CMMC Phase 4.** Full implementation across all contracts.
- **Pending — NIST CSF 2.0 Manufacturing Profile (NIST IR 8183r2).** Initial public draft comment period closed 2025-11-17. Realigns guidance to CSF 2.0 including new Govern function. Source: [NIST CSRC](https://csrc.nist.gov/News/2025/csf-2-0-manufacturing-profile-initial-draft).
- **In effect — EU NIS2 Directive.** National transpositions live from late 2024.

See [[../verticals/manufacturing]].

## Critical Infrastructure

- **2026-05-02 — TSA Security Directive Pipeline-2021-02F expires.** Covers incident reporting + cybersecurity coordinator + cybersecurity plan + annual assessment for pipeline owner/operators. Source: [TSA SD 2021-02F](https://www.tsa.gov/sites/default/files/tsa-security-directive-pipeline-2021-02f-and-memo-508c.pdf).
- **Pending finalization — TSA NPRM Surface Transportation Cybersecurity Rule (Nov 2024 proposed).** Permanent rule for pipelines + freight rail + passenger rail + rail transit + higher-risk bus. Requires cyber risk management program + incident reporting to CISA. Leverages NIST CSF + CISA CPGs. Source: [TSA 2024-11-06 press release](https://www.tsa.gov/news/press/releases/2024/11/06/tsa-announces-proposed-rule-would-require-establishment-pipeline-and).
- **Rolling — NERC CIP standards** for electric utilities.
- **Rolling — CISA Cross-Sector CPGs.** Voluntary baseline, used as TSA + sector-specific reference.
- **Rolling — EPA water sector cybersecurity guidance.** Post-2024 enforcement focus.

See [[../verticals/critical-infrastructure]].

## Cross-cutting (all verticals)

- **NIST CSF 2.0.** Published February 2024. Adds Govern function as sixth core. Voluntary for private sector. Reference: [NIST CSF 2.0 PDF](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf).
- **SOC 2 Type II.** Table stakes for SaaS. Annual renewal cycle.
- **ISO 27001:2022.** 3-year transition from 2013 ran 2022-10-31 to 2025-10-31. All active certifications now on 2022 baseline.
- **US state comprehensive privacy laws.** Rolling effective dates across ~20 states.
- **EU GDPR + UK GDPR.** In effect. AI Act rolling.

## How to use this file

- Morning brief ([[../../40_Plays/shifts/morning-brief]]) checks for accounts within 60-90 days of a listed deadline.
- Trigger-event hunt ([[../../40_Plays/hunt/trigger-event-hunt]]) filters prospects by regulatory-deadline proximity.
- Weekly synthesis ([[../../40_Plays/shifts/weekly-synthesis]]) adds new deadlines as they're published.

## Cross-references

- [[../triggers/sec-cyber-rule]]
- [[../triggers/10k-8k-filing]]
- [[../triggers/breach-event]]
- [[../triggers/settlement-event]]
- [[../verticals/financial-services]]
- [[../verticals/healthcare]]
- [[../verticals/manufacturing]]
- [[../verticals/critical-infrastructure]]
- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../personas/ciso]]
- [[../personas/grc-director]]
- [[../methodology/objections]]
- [[../../40_Plays/hunt/trigger-event-hunt]]
