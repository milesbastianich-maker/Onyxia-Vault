---
type: play
subtype: autonomy-rule
trigger: applied before auto-send decision (reply parser + EOD shift read this frontmatter)
vertical: all
active: false
created: 2026-04-22
tags: [play]
---

# Graduated Send Authority

Spec for auto-sending a narrow slice of outbound without Miles's reaction. Switch is OFF today. Flip only after measurement floor clears.

## Master switch

`active: false` in frontmatter. The reply parser and EOD shift MUST read this field before auto-sending. If `active: false`, fall back to draft-and-approve. No exceptions.

**Status 2026-05-05:** Switch is **intentionally OFF**. Measurement floor is unmet (measurement-log < 50 reply-resolved rows). Friday weekly synthesis (`40_Plays/shifts/weekly-synthesis.md`) evaluates the floor each week and posts a promotion proposal to `#miles-ai-ops` if cleared. Miles flips this field manually after reviewing.

## Flip-to-ON condition (measurement floor)

All must be true:
- [[../50_Intel/methodology/measurement-log]] has at least 50 rows with non-null `reply_y_n`
- Aggregate reply rate across those 50+ rows is 15% or greater
- Last 4 weeks of data show no week below 10% reply rate

Until all three clear, the switch stays OFF regardless of per-draft gate quality.

## Per-draft gates (all must pass, even when master switch is ON)

1. **Template proven.** The template backing this draft has 5+ prior sends logged in measurement-log AND reply rate on that template is 20% or higher.
2. **Tier 1 ICP.** Prospect fit score is 4 or 5 per [[../50_Intel/icp]] rubric.
3. **No prior thread.** HubSpot shows zero prior emails between Miles and this contact.
4. **Exclusion clean.** Contact + company pass `~/.claude/projects/-Users-milesbastianich/memory/reference_onyxia_exclusions.md`.
5. **Vertical reps.** Miles has sent 10+ prior outbounds in this vertical (not first-time-in-vertical).

Any gate fails, fall back to draft-and-approve. Log the failing gate in the audit file.

## Kill-switch

Miles can set `active: false` at any time. Parser and EOD shift re-read frontmatter every run. No restart needed. Effective on next shift tick.

## Rollback protocol

Weekly synthesis (Fri 16:00 ET) compares rolling 4-week reply rate to the prior 4-week baseline.

- If rolling rate drops 20% or more from prior baseline, auto-flip `active: false` on the spot.
- Post to `#miles-ai-ops` with the rate delta and 3 most recent sends that missed.
- Miles must manually flip back to `active: true` after reviewing.

## Audit log

Every auto-send writes a row to `60_Lessons/auto-send-audit/YYYY-WW.md`:

```
| timestamp | draft_id | template | fit_score | vertical | gates_passed | gate_failed_reason | reply_y_n | meeting_booked |
|---|---|---|---|---|---|---|---|---|
```

Weekly file. Pruned from active view after 90 days, moved to `99_Archive/`.

## What this does NOT cover

- Follow-ups on existing threads. Always draft-and-approve.
- Voicemails. Always ask.
- Peer-call CTAs (Sivan). Always ask. Sivan is a finite asset.
- Any reply-to-reply. Only first-touch cold outbound is eligible.

## Reads

Parser and EOD shift read this file's frontmatter `active` field. No other file encodes this state. One source of truth.

The drafter agent (`~/.claude/agents/onyxia-drafter.md`) reads this `active` field at tier-classification time. T0 routing requires `active: true`; otherwise T0-eligible drafts demote to T1 batch approval. See the drafter's "T0 emit path" subsection of Tier Classification for the exact gate flow.

Friday weekly synthesis (`40_Plays/shifts/weekly-synthesis.md`) evaluates the floor over the rolling 4-week window and writes a row to the Runs table below. Master-switch flip remains MANUAL — Miles flips `active: true` after reviewing the synthesis post in `#miles-ai-ops`.

## Runs

Friday weekly synthesis writes one row per evaluation. Format:

| date | rows_in_log | resolved_rows | aggregate_reply_rate | last_4w_min | floor_passed | notes |
|---|---|---|---|---|---|---|

(Empty until Friday floor evaluation step ships in `40_Plays/shifts/weekly-synthesis.md`.)
