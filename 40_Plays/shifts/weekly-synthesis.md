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
4. Read all `60_Lessons/rejections/*.md` and `60_Lessons/replies/*.md` from this week.
5. Pull HubSpot activity: stage changes, new deals, deals closed/lost, email replies, meetings held, calls made.
6. Write `~/ObsidianVault/60_Lessons/YYYY-[W]WW-review.md` using the `tpl-weekly.md` template. Include these new sections:
   - **Rejection patterns.** Aggregate 👎 reasons. Any reason appearing 2+ times triggers a voice rule or play revision. Document the rule change here.
   - **Reply classification summary.** Total replies received + bucket distribution + reply-to-meeting conversion rate.
   - **Compute cost tracking.** Rough estimate of shift-runs and draft-creations this week for observability. Flag if costs spike.
   - **Draft-to-send rate.** Of drafts posted, how many got ✅ approved? Track trend over weeks. When it hits 90%+ consistently for 3 weeks, surface "option (b) auto-send" eligibility to Miles.
   - **Kill-bin patterns** per `40_Plays/killbin.md`. Read all `99_Archive/killbin/YYYY-MM/*.md` for the past 7 days. Aggregate by `killed_reason`, `tier_at_kill`, top `miles_reason` strings, top `spine_pain`. Any `miles_reason` appearing 2+ times → propose a voice rule update or ICP review. Update `99_Archive/killbin/INDEX.md` rolling totals + top-reasons + recovery-log tables.
   - **Batch resolutions** per `40_Plays/batch-approve.md`. Aggregate this week's `60_Lessons/batches/*.md`: batches_posted, items_total, approve_rate, demote_rate, reject_rate, aged_out_rate. If aged-out rate is >25%, T1 SLA may be too tight or shift cadence too sparse — flag for review. Update `60_Lessons/batches/INDEX.md` rolling totals.
   - **Graduated-send-authority floor evaluation** per `40_Plays/graduated-send-authority.md`. Compute over rolling 4 weeks: total `tier∈{T1,T2}` rows in measurement-log with non-null `reply_y_n`, aggregate reply rate, weekly minimum reply rate. If all three pass (50+ rows, ≥15% aggregate, no week <10%), post a promotion proposal to `#miles-ai-ops` and write a Runs row in the graduated-send-authority file. Master switch flip remains manual (Miles ✅).

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
