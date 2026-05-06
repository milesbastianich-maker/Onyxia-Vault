---
type: play
subtype: reply-parser
trigger: continuous (runs within Midday + EOD shifts)
tags: [play]
---

# Reply Intent Parser

The biggest remaining automation gap. When a prospect replies to one of Miles's outbound emails, the reply lands in his Gmail inbox and his brain. The parser watches, classifies, and drafts the branch-default response.

## What the parser does

For every new Gmail thread that's a reply to a message Miles sent in the last 60 days:

1. Read the thread. Identify sender, subject, body.
2. Classify intent into one of these buckets:
   - **Interested** — affirmative reply, wants to book
   - **Referral** — pointing to someone else (name or "talk to X")
   - **Not interested, not now** — polite no, maybe later
   - **Not interested, not ever** — hard no, unsubscribe tone
   - **Out of office** — auto-reply, no action
   - **Wrong person** — "not my area" but no referral
   - **Competitor** — already bought competitor X
   - **Pricing question** — wants cost info before agreeing to a call
   - **Objection** — specific concern needs answering
   - **Ambiguous** — can't tell, needs human read
3. For each classification, draft the branch-appropriate next response per table below.
4. Post to `#miles-ai-ops` with: classified intent, prospect + thread link, suggested response (as Gmail draft), awaiting approval.
5. Log to `60_Lessons/replies/YYYY-MM-DD.md`.

## Branch defaults (all go to Gmail drafts, not sent)

| Intent | Default response |
|---|---|
| Interested | Book the meeting. Send Calendly link or propose 2 times. Loop Sivan if CISO-level. |
| Referral | Thank the sender. Draft a short cold email to the new person. Cite the referral. |
| Not interested, not now | Thank. Ask permission to follow up on a specific trigger (e.g. "happy to circle back when HIPAA 2026 kicks in"). |
| Not interested, not ever | Thank, unsubscribe, log to exclusions. No follow-up draft. |
| Out of office | No response. Log OOO end date if stated. Auto-retry after that date. |
| Wrong person | Thank, ask who's the right contact. |
| Competitor | Thank, ask a calibration question about their experience. Probe for displacement signal. |
| Pricing question | Do NOT quote pricing. Book a 15-min scoping call to understand fit first. |
| Objection | Draft response using objection library (see `50_Intel/methodology/objections.md`). |
| Ambiguous | Flag to Miles. No draft. "Read this one manually." |

## Shift integration

- **Midday Signal Check (12:00 ET):** run the parser on all new replies since the morning brief.
- **EOD Wrap (16:30 ET):** final pass on the day's replies.
- Each run logs to `60_Lessons/replies/YYYY-MM-DD.md`.

## §5 — Measurement-log writeback (mandatory, added 2026-05-05)

Every classified reply must update the originating draft's row in `50_Intel/methodology/measurement-log.md`. This is what closes the reply-rate loop and lets Friday weekly synthesis compute reply rate by tier / hook / persona / play.

**Procedure (per classified reply):**

1. Find the originating draft in measurement-log:
   - Compute `expected_draft_id` from the thread: search rows where `contact` wikilink matches the thread sender, `sent_date ≥ thread.first_message_date - 60 days`, and `reply_y_n=pending`.
   - If exactly one match: that is the row to update.
   - If multiple matches: pick the most recent `sent_date`. Log the disambiguation in `notes`.
   - If zero matches: this is an **orphan reply** (e.g., a reply to a thread that pre-dates measurement-log, or a manually-sent email never logged). Write to `60_Lessons/replies/orphans/YYYY-MM-DD.md` with full context. Do NOT fabricate a row.

2. Update the matched row:
   - `reply_y_n: y` (anything that is not OOO is a real reply)
   - `reply_intent: <classified bucket name>`
   - `notes: <append "replied YYYY-MM-DD HH:MM ET" + brief intent context>`

3. If the classified intent is `Interested` and a meeting subsequently appears on the calendar with this contact within 14 days, EOD wrap (or Friday synthesis) sets `meeting_booked_y_n: y` per the calendar sweep step in `40_Plays/shifts/eod-wrap.md`.

4. OOO replies are special: do NOT flip `reply_y_n=y`. Write `reply_intent: ooo` with `notes` capturing the OOO end date if stated. Auto-retry on/after that date is owned by the touch-tracker auto-update runbook §2.

**Orphan log format (`60_Lessons/replies/orphans/YYYY-MM-DD.md`):**

```yaml
---
type: lesson
subtype: orphan-reply
date: YYYY-MM-DD
tags: [lesson, orphan]
---
```

```
# Orphan replies — YYYY-MM-DD

| reply_at | from | subject | thread_link | classified_intent | reason_orphan |
|---|---|---|---|---|---|
| 2026-05-06 14:22 ET | john@example.com | Re: ... | <gmail link> | Interested | thread_pre_dates_measurement_log |
```

Friday synthesis reads orphan logs to surface "we are getting replies on threads we never logged" — a leakage indicator.

**Failure handling:**

- If measurement-log file is locked or write fails, post a single-line warning to `#miles-ai-ops`: `🚨 reply-parser: measurement-log writeback failed for <thread>. Will retry next shift.` Do NOT block the reply-classification flow on writeback.
- If the same reply has already been written (idempotency check: `notes` already contains "replied YYYY-MM-DD"), skip. Log nothing.

## Hard rules

- **Never send a response.** Always draft. Miles approves per the same rules as cold outbound.
- **Ambiguous is better than wrong.** If the signal is unclear, flag it to Miles manually.
- **Pricing is a hard stop.** Never quote. Always redirect to a scoping call.
- **Voice rules apply.** Short sentences, no em dashes, no corporate jargon.
- **HubSpot logging.** Every reply, classified, gets logged as a HubSpot activity on the associated contact.

## Log format for `60_Lessons/replies/YYYY-MM-DD.md`

```yaml
---
type: lesson
subtype: reply-log
date: YYYY-MM-DD
tags: [lesson]
---
```

```
# Replies — YYYY-MM-DD

## Summary
Total: N. Interested: X. Referrals: Y. Not-now: Z. Hard-nos: W. Others: V.

## Thread by thread
- [Prospect] — [Intent] — [Thread link] — [Draft posted? Y/N]
```

## Weekly synthesis

Reply classification patterns feed the weekly review:
- Most common intent this week
- Conversion rate (Interested / Total)
- Objection types for the library

## What this does NOT do

- Does not read beyond new threads.
- Does not respond without approval.
- Does not auto-book meetings (sends a draft that proposes times).
- Does not handle LinkedIn messages (separate play needed).
