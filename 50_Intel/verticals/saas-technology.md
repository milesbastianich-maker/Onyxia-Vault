---
type: intel
subtype: vertical
vertical: saas-technology
source: closed-won corpus + SOC 2 enterprise gating + SEC cyber rule + CPRA + HubSpot density analysis 2026-04-22
created: 2026-04-22
tags: [intel, v/saas, v/technology]
---

# SaaS / Technology

3 wins (Radiant Logic $165K, CCC Intelligent Solutions $120K, Elite Technology $30K — combined $315K). 1,267 Computer Software companies in HubSpot — biggest pool by far. SEC cyber rule + SOC 2 enterprise gating + CPRA audit mandate create layered compliance pressure for SaaS CISOs. Security-vendor exclusion guardrail applies.

See [[../playbook/closed-won-patterns]], [[../../00_Index/icp]], and [[../hunt-research/2026-04-22-closed-won-nonhealthcare-synthesis]].

## Regulatory surface

- **SOC 2 Type II enterprise gating (market standard, not a dated deadline).** Enterprise procurement teams now require SOC 2 reports before vendor approvals. When public-company customers file their own 10-K cyber disclosures, they must describe vendor risk management — SOC 2 reports from SaaS vendors become the evidence artifact embedded in those filings. Source: [SecureLeap SOC 2 for SaaS](https://www.secureleap.tech/blog/soc-2-compliance-checklist-saas).
- **SEC Cybersecurity Disclosure Rule (public SaaS only).** Same 8-K/10-K obligations as public REITs. CISOs at publicly traded SaaS companies have board-reporting exposure — the exact same pressure as healthcare/financial-services. Source: [BlueRadius SEC Mid-Market Guide 2026](https://blueradius.io/sec-cybersecurity-disclosure-rules-mid-market-2026).
- **CPRA / California Privacy Rights Act (effective Jan 2026).** Cybersecurity audit mandate for businesses processing 250K+ CA consumer personal information. Independent audits required; phased first certifications due April 1 in 2028-2030 based on revenue tier. SaaS companies with large California user bases are scoping now. Source: [Secure Privacy CCPA 2026](https://secureprivacy.ai/blog/ccpa-requirements-2026-complete-compliance-guide).
- **EU DORA (effective Jan 17, 2025).** Digital Operational Resilience Act. US SaaS vendors serving EU financial institutions (banks, insurers, asset managers) must meet DORA's ICT risk management + incident reporting requirements. B2B SaaS with European fintech/bank customers are pulled in as "critical ICT third-party providers."

## What SaaS CISOs care about

1. **Own board-reporting posture.** SaaS CISOs face the same board pressure as any other CISO — especially at public companies. Onyxia consolidates multi-framework posture into one board-ready view.
2. **Customer due diligence evidence.** Enterprise customers now require SOC 2 Type II and ask vendors to narrate their control environment during procurement. Onyxia generates that narrative.
3. **Cascading compliance (SOC 2 + CPRA + DORA simultaneously).** Multi-framework overlap is the operational burden. Manual tracking across 3+ frameworks is broken.
4. **Vendor/supply-chain risk.** SaaS companies are themselves supply-chain risk for their customers. Demonstrating upstream control over third parties matters for enterprise deals.

## Who wins the meeting

Primary: CISO, VP Security.
Secondary thread: CTO, GC, CFO (at public companies).
The Radiant Logic meta-pattern: CCC and Radiant both bought Onyxia for their OWN compliance posture — not to sell to customers. That is the SaaS use-case. Start with the CISO's internal problem, not a resale play.

## Competitive context

SaaS companies skew toward modern GRC tools (Drata, Vanta, Secureframe). These handle SOC 2 automation well but are control-checklist tools, not board-reporting platforms. Onyxia's differentiation: translates the compliance checklist output into a board narrative, risk-quantified, continuously updated. Vanta/Drata tell you whether a control is green — Onyxia tells the board what it means in dollar terms.

See [[../competitors/drata]] and [[../competitors/vanta]].

## Play selection

- Public SaaS company approaching 10-K filing window: SEC-hook opener.
- SaaS CISO whose enterprise customer just asked for SOC 2 evidence in a deal: vendor-risk-cascade angle.
- New CISO hire at a SaaS company (trigger event within 90 days): exec-hire play. See [[../triggers/exec-hire]].
- Radiant Logic pattern: identity/security-adjacent SaaS that handles CUI or regulated data — compliance-for-own-posture.

## Security-vendor exclusion guardrail

Per [[../../00_Index/icp]]: do NOT target companies whose primary business is security software (Ivanti, Rubrik, SolarWinds, Trustwave, Broadcom, Palo Alto, CrowdStrike). These are either competitors or create co-sell conflict. Target SaaS-that-sells-to-enterprise, not security-vendor.

Exclusion check: if the company's primary product IS cybersecurity → skip. If the company uses cybersecurity to run their business → viable.

## HubSpot targets

1,267 Computer Software companies in CRM. First-page sample skews small (Argano, LTS, MetTel — system-integrator type). Filter requirements:
- 500+ employees (surface enterprise-class SaaS)
- Primary industry = Computer Software, NOT security software
- Revenue $50M+ (Onyxia's ACV floor is relevant here)

## Closed-won references

- Radiant Logic ($165K, Brad, identity SaaS — bought for own compliance posture, meta-use-case)
- CCC Intelligent Solutions ($120K, Maura, InsurTech SaaS — regulated customer data)
- Elite Technology ($30K, Maura, generic tech SaaS)
