---
type: play
subtype: intelligence-loop
trigger: 16:30 ET as part of EOD shift
vertical: all
active: true
created: 2026-04-22
tags: [play]
---

# Auto-Promote Intelligence

Per CLAUDE.md mandate: "If a lesson is learned in one account note and never referenced again, it decayed." This play scans daily notes for patterns that repeat across accounts and proposes promotion to the shared `50_Intel/` layer.

Vault-only. Gated on Miles's reaction. No outbound blast radius.

## When it runs

Daily at 16:30 ET during the EOD shift. Reads files modified in the last 24 hours under:
- `10_Accounts/*.md`
- `30_Meetings/*-debrief.md`

## What it looks for

Recurring patterns across 2+ files in the 24h window:

1. **Objection phrases.** Same 3-5 word concern stated by two different prospects. Target: `50_Intel/methodology/objections.md`.
2. **Competitor mentions.** Same tool named in 2+ files. Target: `50_Intel/competitors/{tool}.md` (create if new).
3. **Trigger-event types that converted.** Same event class (new-CISO, breach, M&A) tied to a meeting booked in 2+ files. Target: `50_Intel/icp.md` trigger-events section.
4. **Winning openers.** Same subject-line or opening-paragraph structure tied to a reply in 2+ files. Target: `50_Intel/product/winning-openers.md` (owned by other operator, append only).
5. **Losing patterns.** Same disqualifier showing up in 2+ `#disqualified` transitions. Target: `50_Intel/playbook/closed-lost-patterns.md`.

## Proposal format

Posts to `#miles-ai-ops` as a numbered list:

```
Auto-promote proposals, YYYY-MM-DD

1. Objection: "we already have a GRC tool" heard in [[Acme]] 2026-04-20 and [[Bravo]] 2026-04-21.
   Proposed append to 50_Intel/methodology/objections.md:
   > <one-paragraph objection entry with attribution>

2. Competitor sighting: SafeBase named in [[Charlie]] 2026-04-21 and [[Delta]] 2026-04-22.
   Proposed create/append 50_Intel/competitors/safebase.md:
   > <observation with attribution>

React per item:
- on the number: 1️⃣, 2️⃣, etc. THEN one of the reaction emojis below
- ✅ = approve append
- ✏️ = Miles posts corrected version in thread; bot appends the thread version
- 👎 = reject; bot logs to 60_Lessons/rejections/YYYY-MM-DD.md with thread reason
```

(If Slack can't route by numbered-reaction pairs, break each proposal into its own post with a single ✅ / ✏️ / 👎 decision.)

## Append rules

On ✅:
- Append to the target file with attribution block:
  ```
  - Observed YYYY-MM-DD. Sources: [[Acme]], [[Bravo]]. Auto-promoted from daily scan.
  ```
- Do not rewrite existing entries. Append only. If the pattern is already documented, flag as "duplicate, no action" in the audit log.

On ✏️:
- Miles replies in thread with the corrected version.
- Bot takes the thread text verbatim. No paraphrasing. Appends with attribution.

On 👎:
- Log to `60_Lessons/rejections/YYYY-MM-DD.md`:
  ```
  - auto-promote-proposal | YYYY-MM-DD | [target file] | [pattern summary] | reason: [thread message or "no reason given"]
  ```

## What this does NOT do

- Does not touch files tagged as owned by another operator in active scope (check daily note for ownership flags).
- Does not write to `00_Index/CLAUDE.md`. That is the quarterly self-audit's job.
- Does not rewrite. Append only.
- Does not promote patterns seen in only 1 file. Two files minimum.

## Edge cases

- **Same account, two notes.** Does not count. Needs two distinct accounts.
- **Template drift.** If the same sentence shows up across 5+ files in a day, that's boilerplate, not a pattern. Suppress.
- **Miles wrote it himself.** If a line matches a manual entry Miles made earlier in the day, suppress. Auto-promote is for synthesis, not echo.

## Audit trail

Every proposal and its outcome log to `60_Lessons/auto-promote/YYYY-MM-DD.md`.

```
| timestamp | pattern | source_files | target_file | decision | appended_text |
|---|---|---|---|---|---|
```

## Reads

- Vault files modified in last 24h
- Existing `50_Intel/` files for dedup check
- `60_Lessons/rejections/` for pattern suppression (rejected twice = stop proposing)

## Runs

- YYYY-MM-DD | N proposals | approved X, edited Y, rejected Z
