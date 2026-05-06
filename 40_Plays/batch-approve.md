---
type: play
subtype: approval-spec
trigger: applied at draft post-time when tier=T1
created: 2026-05-05
tags: [play, approval, tier]
---

# T1 Batch Approval

Spec for grouping T1 drafts into a single Slack message and parsing reactions deterministically. Built on top of the existing `#miles-ai-ops` reaction flow (✅/👎/✏️/🟢) — no Block Kit buttons, no HumanLayer, no new Slack apps. Reactions stay the primitive.

## When this applies

Drafter classifies a draft as `tier: T1` per the Tier Classification section in `~/.claude/agents/onyxia-drafter.md`. The shift that produced the draft (typically `morning-brief`, `midday-signal`, or `reactivation-sweep`) groups all T1 drafts from that shift into one batch message. T0 drafts skip Slack entirely. T2 drafts post individually as today.

## batch_id format

`T1-YYYY-MM-DD-HHMM-{shift-slug}`. Example: `T1-2026-05-06-0700-morning-brief`. One batch_id per shift run. Drafter writes the batch_id back into each draft's `measurement-log.md` row at the moment the shift emits the batch (drafter leaves it null at draft time).

## Slack message format

```
🧾 T1 Batch <batch_id> — N drafts

1. <subject> — <First Last> @ <Company>
2. <subject> — <First Last> @ <Company>
...

Reactions on this message:
✅ = approve all unmentioned items
👎 = reject all → kill-bin

Thread replies for surgical control:
"demote 2,5"     = those indices re-post as individual T2 messages
"reject 3"       = that index → kill-bin
"edit 4: <copy>" = manual edit; that draft updates with the new body, posts as T2

SLA 4h. No reaction by then → all items demote to T2 individually.
```

## Reaction parsing (deterministic)

EOD wrap and aging-check shifts both parse open batches. First-match-wins per batch:

1. **Thread reply matches `^reject (\d+(,\s*\d+)*)$`** — those indices archive to kill-bin.
2. **Thread reply matches `^demote (\d+(,\s*\d+)*)$`** — those indices re-post as T2 individual messages with a `(demoted from <batch_id>)` footer line, then are removed from the batch.
3. **Thread reply matches `^edit (\d+):\s*(.+)$`** — that draft's body is replaced; it re-posts as a T2 individual message with the new copy and `(edited from <batch_id>)` footer.
4. **Parent message has 👎** — every item not yet rejected/demoted/edited goes to kill-bin.
5. **Parent message has ✅** — every item not yet rejected/demoted/edited is approved-send.
6. **Neither, and batch is past 4h SLA** — every unresolved item demotes to T2 individual messages.

The parser writes one event per item to `60_Lessons/batches/YYYY-MM-DD.md` (see Idempotency below).

## Idempotency

Each batch logs once and only once. Path: `60_Lessons/batches/YYYY-MM-DD.md`. On every parse pass, the parser checks whether the batch_id already has a `[processed]` line in today's batches file; if so, it skips. The batch is fully resolved when every item has one of these terminal states: `approved-send`, `kill-bin`, `demoted-to-T2`, `edited-and-demoted`. Once all items are terminal, write the `[processed]` line.

Format of the batches file:

```markdown
# Batches — 2026-05-06

## T1-2026-05-06-0700-morning-brief

Posted: 07:04 ET | Items: 5 | SLA expires: 11:04 ET

| # | subject | recipient | resolution | resolved_at | reason |
|---|---|---|---|---|---|
| 1 | <subject> | <name> @ <company> | approved-send | 09:12 ET | parent ✅ |
| 2 | <subject> | <name> @ <company> | demoted-to-T2 | 08:30 ET | thread "demote 2" |
| 3 | <subject> | <name> @ <company> | kill-bin | 09:12 ET | parent 👎 (after partial resolves) |
| 4 | <subject> | <name> @ <company> | approved-send | 09:12 ET | parent ✅ |
| 5 | <subject> | <name> @ <company> | edited-and-demoted | 08:45 ET | thread "edit 5: ..." |

[processed] 2026-05-06 09:12 ET
```

## Drafter writeback on batch resolution

When an item resolves, update its `measurement-log.md` row:

- `approval_state` flips from `pending` to one of: `approved-send`, `rejected`, `edited`, `demoted` (T2 demotion is logged separately as the new T2 row carries the original approval_state once that resolves).
- `batch_id` stays populated even after resolution — it is the audit pointer.

## SLA enforcement (aging-check shift)

The 11:00 and 15:00 aging-check shifts (see `40_Plays/shifts/aging-check.md`) parse all open batches:

- Batch < 4h old + no parent reaction + no thread activity → leave alone.
- Batch ≥ 4h old + no parent reaction → demote-all-unresolved to T2 individual messages; mark batch terminal in batches file with `auto-demote-aged-out` reason.
- Batch < 4h old + partial thread activity (some demote/reject/edit) → wait for parent reaction or SLA.

## What batch-approve does NOT do

- It does not change the drafter. The drafter still emits one YAML payload per draft, with `tier: T1` and `batch_id: null`. The shift assigns batch_id at emit time.
- It does not touch T2. T2 drafts post individually as today.
- It does not auto-send. T0 is the only auto-send tier; see `40_Plays/graduated-send-authority.md`.
- It does not introduce new Slack tooling. Pure reaction + thread-reply parsing.

## Failure modes

- **Two shifts emit batches at the same minute.** Use `HHMM` granularity to disambiguate; if collision, append `-2`, `-3` etc.
- **Miles types `demote 2 and 5` instead of `demote 2,5`.** Parser falls back to natural-language: extract digits separated by non-digit chars, treat as the index list. Log the fuzzy match in the resolution `reason`.
- **Miles edits an item twice.** Last `edit N:` wins; the prior edited body is overwritten in the demoted T2 message.
- **Item index out of range.** Post a thread reply: `🚨 batch <batch_id>: index N out of range (1..M). Ignored. Try again.` Do not silently skip.
- **Parent has both ✅ and 👎.** Treat as "needs review" — demote all unresolved items to T2 and post a thread asking Miles to clarify.

## Cross-references

- `~/.claude/agents/onyxia-drafter.md` — Tier Classification rules; tier emission
- `40_Plays/graduated-send-authority.md` — T0 auto-send (batch-approve does not handle T0)
- `40_Plays/shifts/morning-brief.md` — primary T1 emitter
- `40_Plays/shifts/midday-signal.md` — secondary T1 emitter
- `40_Plays/shifts/eod-wrap.md` — final batch parse on the day
- `40_Plays/shifts/aging-check.md` — 4h SLA enforcement
- `40_Plays/killbin.md` — terminal state for rejected items
- `50_Intel/methodology/measurement-log.md` — `tier` + `batch_id` fields
