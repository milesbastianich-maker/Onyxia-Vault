---
type: play
subtype: hunt
trigger: rolling (one vertical per month)
vertical: rotating
created: 2026-04-21
tags: [play]
---

# Vertical Saturation Hunt

Pick one sub-vertical per month. Enumerate every ICP-fit company in it. Prioritize by size + signal. Map it completely.

## When to run
Rolling, one sub-vertical per calendar month. Start of month = scope the vertical. End of month = hand off the map to recurring hunt cadences.

## Vertical rotation proposal

| Month | Sub-vertical | Rationale |
|---|---|---|
| 2026-04 | Healthcare RCM | Medusind is in pipeline, playbook has 4 healthcare wins, post-breach wave |
| 2026-05 | Regional banks ($10-50B assets) | First Horizon is in pipeline, SEC disclosure tailwind |
| 2026-06 | CMMC defense manufacturers | Metalex is in pipeline, CMMC deadlines forcing function |
| 2026-07 | Critical infrastructure (utilities + transit) | Port Authority + Summit won, NIS2/NIST-CSF 2.0 momentum |
| 2026-08 | Identity/SaaS vendors | Radiant Logic $165K win, peer-vendor play |
| 2026-09 | Reinsurance + complex insurance | RGA in pipeline, multi-jurisdiction compliance |

## Algorithm

1. For the chosen sub-vertical, use ZoomInfo `search_companies` with:
   - Vertical-specific NAICS + SIC codes
   - Employee count 500-10,000
   - Revenue $100M-$5B
   - US HQ

2. Output full list into `50_Intel/verticals/{vertical-name}.md`. Columns:
   - Company, domain, employees, revenue, HQ, already-in-HubSpot (yes/no + owner), already-in-vault (yes/no), existing trigger events, fit score.

3. Prioritize top 25 by:
   - Fit score
   - Recency of trigger event
   - Company size (mid-range preferred: 1K-5K employees)

4. Feed the top 25 into the daily trigger-event hunt queue.

5. Update `50_Intel/verticals/{vertical-name}.md` with status changes weekly (new triggers, new contacts identified, HubSpot activity).

## Persistence
A vertical map is a standing artifact. Once built, it gets updated quarterly, not rebuilt.

## Runs
