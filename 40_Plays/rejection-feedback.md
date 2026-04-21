---
type: play
subtype: feedback-loop
trigger: continuous
tags: [play]
---

# Rejection Feedback Loop

The compounding learning system breaks without this. When Miles rejects or edits a draft, the system must capture WHY. Without the reason, the next draft makes the same mistake.

## The convention

When Miles sees a draft in `#miles-ai-ops` he doesn't like, he does ONE of:

1. **React with 👎** to the draft message in Slack. That alone flags it as rejected.
2. **React with 👎** AND reply in-thread with a one-line reason. Any of:
   - "too formal"
   - "too generic"
   - "wrong hook"
   - "bad timing"
   - "wrong person"
   - "voice off"
   - "too long"
   - "product claim wrong"
   - "already tried this"
   - "let me edit" (then pastes the correct version)
3. **React with ✅** to approve and send.
4. **React with ✏️** + in-thread edit = send after my rewrite.
5. **No reaction** = assume "not now, revisit later."

## How shifts use this

- **EOD wrap** scans `#miles-ai-ops` for reactions on the day's draft posts.
- Writes findings to `60_Lessons/rejections/YYYY-MM-DD.md`.
- Flags any draft with 👎 but no reason — prompts Miles to add one.

## How weekly synthesis uses this

- Friday review aggregates rejection reasons for the week.
- Patterns of 2+ rejections with the same reason trigger:
  - Voice rule update in CLAUDE.md
  - Play retirement or revision
  - ICP refinement
- `60_Lessons/YYYY-WW-review.md` includes a "Rejection patterns" section.

## Format for `60_Lessons/rejections/YYYY-MM-DD.md`

```yaml
---
type: lesson
subtype: rejection-log
date: YYYY-MM-DD
tags: [lesson]
---
```

```
# Rejections — YYYY-MM-DD

## Count
Approvals: N. Rejections: M. Pending: P.

## Rejected drafts
- [Draft link + prospect name] — reason: [one-liner]
- ...

## Patterns
- If 2+ rejections share a reason, note it here and propagate to weekly review.

## Actions taken
- [revision to voice rule / play / ICP]
```

## Hard rule

Every morning brief checks that yesterday's rejections have been logged. If `60_Lessons/rejections/YYYY-MM-DD.md` doesn't exist for yesterday AND any drafts were posted, the morning brief creates a stub and flags missing data.

## What this does NOT do

- It does not auto-resend corrected drafts. Miles still decides.
- It does not override his judgment. It captures it.
- It does not retroactively re-tag historical drafts. Starts today.
