---
type: play
subtype: shift
trigger: cron weekday 16:30 ET
tags: [play, shift]
---

# Shift — EOD Wrap (16:30 ET weekdays)

End-of-day accountability + tomorrow's setup.

## Prompt for the subagent

You are running the EOD wrap for Miles. Read vault baseline including `40_Plays/rejection-feedback.md` and `40_Plays/reply-intent-parser.md`.

1. Read today's daily note + all vault commits since 07:00 ET.
2. Check HubSpot for activities logged today across all Miles-owned deals.
3. **Run reply parser final pass** per `40_Plays/reply-intent-parser.md` on any Gmail replies received since midday check. Run the measurement-log writeback per parser §5 on all classified replies. Write orphans to `60_Lessons/replies/orphans/YYYY-MM-DD.md`. **Then run a calendar sweep** for `meeting_booked_y_n`: for every measurement-log row from the last 14 days with `reply_intent=Interested` and `meeting_booked_y_n=pending`, check `mcp__claude_ai_Google_Calendar__list_events` for an event with the contact's email as an attendee in the next 30 days; flip `meeting_booked_y_n=y` if found.
4. **Run rejection capture** per `40_Plays/rejection-feedback.md` AND `40_Plays/batch-approve.md`:
   - Scan `#miles-ai-ops` for 👎 / ✅ / ✏️ reactions on today's draft posts (T2 individual messages — current behavior)
   - For each 👎 without an in-thread reason, post a follow-up asking Miles for a one-line reason
   - **For T1 batch messages (subject prefix `🧾 T1 Batch`):** parse per `40_Plays/batch-approve.md` reaction rules. Resolve every batch posted today that is not yet `[processed]`. Write per-item resolutions to `60_Lessons/batches/YYYY-MM-DD.md`. Update each item's `measurement-log.md` row with the resolution (`approval_state` flip, `batch_id` retained).
   - Write `60_Lessons/rejections/YYYY-MM-DD.md` summarizing approvals, rejections, reasons (T2 individual + per-batch totals).
5. **Run touch-tracker auto-update** per `50_Intel/methodology/touch-tracker.md` runbook §1-§3:
   - Reply detection on `reply_state=pending` rows older than 24h (Gmail search → reply-intent-parser → write back)
   - Cadence advance on rows where `next_touch_date ≤ today`
   - Sequence exhaust on rows where `touch_number ≥ sequence_max`
   - Log row count of each write to today's daily note under `## Shifter log`
6. **Final aging sweep** per `40_Plays/shifts/aging-check.md` Steps 1-3 (catches anything posted after 15:00 ET that aged through the rest of the day):
   - Pull open T2 individual + T1 batch messages from `#miles-ai-ops`
   - Apply tier-specific SLAs (T2: 24h DM nudge, 48h kill-bin; T1: 4h demote-all-unresolved)
   - Log results to today's daily note under `## Shifter log`
7. Summarize:

```
EOD WRAP — {{date}}

What I did today
- [drafted / enriched / researched / logged — with links]

Awaiting Miles's approval
- [draft for X — in Gmail + in ops channel]
- [follow-up to Y — in ops channel]

What slipped
- [task / account / action that didn't happen + why]

Tomorrow's top 3
1. ...
2. ...
3. ...
```

8. Post to `#miles-ai-ops`.
9. Update `~/ObsidianVault/00_Index/MOC_This_Week.md` "Top 3 to push" if day's events shifted priority.
10. Commit vault.
