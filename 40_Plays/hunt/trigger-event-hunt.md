---
type: play
subtype: hunt
trigger: daily 06:45 ET weekdays (pre-morning-brief)
vertical: all
created: 2026-04-21
tags: [play]
---

# Trigger-Event Hunt

Fresh triggers beat cold lists 10x. This is the highest-conversion hunt lane.

## When to run
Every weekday at 06:45 ET, ahead of the 07:00 morning brief. Feeds the brief.

## Sources
1. **ZoomInfo Scoops** — `search_scoops` filtered to Tier 1 ICP verticals, last 72 hours
2. **Web News** — targeted searches on healthcare breach, banking cyber incident, CMMC award, new CISO, 8-K cyber disclosure
3. **SEC EDGAR** — 8-K filings with cyber keywords, new proxy statements with board-level cyber committee formation
4. **ZoomInfo Intent** — if available on subscription, ICP-vertical intent spike
5. **LinkedIn posts** — "excited to announce" + CISO + ICP companies (via web search)

## Algorithm

1. Pull fresh signals from all five sources, last 72 hours.
2. Dedupe against `10_Accounts/` (already active deals) + HubSpot (other-rep territory).
3. For each surviving signal:
   - Score fit per `50_Intel/icp.md` rubric.
   - Drop anything scoring < 3.
4. Identify the right contact to target (CISO or VP Sec) via ZoomInfo search.
5. Enrich the contact. Confirm email + accuracy 85+.
6. Draft a hyper-personalized opener referencing the trigger event specifically.
7. Save Gmail draft, write vault account + contact notes, post to `#miles-ai-ops` with:
   - Trigger event in one line
   - Fit score
   - Draft copy
   - Awaiting approval tag

## Max volume per run
5 drafts/day. More than that = noise. Quality over quantity.

## Expected objection
"Not a priority right now." → File under nurture with the trigger event date. Re-approach on the next trigger.

## Success criteria
Reply within 5 business days. Peer call booked on calendar. Trigger-event specificity in reply confirms the hook landed.

## Runs
(log every run below with date + count found + count replied)
