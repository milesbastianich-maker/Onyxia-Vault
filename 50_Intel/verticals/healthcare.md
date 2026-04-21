---
type: intel
subtype: vertical
vertical: healthcare
source: closed-won corpus + HHS/OCR 2025 NPRM + HIPAA Journal 2026 + DBIR 2025
created: 2026-04-22
tags: [intel, v/healthcare]
---

# Healthcare

The #1 winning vertical. Four direct wins totaling $672K (Centra, WellStar, Premera, Christiana). Long cycles possible (WellStar 553 days). Biggest single win on record (Centra $270K) came through inbound web traffic. Pattern: multi-thread CISO + CIO + Privacy/GC. Compliance pressure now pivots on the HIPAA Security Rule NPRM (Jan 2025).

See [[../playbook/closed-won-patterns]] and [[../playbook/closed-lost-patterns]].

## Regulatory surface

- **HIPAA Security Rule (45 CFR Part 164, Subpart C).** First major overhaul since 2013. NPRM published 2025-01-06, comment period closed 2025-03-07. Target finalization per OCR Unified Regulatory Agenda: May 2026. Removes the "addressable" vs "required" distinction. Mandates asset inventory + network map updated at least every 12 months, encryption at rest and in transit, MFA, annual pen tests, 72-hour restoration objective, 24-hour access-change notifications, annual compliance audits. Source: [HHS.gov NPRM fact sheet](https://www.hhs.gov/hipaa/for-professionals/security/hipaa-security-rule-nprm/factsheet/index.html).
- **HITECH** — breach notification + state AG enforcement expansion.
- **OCR Audits Phase 3** — active since March 2025. 50 covered entities + business associates. Focus: risk analysis + risk management (per OCR Director).
- **2025 OCR enforcement anchor.** Warby Parker $1.5M civil monetary penalty for credential-stuffing-linked Security Rule failures. Risk analysis + activity review deficiencies cited. Source: [HIPAA Journal](https://www.hipaajournal.com/new-hipaa-regulations/).

## What healthcare CISOs care about (from the closed-won corpus)

1. **Analyst hours saved on manual reporting.** Quote from [[../product/quotes]]: "160 working hours a month that one full-time analyst would traditionally spend on manual reporting." This is a not-for-profit healthcare CISO. Copy verbatim for any healthcare prospect.
2. **Multi-facility + multi-BU compliance visibility.** Hospital systems have distributed HIPAA surfaces. Single dashboard matters.
3. **Board-ready framework reporting.** One-click HIPAA + HITRUST view is the [[../product/features]] pillar 7 sell.
4. **Risk quantification post-breach.** Centra, WellStar, Medusind-style post-incident buyers want measurable risk-reduction evidence.

## Who wins the meeting

Primary: CISO, VP Security.
Secondary thread: CIO, Privacy Officer, GC (post-breach), CFO.
Healthcare wins average 2-5 contacts per deal. Healthcare losses average 1-2. Multi-thread or die. See [[../personas/ciso]] and [[../personas/general-counsel]].

## Attack vectors (2025 DBIR)

- Espionage-motivated attacks rising sharply in healthcare.
- Insider threats + error-related breaches lead the sector.
- Third-party involvement in 30% of breaches across all verticals, up from ~15% YoY. Healthcare is over-indexed on BAA risk. Source: [Verizon 2025 DBIR](https://www.verizon.com/business/resources/reports/dbir/).

## Play selection

- New CISO at Tier 1 hospital within 180 days: [[../../40_Plays/sivan-peer-intro]]. Ran at [[../../10_Accounts/FMOL Health]].
- Post-settlement / post-breach window: [[../triggers/settlement-event]]. Live at [[../../10_Accounts/Medusind]].
- Non-responsive healthcare after first meeting: pattern-break at day 14. Object: [[../methodology/objections]] #10.
- Inbound healthcare web visitor: Centra won at $270K through direct traffic. RB2B + [[../../40_Plays/hunt/intent-signal-hunt]] are the watch.

## Accounts in play

- [[../../10_Accounts/Medusind]] — PE-backed RCM, post-settlement, single-thread risk.
- [[../../10_Accounts/FMOL Health]] — multi-facility nonprofit, new CISO (Britani Tullier) July 2025.
- [[../../10_Accounts/GenomOncology]] — precision oncology SaaS, compliance-adjacent.

## Closed-won references

- Centra Health ($270K, 137 days, inbound) — fastest healthcare win.
- WellStar Health System ($172K, 553 days) — long-cycle enterprise hospital system.
- Premera Blue Cross ($170K, 169 days) — health insurance mid-cycle.
- Christiana Care Health ($60K, Sivan-sold) — peer-intro lineage.

## Closed-lost references (pattern library)

Montefiore, Cleveland Clinic, Main Line Health, Hoag, Healthfirst, Temple Health, Brighton Health Plan, Smile Brands, Delta Dental. Common thread: 1-2 contacts, no named EB, no forcing event. See [[../playbook/closed-lost-patterns]] healthcare section.

## Language that lands

- "Your analysts spend 40+ hours a week on manual framework mapping. One of our customers called it the spreadsheet-from-hell to automation shift." (verbatim from [[../product/quotes]])
- "If OCR audits your risk analysis next quarter, what does your answer look like?" (Phase 3 hook)
- "The HIPAA Security Rule update is targeted for May 2026 finalization. Asset inventory + network map + 72-hour restoration are the three items most programs aren't instrumented for." (NPRM hook)

## Cross-references

- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../product/positioning]]
- [[../product/quotes]]
- [[../product/features]]
- [[../methodology/objections]]
- [[../industry/regulatory-calendar]]
- [[../industry/breach-report-synthesis]]
- [[../triggers/exec-hire]]
- [[../triggers/settlement-event]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../90_Templates/tpl-ciso-cold]]
