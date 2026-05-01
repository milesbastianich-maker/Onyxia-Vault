---
type: intel
subtype: industry
topic: regulatory calendar
source: SEC + NYDFS + HHS OCR + NIST + TSA + DoD CMMC + CISA CIRCIA (pulls 2026-05-01)
created: 2026-04-22
updated: 2026-05-01
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
- **2026-04 — OCC Model Risk Management Guidance updated (OCC Bulletin 2026-13).** Interagency (OCC + Fed + FDIC) revised guidance. Risk-based, tailored to institution size and complexity. Explicitly covers AI models used by banks. National banks expected to review and update model risk governance frameworks. Source: [OCC News Release 2026-29](https://www.occ.treas.gov/news-issuances/news-releases/2026/nr-occ-2026-29.html).

See [[../verticals/financial-services]].

## Healthcare

- **Target 2026-05 — HIPAA Security Rule final rule (OCR).** #window/60d NPRM published 2025-01-06, nearly 5,000 comments. OCR Unified Regulatory Agenda milestone: May 2026. Industry coalition of 100+ hospital systems called for withdrawal. May slip to late 2026; enforcement will likely lag finalization by ~1 year. If finalized: mandatory asset inventory + network map (12-month cycle), encryption at rest + in transit, MFA, annual pen test, 72-hour restoration objective, 24-hour access-change notifications, annual compliance audit. Accounts: [[../../10_Accounts/FMOL Health]], [[../../10_Accounts/GenomOncology]], [[../../10_Accounts/People Inc]], [[../../10_Accounts/Medusind]]. Source: [HHS.gov NPRM fact sheet](https://www.hhs.gov/hipaa/for-professionals/security/hipaa-security-rule-nprm/factsheet/index.html).
- **2026-05-01 — OCR enforcement expands from risk analysis to risk management.** OCR Senior Advisor for Cybersecurity guidance confirms formal enforcement now targets risk management (acting on risks), not just risk analysis (knowing risks). Risk management deficiencies now carry the same CMP exposure as risk analysis failures. Rolling enforcement trigger. Source: [Clearwater Security](https://clearwatersecurity.com/blog/hipaa-security-rule-enforcement-2026/).
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

- **2026-05-02 — TSA Security Directive Pipeline-2021-02F expires. Superseded by Pipeline-2021-01G.** #window/60d New directive issued 2026-01-09, effective 2026-01-16 through 2027-01-15. Covers same core requirements: cybersecurity coordinator, incident reporting to CISA, vulnerability assessment, Cybersecurity Implementation Plan. Pipeline owner/operators must verify they are complying with the updated 01G version, not the expired 02F. Source: [TSA SD Pipeline-2021-01G](https://www.tsa.gov/sites/default/files/signed_security-directive-pipeline-2021-01g-and-transmittal-memo_508c.pdf).
- **2026-05-02 — TSA Railroad Security Directive 1580/82-2022-01D issued.** #window/60d Supersedes prior version. Applies to freight railroad carriers + TSA-designated freight + passenger railroads. Requires: cybersecurity coordinator, incident reporting to CISA, cybersecurity vulnerability assessment, TSA-approved Cybersecurity Implementation Plan, annual Cybersecurity Assessment Program. Issued in response to ongoing threat to surface transportation systems. Accounts: [[../../10_Accounts/GE Vernova]], [[../../10_Accounts/FirstEnergy]], [[../../10_Accounts/SJI]]. Source: [TSA SD 1580/82-2022-01D](https://www.tsa.gov/sites/default/files/security_directive_1580-21-01c_and_memo_508c.pdf).
- **Target 2026-05 — CISA CIRCIA Final Rule.** #window/60d Cyber Incident Reporting for Critical Infrastructure Act of 2022. Final rule delayed from Oct 2025 to May 2026. Will require: 72-hour incident reporting to CISA from time of "reasonable belief" a covered incident occurred; 24-hour reporting for ransom payments. Applies to entities in all 16 critical infrastructure sectors exceeding SBA small-business size standards (est. 300,000+ entities). Compliance clock begins post-publication. CISA held virtual town halls by sector in March 2026. Accounts: [[../../10_Accounts/GE Vernova]], [[../../10_Accounts/FirstEnergy]], [[../../10_Accounts/SJI]]. Source: [CyberScoop](https://cyberscoop.com/cisa-pushes-final-cyber-incident-reporting-rule-to-may-2026/).
- **Pending finalization — TSA NPRM Surface Transportation Cybersecurity Rule (Nov 2024 proposed).** Permanent rule for pipelines + freight rail + passenger rail + rail transit + higher-risk bus. Requires cyber risk management program + incident reporting to CISA. Leverages NIST CSF + CISA CPGs. Source: [TSA 2024-11-06 press release](https://www.tsa.gov/news/press/releases/2024/11/06/tsa-announces-proposed-rule-would-require-establishment-pipeline-and).
- **Rolling — NERC CIP standards** for electric utilities.
- **Rolling — CISA Cross-Sector CPGs.** Voluntary baseline, used as TSA + sector-specific reference.
- **Rolling — EPA water sector cybersecurity guidance.** Post-2024 enforcement focus.

See [[../verticals/critical-infrastructure]].

## Cross-cutting (all verticals)

- **NIST CSF 2.0.** Published February 2024. Adds Govern function as sixth core. Voluntary for private sector. Reference: [NIST CSF 2.0 PDF](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf).
- **2026-05-06 — NIST CSF 2.0 Informative References Quick-Start Guide public comment deadline.** #window/60d Comment period closes May 6, 2026. Practitioners mapping controls to CSF 2.0 should track this. Source: [NIST CSRC](https://csrc.nist.gov/News/2026/two-new-csf-2-0-quick-start-guides).
- **Draft — NIST CSF 2.0 AI Cybersecurity Framework Profile.** NIST NCCoE released preliminary draft. Full-day workshop held 2026-01-14. Covers AI system risks mapped to CSF 2.0 functions. Final profile will affect how AI-using covered entities demonstrate security governance. Source: [NIST NCCoE](https://www.nist.gov/cyberframework).
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
