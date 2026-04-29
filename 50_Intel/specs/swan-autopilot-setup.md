---
type: intel
subtype: spec
source: Miles / session 2026-04-29
created: 2026-04-29
status: live
tags: [intel]
---

# Swan AI Autopilot — Program Setup

Automated outbound prospecting agent. Runs daily, finds qualifying companies, researches them, identifies the right contact, drafts personalized outreach, and drops tasks for Miles's review. Nothing sends without approval.

## What Swan is

External AI prospecting system (separate from n8n workflows). It runs on its own schedule and posts draft outreach tasks to Miles's review queue. Think of it as a parallel hunt lane — not a replacement for the n8n trigger-event-hunt (06:45 ET), but a second daily pass focused on a defined signal set.

## Live triggers (as of 2026-04-29)

### Trigger 1 — New Security Leader Hired
- **Schedule:** Mon–Fri 7:00 AM ET
- **Volume:** Up to 5 companies/day (ramp: 3/day during deliverability warm-up)
- **Signal:** CISO, VP InfoSec, Head of Security hired in the last 90 days
- **Verticals:** Healthcare, Financial Services
- **Size:** 500–5,000 employees
- **Outreach angle:** New leader, fragmented stack, board credibility gap. Sivan peer framing.
- **Primary persona:** The new hire directly (CISO or VP Sec)
- **Template:** [[../../90_Templates/tpl-ciso-cold]] new-CISO variant. See [[../triggers/exec-hire]] for language that lands.

### Trigger 2 — GRC/Compliance Hiring Signal
- **Schedule:** Mon–Fri 7:00 AM ET
- **Volume:** Up to 5 companies/day (ramp: 3/day during deliverability warm-up)
- **Signal:** Job posting for GRC Analyst, Security Program Manager, or Compliance Director, last 14 days
- **Verticals:** Healthcare, Financial Services
- **Size:** 500–5,000 employees
- **Outreach angle:** Solving the reporting problem with headcount instead of software. 160-hour anchor.
- **Primary persona:** CISO or VP Security (the hiring manager, not the open role)
- **Template:** See [[../triggers/grc-hiring]] for detection + language guidance.

## ICP segments configured

| Segment | Size | Compliance anchor |
|---|---|---|
| Mid-Market Healthcare | 500–5,000 emp | HIPAA, HICP |
| Mid-Market Financial Services | 500–5,000 emp | SOC 2, PCI-DSS, SEC cyber rules, NYDFS 500 |
| Mid-Market Manufacturing / Critical Infrastructure | 500–5,000 emp | NIST CSF, CMMC |

Full ICP scoring rubric: [[../icp]].

## What Swan produces

For each qualifying company:
1. HubSpot dedupe check (if Brad-owned, skip — see territory rules below)
2. Contact identified and enriched (CISO or VP Sec)
3. Email draft written referencing the specific trigger signal
4. Task dropped in Miles's review queue
5. Account + contact notes written to vault

Miles reviews, tweaks if needed, approves. Nothing sends without the ✅.

## Territory rules (critical)

Brad Baldelli (HubSpot owner 77002456) holds US healthcare + financial services enterprise territory by default. Before enriching any contact:
- Check HubSpot ownership
- If Brad-owned: skip or flag for territory conversation. Do not enrich, do not draft.
- If unowned or not in HubSpot: proceed.

Historical data: ~80% of obvious healthcare/finserv lookalikes in HubSpot are Brad-owned. White space is in companies NOT yet in HubSpot or unowned lifecycle:lead accounts.

## Senders

- **Email:** Miles (connected)
- **LinkedIn:** Not yet connected — add when ready

## Volume math

Triggers 1 + 2 combined = up to 10 companies/day at full ramp. Ramp phase: 6/day (3 per trigger). Stay at ramp until bounce rate confirms clean deliverability.

## What Swan reads for program context

Swan should reference these vault files before drafting:

| Context | File |
|---|---|
| ICP + fit scoring | [[../icp]] |
| Product positioning | [[../product/positioning]] |
| Customer quotes (verbatim) | [[../product/quotes]] |
| Email voice rules | [[../../00_Index/CLAUDE.md]] |
| Exec-hire trigger guidance | [[../triggers/exec-hire]] |
| GRC hiring trigger guidance | [[../triggers/grc-hiring]] |
| Sivan peer play | [[../../40_Plays/sivan-peer-intro]] |
| CTA ladder | [[../../40_Plays/cta-ladder]] |
| Forbidden words | [[../product/forbidden-words]] |
| Power phrases | [[../product/power-phrases]] |
| Winning openers | [[../product/winning-openers]] |
| Hard exclusions | `~/.claude/projects/-Users-milesbastianich/memory/reference_onyxia_exclusions.md` |

## Relationship to n8n workflows

Swan runs in parallel with the n8n trigger-event-hunt (06:45 ET). They cover different signal sources:
- n8n (06:45): SEC 8-K, HHS OCR breach portal, ZoomInfo Scoops, CISA KEV, NewsAPI
- Swan: job posting signals, new hire detections via LinkedIn/ZoomInfo

Dedupe between the two: HubSpot is the shared deduplication layer. Any company Swan surfaces that already has an active sequence in HubSpot should be skipped.

## Success metrics (90-day)

From [[../../onyxia-autopilot/SPEC.md]]:
- 40–50 personalized cold emails/day at full ramp
- ≥35% open rate
- 8–12% reply rate
- 3–5 qualified meetings/week
- < 15 min/day of Miles's time on outbound
