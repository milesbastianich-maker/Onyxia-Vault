---
type: intel
subtype: icp
source: derived from 23 closed-won deals + 113 closed-lost deals
created: 2026-04-21
tags: [intel]
---

# Onyxia ICP (Derived from Closed-Won Playbook)

This is the queryable ICP. Every hunt filters through this.

## Tier 1 (closed-won concentration)

**Vertical** — healthcare, financial services, manufacturing (especially aerospace/defense/CMMC), critical infrastructure, identity-adjacent SaaS vendors.
**Employee count** — 500 to 10,000.
**Revenue** — $100M to $5B.
**Geography** — United States (primary), UK/EU (secondary).
**Compliance surface** — multi-framework (HIPAA + SOC 2, SEC + NYDFS, CMMC + ITAR + NIST, PCI-DSS, GDPR across jurisdictions).
**Security maturity** — already has SIEM + EDR + DLP. Needs the layer above.
**Stack** — CyberArk, CrowdStrike, Microsoft E5, Splunk, NIST-aligned frameworks are friendly signals.

## Persona

**Primary:** CISO, VP Security, CSO
**Secondary champions:** GRC Director, Privacy Officer, Head of Security Ops, Director of Risk
**Economic buyer:** CFO, CIO, General Counsel (healthcare + regulated), CEO for smaller orgs

## Trigger events (ranked by conversion signal)

1. **Recent breach / incident** — strongest signal. Settlement payouts, disclosure filings, class-action news. See Medusind ($5M settlement paid 2026-04-10).
2. **New CISO or VP Security hire** (within 90-180 days). Strategy-setting window.
3. **Public SEC cyber disclosure / 8-K on incident** — regulated filers only.
4. **M&A activity** — post-close security integration is a budget-release event.
5. **Funding round (Series B+)** — growing orgs hit compliance scaling pain.
6. **New CMMC, NYDFS 500, HIPAA Security Rule, or DORA deadline** — regulatory forcing function.
7. **Exec team expansion** — new GC / CFO often followed by vendor review.

## Hard exclusions

See `~/.claude/projects/-Users-milesbastianich/memory/reference_onyxia_exclusions.md` for the complete do-not-contact list (Solomon Rozental, Hornblower, etc.).

Also exclude:
- Security vendors themselves (Ivanti, Rubrik, SolarWinds, Trustwave, Broadcom) unless explicit co-sell partner angle
- Israeli-HQ entities per Sivan's 2026-04-15 guidance ("even if they like it they won't commit and they are cheap")

## De-prioritize (not excluded, just low-probability)

- BigLaw without a warm intro (pattern: non-responsive except via peer referral. See Simpson Thacher as the one win after 577-day cycle)
- Companies with < 500 employees (deal size too small)
- Companies > $10B revenue without a named champion (procurement cycle exceeds our bandwidth)
- VC / private equity firms (Vista won, but pattern is weak; usually noise)

## Fit scoring rubric (1-5)

**5 — Ideal:** Tier 1 vertical + 500-10K employees + fresh trigger event + named champion at CISO/VP Sec + multi-framework compliance surface
**4 — Strong:** Tier 1 vertical + 500-10K employees + any trigger event OR named champion
**3 — Worth it:** Tier 1 vertical + size fit, no trigger yet
**2 — Weak:** Adjacent vertical OR size edge (150-500 or 10K-15K)
**1 — Pass:** Excluded, non-ICP, or in another rep's territory

## ZoomInfo query template (Tier 1 hunt)

```
managementLevel: "C Level Exec,VP Level Exec"
jobTitle: "CISO OR Chief Information Security OR VP Security OR Head of Security OR Chief Privacy OR GRC Director"
country: "United States"
employeeRangeMin: 500
employeeRangeMax: 10000
revenue: "$100M - $5B"
primaryIndustriesOnly: true
industryCodes: (healthcare | financial | manufacturing | critical infra codes — via lookup)
positionStartDateMin: <180 days ago>    # new-CISO filter
contactAccuracyScoreMin: 85
requiredFields: "email"
excludePartialProfiles: true
```

Tune the filters per hunt mode.
