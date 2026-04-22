---
type: play
active: false
blast_radius: medium
rollback_criteria: any rolling 7-day false-positive > 1
measurement_precondition: 25+ inbound form submissions logged in measurement-log
created: 2026-04-22
tags: [play, autonomy]
---

# Autonomy — Inbound Intent-Form Auto-Reply

## What it does

When a prospect submits the onyxia.io contact form or books a demo slot via the website, the operator auto-generates a personalized reply draft within 10 minutes and posts it to `#miles-ai-ops` for ✅. No send without approval.

## Why

Centra closed at $270K from an inbound. Speed-to-response on inbound is the single highest-conversion lever in the existing corpus (per `closed-won-patterns.md`). Current flow is: form hits email → Miles eventually sees → manual research → manual draft. Cycle time: 2-24h. Target: 10 minutes to drafted-and-staged.

## Trigger conditions

- New row appears in HubSpot contacts with `source = website` OR `lead_source = inbound_form`.
- Calendar event created by prospect booking via onyxia.io/book-a-demo.
- Email to `info@onyxia.io` or `sales@onyxia.io` classified as inbound interest (reply-intent-parser confidence ≥75% on "interested" intent).

## Pipeline

1. **Detect** — n8n workflow polls HubSpot contacts + Gmail inbox every 5 minutes for new inbound signals.
2. **Enrich** — onyxia-researcher sub-agent pulls ZoomInfo + HubSpot history + any Gmail prior thread on the prospect.
3. **Score** — score-prospect-fit skill runs. Below 3: drop to morning brief only. 4-5: continue.
4. **Draft** — onyxia-drafter creates a Gmail draft thanking them for reaching out, referencing specifically what they clicked or booked, proposing 2-3 specific times pulled from Calendar.
5. **Post** — operator posts draft preview to `#miles-ai-ops` for ✅.

## Blast radius

Medium. The draft is gated on Miles's ✅, but the research + draft generation happens without him. If the Gmail draft is accidentally sent (e.g., keyboard slip), it goes to a warm inbound, not a cold prospect. Worst case: slightly-off-voice reply to someone who wanted to hear from us anyway.

## Rollback criteria

- Any single false-positive in the "this was an interested inbound" classification (spam classified as interested, or a partnership email classified as prospect) → flip `active: false`.
- Rolling 4-week bad-draft rate (Miles 👎) > 25% → pause for voice retraining.

## Measurement precondition

Must have 25+ inbound form submissions logged in `measurement-log.md` with response-time and outcome captured. Without that baseline, the speed-to-reply claim is ungrounded.

## Kill switch

Flip frontmatter `active: true` → `active: false`. Takes effect within 5 minutes (polling interval).

## Cross-references

- [[./reply-intent-parser]]
- [[./graduated-send-authority]]
- [[./auto-promote-intelligence]]
- [[../50_Intel/agent-architecture/specialist-agents]]
