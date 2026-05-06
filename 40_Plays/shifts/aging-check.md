---
type: play
subtype: shift
trigger: cron weekday 11:00 ET + 15:00 ET
tags: [play, shift]
---

# Shift — Aging Check (11:00 ET + 15:00 ET weekdays)

SLA enforcement for un-reacted approvals. Two firings per business day at clean SLA boundaries (morning T1 batch hits 4h at 11:00; afternoon work hits its own boundary at 15:00).

## Prompt for the subagent

You are running the aging check. Read vault baseline first, including `40_Plays/batch-approve.md`, `40_Plays/killbin.md`, and `~/.claude/agents/onyxia-drafter.md` Tier Classification section.

### Step 1 — Pull open approvals from `#miles-ai-ops`

Use `mcp__claude_ai_Slack__slack_read_channel` on channel `C0AUB4DATP0` for the last 72 hours. Filter to messages posted by the bot (drafter / shifter / operator) that are draft approvals or T1 batches. Categorize:

- **T2 individual** — bot message with a draft body, no `🧾 T1 Batch` prefix, no terminal reaction (no ✅, 👎, or matching ✏️ thread reply).
- **T1 batch** — bot message with `🧾 T1 Batch` subject prefix, no `[processed]` line yet in `60_Lessons/batches/YYYY-MM-DD.md`.
- **T0** — N/A (T0 never posts to Slack).

### Step 2 — Apply tier-specific SLAs

For each open item, compute age = (now - posted_ts).

**T2 SLAs:**
- age ≥ 24h AND no DM nudge sent yet → send DM to Miles (channel `D...` for Miles direct) with format:
  ```
  ⏰ T2 draft aging — 24h, no reaction
  • Account: <Company>
  • Recipient: <First Last> (<title>)
  • Subject: <subject>
  • Posted: <HH:MM ET>
  • Original message: <Slack permalink>
  ```
  Mark the original Slack message with a thread reply: `⏰ aged 24h — DM nudge sent at <HH:MM ET>`. Idempotency: do not re-send DM if one was already sent for this message.
- age ≥ 48h AND still no reaction → archive to kill-bin per `40_Plays/killbin.md`. Update the original Slack message with thread reply: `⚰️ aged out at 48h — moved to kill-bin/{draft_id}`. Apply Gmail label `Onyxia/Killbin`. Update touch-tracker row to `reply_state=killed-aged`.

**T1 batch SLAs:**
- age ≥ 4h AND no parent ✅ AND no parent 👎 → demote-all-unresolved per `40_Plays/batch-approve.md`. For each item not already terminal (rejected via `reject N`, demoted via `demote N`, or edited via `edit N:`):
  1. Re-post as individual T2 message with `(demoted from <batch_id>)` footer.
  2. Mark item terminal in `60_Lessons/batches/YYYY-MM-DD.md` with reason `auto-demote-aged-out`.
  3. Update `measurement-log.md` row: `approval_state=demoted`, `batch_id` retained.
- After demotion, if all items in the batch are now terminal, write the `[processed]` line.

### Step 3 — Idempotency log

Write a single line to today's daily note `## Shifter log` section per firing:

```
- HH:MM ET — aging-check fired: N T2 nudges sent, M T2 archived to kill-bin, K T1 batches demoted, J T1 items demoted total
```

Even if all counts are zero, log the firing. Watchdog reads this.

### Step 4 — Failure handling

If Slack read fails or Gmail label apply fails, post to `#miles-ai-ops`:

```
🚨 AGING-CHECK — partial failure at HH:MM ET
- Slack read: <pass|fail with error>
- Kill-bin writes: <N successful / M total>
- Gmail label apply: <N successful / M total>
Partial state in kill-bin/INDEX.md. Re-run aging-check to retry.
```

### Step 5 — No-op clean-firing

If nothing is open or aged, do NOT post anything to Slack. The daily-note log line is the only artifact. Posting "aging-check clean" twice a day adds noise to the channel.

## Hard rules

- **Never auto-archive a draft that has any reaction or thread activity.** If Miles reacted with 🟢 (ack), that counts as activity — leave it alone. The aging logic is for *zero* activity, not for "I haven't decided yet."
- **Never delete a Slack message.** Update with thread reply only. Channel history is the audit log.
- **Never archive a T0 draft.** T0 has no Slack message; T0 lifecycle is owned by `40_Plays/graduated-send-authority.md` + n8n Workflow 3.
- **Never demote a T1 item that already has a thread resolution.** Read `60_Lessons/batches/YYYY-MM-DD.md` before acting.
- **Time-window enforcement.** This shift fires at 11:00 ET and 15:00 ET only. Ad-hoc invocation requires explicit operator override via the shifter.

## What this shift does NOT do

- Does not draft. Does not send. Does not classify replies (that is reply-intent-parser at midday + EOD).
- Does not touch HubSpot beyond the kill-bin's `ai_drafter_outcome=killed-aged` write (see `killbin.md`).
- Does not modify the touch-tracker beyond the single `reply_state=killed-aged` flip on archived items.

## Cross-references

- `40_Plays/batch-approve.md` — T1 reaction parsing rules
- `40_Plays/killbin.md` — kill-bin schema + Gmail-label rule + recovery
- `40_Plays/shifts/eod-wrap.md` — final aging sweep at 16:30 ET
- `~/.claude/agents/onyxia-shifter.md` — dispatch table
- `60_Lessons/batches/INDEX.md` — batches resolution log

## System actions required (Miles must run these once)

This shift play is inert until launchd is configured. One-time setup:

1. Add `aging-check` to the `VALID_SHIFTS` array in `~/code/onyxia-shifts/run-shift.sh`.
2. Create `~/Library/LaunchAgents/com.milesbastianich.onyxia-shift-aging-check.plist` modeled on the existing shift plists, with two `StartCalendarInterval` entries: `Hour=11 Minute=0 Weekday=1..5` and `Hour=15 Minute=0 Weekday=1..5`.
3. `launchctl bootstrap gui/$(id -u) ~/Library/LaunchAgents/com.milesbastianich.onyxia-shift-aging-check.plist` to activate.
4. Add a row to the dispatch table in `~/.claude/agents/onyxia-shifter.md` (already pointed to via `batch-approve.md`).
