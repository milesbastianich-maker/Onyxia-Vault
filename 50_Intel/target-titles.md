---
type: intel
category: icp
status: canonical
last_updated: 2026-04-28
source: Miles direct (2026-04-28)
---

# Onyxia Target Titles (canonical)

Authoritative list of titles to target for Onyxia outbound. All hunts (HubSpot search, ZoomInfo search_contacts, vertical sweeps) MUST use this list as the title filter. Anything outside this list is out of scope unless Miles explicitly authorizes a one-off exception.

The list is tiered by buying authority and outreach posture, not by importance. All four tiers are in scope.

## Tier 1: Economic Buyer (signs the contract)

Direct decision-makers. Single-thread these for closing motion. Default targets for executive dinners and direct EB outreach.

- Chief Information Security Officer (CISO)
- Chief Security Officer (CSO)
- Chief Risk Officer (CRO)
- VP Information Security
- VP Cybersecurity
- VP Cyber Security
- VP IT Security
- VP Security
- SVP Information Security
- SVP Cybersecurity
- Head of Information Security
- Head of Cybersecurity
- Head of Cyber
- Head of Security

## Tier 2: Senior Influencer (co-signs, champions to EB)

Strong influence on the EB. Multi-thread alongside Tier 1. Often the operational owner who runs the eval even when the CISO signs.

- Deputy CISO
- BISO (Business Information Security Officer)
- VP Governance Risk Compliance (VP GRC)
- VP Cyber Risk
- VP IT Risk
- VP Technology Risk

## Tier 3: Champion (drives the eval, brings the EB in)

Department-level leaders who run vendor selection. Best targets for first-touch when the CISO is unreachable. Use to multi-thread up to the EB.

- Director Information Security
- Director Cybersecurity
- Director Cyber Security
- Director IT Security
- Director Security
- Director Security Operations
- Director SecOps
- Director Security Architecture
- Director Security Engineering
- Director Security Program
- Director GRC
- Director Governance Risk Compliance
- Director Cyber Risk
- Director IT Risk
- Director Information Risk
- Director Technology Risk
- Head of GRC
- Head of Cyber Risk
- Head of IT Risk

## Tier 4: Senior Champion (pre-EB, scaling toward signing authority)

Senior individual contributors and program leads who often sit one level below an EB. Treat as Tier 3 with slightly higher seniority weight.

- Senior Director Information Security
- Senior Director Cybersecurity

## Out of scope (do NOT target)

These titles do not have buying authority and are noise in cold outreach. Do not surface in hunts.

- Manager / Senior Manager (any security or risk function)
- Analyst (SOC Analyst, Security Analyst, GRC Analyst, etc.)
- Engineer (Security Engineer, IAM Engineer, Cloud Security Engineer, etc.)
- Architect at non-Director level (Director-level architects ARE in Tier 3)
- Lead, Specialist, Coordinator
- Compliance Officer below Director level
- Privacy Officer (separate function, distinct buying motion)

## Use in the drafter

Per the v2 cold email rules, tone calibration shifts by tier:

- **Tier 1:** strategic priority tie required (10-K, earnings call, board statement). Plain. No tool talk.
- **Tier 2:** co-sign framing. Reference the EB by name when known. Risk and reporting language.
- **Tier 3:** champion framing. Slightly more technical. Can reference specific tools or integrations. Map their pain to what their CISO will care about.
- **Tier 4:** treat as Tier 3 with senior weight. They are usually a year from a CISO seat themselves.

## Hunt enforcement

Every hunt prompt must include:

```
Title filter: must match a title in ~/ObsidianVault/50_Intel/target-titles.md (Tier 1, 2, 3, or 4 as specified by the requestor). Reject anything else.
```

If a hunt requestor does not specify a tier, default to all four tiers and rank Tier 1 first.
