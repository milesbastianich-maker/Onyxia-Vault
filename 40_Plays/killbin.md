---
type: play
subtype: archive-spec
trigger: applied when a draft is rejected, aged-out, or batch-rejected
created: 2026-05-05
tags: [play, archive, killbin]
---

# Kill-Bin

Terminal archive for drafts that will never ship. Recoverable, not destroyed. The kill-bin is a teaching surface — Friday weekly synthesis reads kill-reasons to spot ICP errors, voice drift, or playbook mistakes.

## Path layout

```
99_Archive/killbin/
├── INDEX.md                 # rolling index, weekly-synthesis updates
├── 2026-05/
│   ├── 2026-05-06-{draft_id}.md
│   ├── 2026-05-07-{draft_id}.md
│   └── ...
└── 2026-06/
    └── ...
```

One file per killed draft. Folder per ISO month. Index file rebuilt by Friday weekly synthesis.

## File schema

```yaml
---
type: killbin-entry
draft_id: <Gmail draft ID or vault draft slug>
gmail_draft_id: <Gmail's internal ID, e.g. r-1234567890>
killed_at: YYYY-MM-DD HH:MM ET
killed_reason: rejected | aged-out | batch-reject | manual
tier_at_kill: T0 | T1 | T2
batch_id: <batch_id if killed via batch flow, else empty>
miles_reason: <one line — Miles's stated reason if any. Empty if aged-out without comment.>
account: wikilink to 10_Accounts/{Company}.md
contact: wikilink to 20_Contacts/{First Last}.md
subject: <verbatim>
recipient_email: <email>
spine_pain: <Pain #N from drafter writeback>
canon_match: <canon entry from drafter writeback>
gmail_label_applied: Onyxia/Killbin | failed
touch_tracker_updated: pass | fail
recoverable: true
---

# Killed Draft — {{subject}}

## Body (verbatim, for reference)

<full draft body>

## Pain Selection (from drafter)

- Spine pain: <Pain #N>
- Why this pain: <rationale>

## Resolution

- Killed via: <slack_message_permalink>
- Aged out at: <HH:MM ET on YYYY-MM-DD>  *(if aged-out)*
- Miles reaction: <👎 / 👎 + thread reason / no reaction>
- Demoted from batch: <batch_id>  *(if applicable)*

## Lesson candidate

(Filled by Friday weekly synthesis if this kill connects to a pattern across ≥2 kills this week.)
```

## Gmail-label rule

Apply Gmail label `Onyxia/Killbin` to the Gmail draft, but DO NOT delete the draft. The label is the soft-delete primitive — it removes the draft from Miles's normal Drafts view via a Gmail filter rule he can configure once. The draft remains recoverable for 30 days, after which Miles can hard-delete via Gmail UI.

If the Gmail label apply fails (label missing, API error), record `gmail_label_applied: failed` in the killbin file and post a single-line warning to `#miles-ai-ops`. Do not block the kill-bin write on label-apply.

## Recovery procedure

1. Read the killbin file at `99_Archive/killbin/YYYY-MM/{date}-{draft_id}.md`.
2. Remove `Onyxia/Killbin` Gmail label from the original draft (the Gmail draft itself was not deleted).
3. Re-post the draft to `#miles-ai-ops` as a fresh T2 individual message with footer `(recovered from kill-bin {date})`.
4. Add a `## Recovery` section to the killbin file: `recovered_at: YYYY-MM-DD HH:MM ET, by: Miles, reason: <one line>`.
5. Set `recoverable: false` to prevent double-recovery.

The killbin file stays — it is the audit record. Recovery does not delete history.

## What goes here

- T2 individual drafts that received 👎 or aged ≥48h with no reaction.
- T1 batch items that hit `reject N` thread reply or aged ≥4h without parent reaction (the latter demotes to T2 first; if the resulting T2 then ages out, it lands here).
- T0 drafts that hit a graduated-send-authority gate failure mid-flight (rare; the path is normally caught at drafter time, not at send time).
- Drafts manually killed by Miles via vault edit or `/operator kill <draft_id>` command.

## What does NOT go here

- Drafts Miles edited via `✏️` reaction or `edit N:` thread reply — those re-post as fresh drafts and land in measurement-log as `approval_state=edited`.
- Drafts that simply have no reaction and are not yet aged — those wait their full SLA.
- Sent drafts with a hard-no reply — those live in measurement-log with `reply_intent=hard-no`.

## Friday weekly synthesis

Weekly synthesis reads `99_Archive/killbin/{YYYY-MM}/` files for the past 7 days. Aggregate by:

- `killed_reason` distribution (rejected vs aged-out vs batch-reject vs manual)
- `tier_at_kill` distribution (which tier produces the most kills?)
- top `miles_reason` strings (any reason appearing 2+ times → propose voice rule update or ICP review)
- top `spine_pain` killed (any spine pain that consistently kills → reconsider its tenure/breach overrides)

Output to `60_Lessons/YYYY-WW-review.md` `## Kill-bin patterns` section. Index file at `99_Archive/killbin/INDEX.md` rebuilds with the rolling totals.

## Cross-references

- `40_Plays/batch-approve.md` — feeds kill-bin via `reject N` and aged-out paths
- `40_Plays/shifts/aging-check.md` — primary kill-bin writer (T2 aged + T1 aged-batch demoted)
- `40_Plays/shifts/eod-wrap.md` — secondary kill-bin writer (👎 rejections)
- `40_Plays/shifts/weekly-synthesis.md` — pattern review consumer
- `~/.claude/agents/onyxia-drafter.md` — provides spine-pain + canon match for the schema
- `50_Intel/methodology/touch-tracker.md` — `reply_state=killed-aged` flip
