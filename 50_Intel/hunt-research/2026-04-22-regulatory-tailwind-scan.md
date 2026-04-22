---
type: intel
subtype: hunt-research
date: 2026-04-22
tags: [intel, hunt-research]
---

# Regulatory Tailwind Scan — 6 Expansion Verticals

Phase 3 of the vertical-expansion research. For each vertical: compliance driver, effective date, scope, and Onyxia mapping.

---

## 1. Real Estate / REITs

**Driver:** SEC Cybersecurity Disclosure Rule (adopted July 2023)
**Enforcement status:** Fully in effect since December 2023. FY 2026 SEC examination priorities explicitly flag cyber disclosure quality.
**Scope:** All SEC registrants — including publicly traded REITs and commercial real estate operators filing 10-Ks.
**Requirements:**
- Form 8-K Item 1.05: material cybersecurity incident disclosure within 4 business days of materiality determination.
- Form 10-K: annual disclosure of cyber risk management program, board oversight, and management role/expertise.

**Onyxia mapping:** Direct. Onyxia's board-reporting layer produces exactly the narrative public REITs must put into 10-K Item 106. REIT boards ask the same governance questions that the SEC rule codifies. The pitch is: "Your 10-K cyber section is a living document — Onyxia is the reporting infrastructure behind it."

**Urgency signal:** SEC exam teams are now reviewing whether 8-K and 10-K disclosures are substantive or boilerplate. Enforcement citations are rising. 2026 is the first full exam cycle under the rule.

**Sources:**
- [SEC.gov Rule S7-09-22](https://www.sec.gov/rules-regulations/2023/07/s7-09-22)
- [BlueRadius SEC Mid-Market Guide 2026](https://blueradius.io/sec-cybersecurity-disclosure-rules-mid-market-2026)
- [Shulman Rogers SEC FY2026 Exam Priorities](https://www.shulmanrogers.com/legal-alert-sec-releases-fy-2026-examinations-priorities-for-rias-and-others/)

---

## 2. Retail / Hospitality

**Driver:** PCI-DSS 4.0.1 (PCI Security Standards Council)
**Enforcement status:** All requirements mandatory as of March 31, 2025. 2026 is the first full compliance year with no grace periods, no exceptions, no version 3.2.1 fallback.
**Scope:** Any merchant accepting card payment — retail, QSR, hospitality, franchise operators.
**Requirements:**
- Requirements 6.4.3 and 11.6.1 (new): real-time visibility into payment-page scripts to prevent e-skimming.
- Continuous compliance model — controls must be in place year-round, not assembled for annual audit.
- Quarterly external scans + annual penetration testing mandatory.
- Non-compliance: acquiring banks levy $5K–$100K/month.

**Onyxia mapping:** Multi-location/franchisee scorecard problem. Chipotle ($80K win) was exactly this — brand-risk + franchisee reporting at scale. Onyxia's continuous monitoring layer maps to PCI's continuous compliance requirement. The Starboard Group pipeline ($150K) is live confirmation. Position as: "You're no longer compliant once a year — PCI 4.0.1 means you need to show it continuously. Onyxia is the reporting layer that proves ongoing posture to your acquiring bank and board."

**Urgency signal:** March 31 2025 deadline already passed. Any retail CISO who hasn't operationalized continuous monitoring is currently non-compliant and accumulating monthly fines.

**Sources:**
- [UpGuard PCI DSS 4.0.1 Guide 2026](https://www.upguard.com/blog/pci-compliance)
- [Feroot PCI DSS 4.0.1 CISO Checklist](https://www.feroot.com/blog/pci-compliance-checklist-for-cisos/)
- [PCI Security Standards Council](https://www.pcisecuritystandards.org/)

---

## 3. Legal Services / BigLaw

**Driver:** ABA ethics opinions + state bar mandatory cyber CLE + NY SHIELD Act
**Enforcement status:** Multiple overlapping pressures active in 2026.
**Scope:** Law firms handling client data (which is all of them).

**Requirements — layered:**
1. **NYC Bar Formal Opinion 2024-3** — detailed ethical obligations when a firm experiences a cybersecurity incident. Breach response, client notification, and duty to protect.
2. **NY Cybersecurity CLE (2026)** — mandatory 1-credit cybersecurity requirement as a hard-stop for NY attorney biennial registration. Creates floor of cyber awareness across firm leadership.
3. **NY SHIELD Act + RPC 1.1(c) + RPC 1.6** — reasonable security for personal information is an ethical obligation. NYDFS-adjacent firms must move to active EDR, not passive firewalls.
4. **ABA Formal Opinion 512 (July 2024)** — AI tools ethics (not cyber-specific) but raises new attack surface: law firm AI use = new data-exfiltration risk + client-confidentiality exposure.
5. **California CPRA (Jan 2026)** — cybersecurity audits for large firms processing 250K+ CA consumers' data.

**Note on ABA 512:** This opinion covers generative AI ethics, not cybersecurity directly. The cyber baseline opinions are ABA 477R and 483. Do not over-index on "512 = cyber" in messaging.

**Onyxia mapping:** Firm partner/GC board-equivalent reporting. Simpson Thacher ($60K, 577 days) closed on peer-intro driven by a partner needing to show risk posture to the executive committee. Position as: "Your managing partners now have the same SEC-adjacent board accountability questions that corporate CISOs have had for 3 years. Onyxia is the reporting layer that answers them."

**Caveat:** 577-day cycle. This vertical needs a 12+ month pipeline view. Good for long-arc sequences, not this-quarter plays.

**Sources:**
- [NYC Bar Formal Opinion 2024-3](https://www.nycbar.org/reports/formal-opinion-2024-3-ethical-obligations-relating-to-a-cybersecurity-incident/)
- [NYSBA Cybersecurity CLE Requirements](https://nysba.org/cybersecurity-cle-requirements-nysba/)
- [Consult CRA NYC Law Firm IT Compliance 2026](https://www.consultcra.com/2026-it-compliance-checklist/)

---

## 4. SaaS / Technology

**Driver:** SOC 2 enterprise gating + SEC cyber rule (public SaaS) + CPRA audit mandate
**Enforcement status:** SOC 2 is now table stakes — enterprise deals require it, not request it. SEC rule active. CPRA phased audits begin 2028-2030 but scoping happens now.
**Scope:** Any B2B SaaS company with enterprise customers (especially public company customers) and/or 250K+ CA user base.

**Requirements:**
- **SOC 2 Type II:** Enterprise customers now require it before procurement. When public-company customers file their own 10-K cyber disclosures, they must describe vendor risk management — SOC 2 reports become the evidence artifact.
- **SEC cyber rule (public SaaS only):** Same 8-K/10-K obligations as REITs. Public SaaS companies (CCC, Radiant Logic pre-exit) have CISO-level board reporting pressure.
- **CPRA (California):** Businesses processing 250K+ CA consumers must conduct independent cybersecurity audits. Phased certification schedule: first certifications due April 1, 2028-2030 based on revenue tier.
- **EU DORA (Digital Operational Resilience Act):** Effective January 17, 2025 for EU financial-sector SaaS vendors. US SaaS companies with EU fintech/bank customers are pulled in.

**Onyxia mapping:** The downstream cascade effect. SaaS CISOs need to show their own board a clean risk posture *and* be able to produce SOC-2-grade evidence for enterprise customer due diligence. Onyxia consolidates both. The Radiant Logic pattern ($165K): identity SaaS bought Onyxia for its OWN compliance reporting, not for external sale. That is the SaaS meta-use-case.

**Guardrail:** Filter out security vendors (Ivanti, Rubrik, SolarWinds, Broadcom, Trustwave) per icp.md exclusion list. Target is "SaaS-sells-to-enterprise" not "security-software-primary-business."

**Sources:**
- [SecureLeap SOC 2 for SaaS 2026](https://www.secureleap.tech/blog/soc-2-compliance-checklist-saas)
- [BlueRadius SEC Mid-Market Guide 2026](https://blueradius.io/sec-cybersecurity-disclosure-rules-mid-market-2026)
- [Secure Privacy CCPA 2026 Guide](https://secureprivacy.ai/blog/ccpa-requirements-2026-complete-compliance-guide)

---

## 5. Higher Education

**Driver:** GLBA Safeguards Rule + NIST 800-171 Rev 3 (DoD research) + FERPA
**Enforcement status:** GLBA compliance required since June 6, 2023 for all Title IV institutions. NIST 800-171 Rev 3 DoD contractor implementation expected late 2026–early 2027.
**Scope:** All Title IV institutions (GLBA). Research universities with DoD contracts face CMMC-adjacent requirements.

**Requirements:**
- **GLBA Safeguards Rule (FTC, Title IV):** All universities accepting federal student aid must maintain a written information security program (WISP), conduct periodic risk assessments, enforce access controls, test safeguards, and oversee third-party vendors. DoE enforces via Single Audit + SAIG Agreement.
- **NIST 800-171 Rev 3:** Universities handling Controlled Unclassified Information (CUI) from DoD research contracts must implement NIST 800-171 controls. DoD April 2025 memo assigns ODP values for Rev 3 — rulemaking expected late 2026–early 2027. Research universities that fail face loss of DoD contracts.
- **FERPA:** Student record privacy. FTC ruling: FERPA compliance satisfies GLBA's privacy requirement but NOT security requirement — both must be addressed separately.
- **State tightening:** NY, CA, and TX have enacted or are enacting university-specific breach notification timelines.

**Onyxia mapping:** University CISO + CIO + Board of Trustees reporting. Research universities have an IT/compliance office that maps to Onyxia's multi-framework layer (GLBA + NIST 800-171 + FERPA simultaneously). Pitch angle: "Your IT compliance team is running three frameworks at once with manual spreadsheets. Onyxia consolidates to one board-ready view." HubSpot depth: 286 Higher Ed companies.

**0 closed-won today.** This is exploratory territory. First meeting should be peer-call via Sivan (university CISO network). Do not cold-open without a warm signal.

**Sources:**
- [Student Privacy Compass GLBA Higher Ed](https://studentprivacycompass.org/higher-education-compliance-with-updates-to-the-glba-safeguards-rule/)
- [UpGuard NIST 800-171 Rev 3 2026](https://www.upguard.com/blog/nist-800-171-rev3)
- [Holland & Knight DoD NIST 800-171 Rev 3 ODPs](https://www.hklaw.com/en/insights/publications/2025/05/dod-publishes-organization-defined-parameters-for-nist-sp)
- [Forvis Mazars Research University IT Compliance](https://www.forvismazars.us/forsights/2025/11/why-research-universities-must-get-serious-about-it-compliance)

---

## 6. Defense / Aerospace

**Driver:** CMMC 2.0 Phase 2 — November 10, 2026 deadline
**Enforcement status:** Hard deadline. No grace period announced. C3PAO assessor slots already booking into late 2026 and 2027.
**Scope:** ~220,000 Defense Industrial Base (DIB) contractors handling CUI. Most will require Level 2 certification.

**Requirements:**
- **CMMC Level 2 certification** (C3PAO-assessed): mandatory for contracts involving CUI starting November 10, 2026.
- Readiness journey = 12–14 months: gap analysis → remediation → documentation → pre-assessment → C3PAO engagement.
- DoD April 2025 memo established ODP values for NIST 800-171 Rev 3 — the compliance framework underlying CMMC Level 2.
- ~1% of affected contractors are currently fully prepared. C3PAO pipeline is severely constrained.

**Onyxia mapping:** CMMC certification requires documented evidence of controls — not just technical implementation. Onyxia's continuous monitoring and reporting layer is the documentation artifact that C3PAO assessors and contracting officers review. Pitch: "CMMC isn't just a technical checklist — it's a documentation audit. Onyxia builds the reporting layer that proves your controls are live and continuous, not assembled for the assessment."

**Urgency:** November 10, 2026 is 6.5 months from today. Any contractor that hasn't started their readiness journey is almost certainly going to miss the deadline. The sense of urgency is the hook — NOT a regulatory education play.

**HubSpot depth:** 83 defense companies. Samples: Mercury Systems, General Dynamics, MITRE, JHU Applied Physics Lab, Ducommun.
**0 closed-won today.** Exploratory. But the deadline is the single strongest urgency signal of all 6 verticals.

**Sources:**
- [CMMC Phase 2 November 2026 Deadline — RidgeIT](https://www.ridgeit.com/cmmc-phase-2-deadline-november-2026/)
- [Secureframe CMMC 2.0 Timeline](https://secureframe.com/hub/cmmc/proposed-final-rule)
- [CRC Cloud CMMC Countdown](https://www.crccloud.com/cmmc-2-0-compliance-countdown-what-small-defense-contractors-need-to-do-before-november-2026)

---

## Summary table

| Vertical | Primary Driver | Deadline / Status | Urgency (1-5) | Onyxia Fit |
|---|---|---|---|---|
| Real Estate | SEC cyber disclosure rule | Active, 2026 exam cycle | 3 | Board reporting for public REITs |
| Retail/Hospitality | PCI-DSS 4.0.1 | Active since Mar 2025 | 4 | Multi-location continuous monitoring |
| Legal Services | NYC Bar + NY CLE + SHIELD | Active 2026 | 2 | Partner/exec committee reporting |
| SaaS/Technology | SOC 2 gating + SEC + CPRA | Active / audit 2028 | 3 | Own compliance + customer evidence |
| Higher Education | GLBA + NIST 800-171 Rev 3 | GLBA active, NIST late 2026 | 3 | Multi-framework board reporting |
| Defense/Aerospace | CMMC Phase 2 | **Nov 10, 2026** | **5** | CMMC documentation artifact |
