---
type: play
subtype: hunt
trigger: continuous (RB2B channel monitor)
vertical: all
created: 2026-04-21
tags: [play]
---

# Intent Signal Hunt

Visitors to `onyxia.io` who don't fill a form are the hottest cold leads we have. RB2B de-anonymizes them. Most of them never get worked.

## Sources
1. **RB2B** — Slack channel `#rb2b` (ID `C078FDJBJ2X`). Auto-posts visitor Name/Title/Company/LinkedIn/Location + company size + industry.
2. **ZoomInfo WebSights / Intent** — if subscribed. Supplement to RB2B.
3. **HubSpot form submissions** — inbound demo requests, event signups.

## When to run
- Morning brief (07:00 ET) pulls all RB2B hits since yesterday 17:00 ET.
- Midday check (12:00 ET) pulls fresh RB2B hits.
- Urgent: if an RB2B hit is clearly Tier 1 (CISO at enterprise healthcare/fins/mfg), flag immediately.

## Algorithm

For each RB2B hit:

1. Parse visitor payload: name, title, company, industry, employee count, revenue, LinkedIn, location.
2. Fit score per `50_Intel/icp.md`. Most visitors will be score 1-2 (noise). Keep only score ≥ 3.
3. Dedupe against `10_Accounts/` + HubSpot.
4. Enrich via ZoomInfo (confirm email + phone + tenure + recent role change).
5. Draft a short, specific opener that acknowledges they visited (without being creepy). Use "saw you poking around our site" energy, not "we tracked your IP."
6. Save Gmail draft, write vault notes, post to `#miles-ai-ops`.

## Visitor classification

| Fit Score | Example | Action |
|---|---|---|
| 5 | CISO at $1B healthcare org, visited today | Draft within 2 hours. Escalate to Miles for same-day send. |
| 4 | Director Security at enterprise ICP org | Draft within 24 hours. Normal review cadence. |
| 3 | VP at ICP adjacent org | Log in `50_Intel/signal-log/` for future touch. No immediate draft. |
| 1-2 | VC partners, vendors, small orgs, job seekers | Log and ignore. |

## The creep line
RB2B hits should be worked with discretion. Never quote the visit in the opener. Never name the page they visited. Use the visit as internal signal, not external evidence.

Good: "been following cyber resilience trends in healthcare, figured I'd reach out." (visit is internal signal)
Bad: "Saw you on onyxia.io yesterday." (creepy)

## Pre-approved auto-send (proposal)

For RB2B hits with fit score 5 AND in Tier 1 vertical AND using a pre-approved play, consider auto-send without per-email approval. Miles to review monthly rather than per-email.

*Not enabled without Miles's explicit green-light.*

## Runs
Every draft this play creates must append a row to [[../../50_Intel/methodology/measurement-log]] with `play_source = intent-signal-hunt`.

| date | hits pulled | fit≥3 | drafts staged | drafts sent | replies | meetings |
|---|---|---|---|---|---|---|
