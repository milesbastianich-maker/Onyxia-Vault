---
type: play
active: false
blast_radius: low-medium
rollback_criteria: 2 consecutive false-stall escalations in 30 days
measurement_precondition: 10+ live POCs in measurement-log with stall-event tracking
created: 2026-04-22
tags: [play, autonomy]
---

# Autonomy — Stalled POC Auto-Escalation

## What it does

When a deal in stage `decisionmakerboughtin` (POC/Partnership) has no HubSpot activity in 10 consecutive days AND MEDDPICC slots are still open AND no planned next-action-date covers the gap, the operator:

1. Pulls the full deal file + all contacts.
2. Runs onyxia-researcher on any trigger-event that happened in the last 10 days (exec change, breach, new funding, M&A).
3. Drafts THREE parallel re-engagement angles:
   - Champion-focused (to the current primary): "saw <trigger event> — how does it shift the <POC use case>?"
   - Economic-buyer-focused (to CFO or CIO): "the <trigger event> is the kind of thing the POC was designed to catch."
   - Peer-intro (to Sivan-to-CISO, only if CTA-ladder peer-call available this week).
4. Posts all three options to `#miles-ai-ops` for ✅ (choose one or edit).

## Why

POC-stall is the single most common late-stage failure mode in `closed-lost-patterns.md`. "Onyxia loses to silence not competitors." 10 days is the inflection — any longer and the POC thread is colder than cold. Trigger-event re-hooks are the pattern that works when the cold restart doesn't.

## Trigger conditions

- Deal stage = `decisionmakerboughtin` (POC/Partnership per inverted-label translation).
- No activity (email, call, meeting) in HubSpot engagements associated with the deal for 10 consecutive days.
- MEDDPICC slots in vault account file still blank on: Metrics, Decision Criteria, or Paper Process.
- No `next_action_date` covering the current date + 7 days.

## Pipeline

1. **Detect** — EOD shift scans Miles-owned deals in POC stage daily. If 10-day stall: queue.
2. **Research** — onyxia-researcher pulls 10-day trigger events on the account.
3. **Draft** — onyxia-drafter produces three options with distinct angles.
4. **Post** to `#miles-ai-ops` with the three drafts + context.
5. **Miles picks one** via ✅ reaction on the option letter (A / B / C), 👎 to drop, ✏️ to edit.

## Blast radius

Low-medium. Three drafts, Miles picks one. Draft-only. Worst case: Miles ignores → deal keeps stalling (no worse than status quo). The specialist effort is in research quality + voice-clean drafts.

## Rollback criteria

- If 2 consecutive auto-escalations get 👎 with reason "this wasn't stalled, I was working it" → flip `active: false` + investigate stall-detection logic.
- If a draft accidentally goes to an excluded contact → kill immediately.

## Measurement precondition

10+ live POCs with stall-event instrumentation in `measurement-log.md`. Each POC logs: stage entry date, first activity, MEDDPICC slot fill rate, any stall event (>10 day gap). Otherwise the "what's a stall" definition is theoretical.

## Kill switch

Frontmatter flip.

## Cross-references

- [[./reply-intent-parser]]
- [[./graduated-send-authority]]
- [[../50_Intel/playbook/closed-lost-patterns]]
- [[../50_Intel/methodology/measurement-log]]
