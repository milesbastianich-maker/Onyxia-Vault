---
type: play
active: false
blast_radius: low
rollback_criteria: Miles rewrites >50% of the auto-draft 2 quarters running
measurement_precondition: 2 completed manual QBR decks in Drive as training reference
created: 2026-04-22
tags: [play, autonomy]
---

# Autonomy — Quarterly QBR Deck Auto-Draft

## What it does

Two weeks before each calendar quarter close, the operator generates a draft QBR deck in Google Drive for every active customer account. Deck includes:

- Quarter activity summary (pulled from HubSpot engagement history)
- Current MEDDPICC state (from vault account file)
- Onyxia usage/outcome metrics (from product if available, else placeholder)
- Upcoming regulatory deadlines affecting their vertical (via regulatory-deadline-tracker skill)
- Recommended Q+1 play
- Open risks / watch-outs

Miles edits + sends. Operator never sends.

## Why

QBRs are high-leverage, low-frequency. Miles currently builds them ad-hoc in the week before each quarter close, often at 9pm. The mechanical work (pulling activity logs, screenshotting charts, cross-referencing regulatory context) is automation-eligible. The strategic narrative is Miles's.

Target: reduce Miles's QBR build time from 3 hours to 45 minutes.

## Trigger conditions

- Date is (quarter-end minus 14 days).
- Account is `#active` AND HubSpot deal stage is post-`contractsent` OR the account has closed-won in the current or prior quarter.
- Account has >1 usage data point in the last 90d (to avoid auto-drafting dead-weight accounts).

## Pipeline

1. **Identify eligible accounts** (EOD shift at quarter-end minus 14d).
2. For each:
   - Researcher pulls HubSpot engagements, activity, meetings.
   - Reads vault account file for MEDDPICC + Timeline.
   - Reads `regulatory-calendar.md` for vertical-relevant deadlines Q+1.
3. **Generate deck** — Google Slides template (stored at `Drive/Onyxia-Sales-Assets/tpl-QBR.gslides`). Operator fills sections via slides API.
4. **Post to #miles-ai-ops** with the Drive link per account.
5. Miles edits + sends.

## Blast radius

Low. Draft in Drive, not sent. Even if the draft has errors, Miles reviews before any customer sees it. Worst case: time wasted on a bad draft.

## Rollback criteria

- If Miles rewrites >50% of the draft content 2 consecutive quarters → the auto-draft is not saving time. Pause and retrain prompts.
- If wrong account gets auto-drafted (not actually active) → kill + investigate.

## Measurement precondition

Two completed QBR decks Miles has built manually, stored in Drive under `Onyxia-Sales-Assets/qbr/YYYY-QN/`. These serve as training references for the template + tone calibration.

## Kill switch

Frontmatter flip.

## Cross-references

- [[../.claude/skills/regulatory-deadline-tracker/SKILL]]
- [[../.claude/agents/onyxia-researcher]]
- [[./quarterly-self-audit]]
