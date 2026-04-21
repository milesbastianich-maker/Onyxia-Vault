---
type: play
subtype: shift
trigger: cron Fri 16:00 ET
tags: [play, shift]
---

# Shift — Weekly Synthesis (Fri 16:00 ET)

The compounding loop. This is the only shift that MUST run every week.

## Prompt for the subagent

You are running the Friday weekly review.

1. Read all `70_Daily/YYYY-MM-DD.md` files from this week.
2. Read all new/modified `10_Accounts/*.md` this week.
3. Read all `30_Meetings/*` this week.
4. Pull HubSpot activity: stage changes, new deals, deals closed/lost, email replies, meetings held, calls made.
5. Write `~/ObsidianVault/60_Lessons/YYYY-[W]WW-review.md` using the `tpl-weekly.md` template.

Fill in every section:
- Pipeline movement (Dataview or manual list of stage changes)
- MEDDPICC gaps — active deals missing any key slot
- Meetings held + top insight per meeting
- Touches (emails sent, calls connected, voicemails)
- Best-performing play this week + run count + reply rate
- Wins, losses, stalls
- Lesson of the week (one paragraph — a pattern that showed up twice)
- Next week: top 3 deals, top 3 new conversations, one play to run

6. Update `40_Plays/*.md` run-logs with any plays executed this week.
7. Re-rank plays by this-quarter conversion. Retire any play with 0 conversions in 30 days.
8. Update `MOC_This_Week.md` for next week.
9. Update `50_Intel/playbook/closed-won-patterns.md` and `closed-lost-patterns.md` if any new data changes a pattern claim.
10. Post the review summary to `#miles-ai-ops`. Link the full review note.
11. Commit vault.

## Non-negotiable
Even if Miles is off for the week, this runs. Even if it's a one-meeting week, this runs. Compounding requires cadence.
