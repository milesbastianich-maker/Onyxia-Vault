---
type: account
company: Starboard Group
domain: starboardgroup.com
vertical: other
account_tier: 3
hubspot_id: _unknown - research needed_
arr_target: 50000
stage: poc
status: active
created: 2026-04-21
last_touch: 
next_action: pull HubSpot champion + validate size fit
next_action_date: 2026-04-24
metrics: 
economic_buyer: _unknown - research needed_
champion: _unknown - research needed_
paper_process: _unknown - research needed_
tags: [account, "#active", "#stage/poc"]
---

# Starboard Group

## Why they'd buy
Multi-concept franchisee: 98 Wendy's + 6 McAlister's + 15 Subway + 5 Fuzzy's + 24 CiCi's + 34 Applebee's restaurants across multiple states (AL, FL, IL, MO, WI, AR, KY, LA, TX). Founded 1999. ~114 corporate employees per Feb 2026. Heavy PCI-DSS exposure at store level, payroll + HR data across ~thousands of store staff. The franchise-operator cyber story: you inherit brand-mandated tooling from each franchisor (Wendy's, Applebee's, etc.) and then have to prove your own posture to each.

## Fit
Tier 3. Employee count in corporate is small (~114), but operational footprint across 180+ stores is real. Off-vertical per [[../50_Intel/icp]] (hospitality/QSR is not Tier 1). Score: 2. Saving grace: Chipotle closed at $80K per [[../50_Intel/playbook/closed-won-patterns]] — QSR franchise is a proven pattern even if small.

## Note from vault
Prior Solomon Rozental outreach referenced a "from Starboard" template he modified to book Well Health. Messaging is already productized internally.

## MEDDPICC
- **Metrics** — _unknown - research needed_. Candidate: PCI audit hours per brand, franchise-compliance reporting to 6 different franchisors, store-level POS security posture.
- **Economic buyer** — _unknown - research needed_. Likely CEO (the founder who started with 5 restaurants in PA) or CFO.
- **Decision criteria** — _unknown - research needed_
- **Decision process** — _unknown - research needed_. Franchise operator decision-making tends to be centralized at HQ.
- **Paper process** — _unknown - research needed_. Lighter than enterprise — franchise operators don't run heavy procurement.
- **Identified pain** — _unknown - research needed_. Hypothesis: proving posture to 6 different franchisor cyber teams + PCI auditors.
- **Champion** — _unknown - research needed_. Stage "Decision Maker Bought In" without name is a pipeline-hygiene gap.
- **Competition** — _unknown - research needed_. Likely "do nothing" + brand-mandated tools.

## Threads
_No contacts on file. Pull from HubSpot._

## Deal
- Amount: $50,000
- HubSpot stage: Decision Maker Bought In (per backfill label)
- HubSpot ID: _unknown - research needed_
- Close target: _unknown - research needed_

## Timeline
- 2026-04-21: stub created from HubSpot backfill
- 2026-04-22: vault densification. Confirmed as multi-concept franchise operator (~98 Wendy's + 6 other brands + ~180 total stores). ~114 corporate employees. HubSpot access needed to pull contacts

## Next
- [ ] Pull HubSpot: deal ID, owner, dealstage, contacts, last activity
- [ ] Validate stage vs named champion gap
- [ ] ZoomInfo enrich CEO, CFO, Head of IT
- [ ] Decide whether $50K ARR is realistic for a ~114-corporate-employee franchisee

## Intel
Based in Oak Brook IL per public records (or Lombard). CEO founded company in 1999 with 5 PA restaurants. Google Cloud Platform + Microsoft 365 + Microsoft Dynamics GP in tech stack. Historic compliance issue: a Starboard-affiliated Wendy's franchisee was hit with a $7.1M judgment for harassment + PPP fraud (QSR Magazine). Whether that entity is the same legal operator in HubSpot needs confirmation.

## Pattern match
Closest win: Chipotle ($80K, 495-day cycle). QSR franchise cyber closes, but slowly. Plan for 12+ months per [[../50_Intel/playbook/closed-won-patterns]] "large enterprise, procurement-heavy verticals, non-linear but persistent" pattern. Starboard is smaller than Chipotle but pattern is comparable.

## Risk flags
- Corporate employee count (~114) is near the 100-employee floor per exclusions reference.
- Off-vertical.
- Single-threaded.

## Links
- [[../50_Intel/verticals/other]]
- [[../50_Intel/personas/ciso]]
- [[../50_Intel/playbook/closed-won-patterns]]
- [[../50_Intel/playbook/closed-lost-patterns]]
- [[../50_Intel/icp]]
- [[../50_Intel/triggers/pci-dss]]
