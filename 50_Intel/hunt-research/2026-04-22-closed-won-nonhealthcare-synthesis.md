---
type: intel
subtype: hunt-research
date: 2026-04-22
tags: [intel, hunt-research]
---

# Closed-Won Synthesis — Non-Covered Verticals

Pulled from `../playbook/closed-won-patterns.md`. Only wins outside the 4 already-vault-filed verticals (healthcare, financial-services, manufacturing, critical-infrastructure).

## Real Estate

| Deal | Amount | Owner | Pattern |
|---|---|---|---|
| Gaia Real Estate | $37,500 | Sivan | Small real-estate operator, Sivan-personal network |
| Silverstein Properties | $10,000 | Sivan | NYC CRE, relationship sale |

**Win angle:** both sold by Sivan personally. Indicates real estate closes via peer-intro more than enterprise motion. Deal sizes are smaller than healthcare norm. Board-reporting language still applies (REIT boards ask the same cyber-disclosure questions SEC cyber rule demands).

**Churn signal:** Brookfield Properties is in the "Churned" bucket (converted and left). Worth a separate why-did-they-leave review before re-prospecting.

**HubSpot pairing:** 243 real-estate companies in CRM. Non-Gaia/Silverstein companies = 241 potential targets. Sample companies surfaced: Howard Hanna, Douglas Elliman, Sun Communities, KBS. These are operators + REITs.

**Verdict: FILE-WORTHY.** 2+ wins, meaningful CRM depth, SEC cyber rule tailwind for public REITs.

---

## Retail / Hospitality

| Deal | Amount | Owner | Pattern |
|---|---|---|---|
| Chipotle Mexican Grill | $80,000 | Maura | QSR, public company, brand-risk driven |
| CWT (Corporate Travel) | $100,000 | Brad | Travel/hospitality adjacency |
| Starboard Group (pipeline, not closed) | $150K deal-in-flight | Miles | Hospitality franchise |

**Win angle:** Chipotle was a brand-risk + franchisee reporting pattern. CWT sits in the B2B-travel-management slice. Common thread: multi-location consumer-facing businesses with payment-data surface + franchisee/location scorecard problem.

**HubSpot pairing:** 206 retail companies. Samples skew toward larger operators: Circle K (46K employees), El Corte Inglés (90K), Mohawk, American Woodmark. Good enterprise-class depth.

**Regulatory tailwind:** PCI-DSS 4.0.1 future-dated requirements became effective March 31 2025 per PCI Council, so ICS already compliant. Next real compliance event is ongoing breach-disclosure exposure, not a single date.

**Verdict: FILE-WORTHY.** 1 direct + 1 adjacent win (CWT) + live Starboard pipeline. PCI context is already past the deadline so position as ongoing maturity, not deadline-driven.

---

## Legal Services (BigLaw)

| Deal | Amount | Owner | Pattern |
|---|---|---|---|
| Simpson Thacher & Bartlett | $60,000 | Brad | 577-day cycle, peer-intro driven |

**Win angle:** Per `closed-won-patterns.md`, Simpson Thacher is the ONE BigLaw win in the corpus. 577-day cycle signals BigLaw does not buy fast and does not buy cold. Required a named warm introduction.

**HubSpot pairing:** 141 legal_services companies. Filtering out municipalities (Elk Grove PD, City of Lakewood, Luxembourg Govt — mis-tagged in HubSpot) narrows the actionable BigLaw count. Stephenson Harwood + Smith Gambrell Russell are real BigLaw in the sample.

**Regulatory tailwind:** 2026 ABA Formal Opinion 512 raises cyber-duty for lawyers handling client data. State bar updates in NY + CA raise minimum-security standards for law firms.

**Verdict: FILE-WORTHY but DEPRIORITIZED.** 577-day cycle is expensive for an AE with quarterly quota pressure. Worth a file for record + pipeline-filler plays, not a primary vertical push.

---

## SaaS / Technology (non-security vendor)

| Deal | Amount | Owner | Pattern |
|---|---|---|---|
| Radiant Logic (Identity SaaS) | $165,000 | Brad | Identity vendor, sells to security teams, bought Onyxia for own compliance |
| CCC Intelligent Solutions (InsurTech SaaS) | $120,000 | Maura | Mid-market SaaS with regulated customer data |
| Elite Technology (Tech/SaaS) | $30,000 | Maura | Generic tech SaaS, smaller deal |

**Win angle:** 3 related wins in the "SaaS-company-with-enterprise-customers" pattern. Radiant Logic is borderline — they are a security vendor but bought for their OWN compliance posture (meta-use-case). CCC + Elite are straight-enterprise SaaS.

**HubSpot pairing:** 1,267 Computer Software companies. First-page sample skews toward system integrators + smaller shops (Argano, LTS, MetTel). Real enterprise SaaS likely requires employee-count filter (500+) to surface. Exclusion list per `icp.md` bars Onyxia from targeting security vendors directly without a clear co-sell angle.

**Verdict: FILE-WORTHY with guardrail.** Biggest HubSpot pool by far. 3 wins in the pattern. Must filter out security vendors (Ivanti, Rubrik, SolarWinds, Trustwave, Broadcom + the broader security-software-primary-industry bucket). Position as SaaS-sells-to-enterprise-customers pattern, not SaaS-vendor pattern.

---

## Wins that stay singletons (not file-worthy alone)

- AXNY Group — Staffing, $60K, Brad. Pattern: multi-location staffing firms with franchisee payroll data. Insufficient precedent alone. Footnote under future "Professional Services" if that vertical ever hits 2+ wins.
- Vista Equity Partners — PE, $37.5K, Brad. PE firms under new SEC marketing + custody rules. 3 HubSpot companies only (sparse). Keep as a reactivation-sweep target, no file.
- Adama — Agri-Chemicals, $16K, Sivan. Smallest direct deal. Agri-chem is manufacturing-adjacent; footnote under manufacturing.md if it comes up again.

## Verticals to carry into Phase 3 (regulatory scan)

1. Real Estate (REIT / SEC cyber rule)
2. Retail / Hospitality (ongoing PCI-DSS maturity + brand-risk)
3. Legal Services / BigLaw (2026 ABA cyber rules + state bar updates)
4. SaaS / Technology (SOC 2 + state privacy laws + SEC disclosure for public SaaS)
5. Higher Education (FERPA + NIST 800-171 for research; state-level tightening)
6. Defense/Aerospace (CMMC Phase 2 rollout)
