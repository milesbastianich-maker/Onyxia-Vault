---
type: play
active: false
blast_radius: medium
rollback_criteria: single territory conflict OR single exclusion-list hit
measurement_precondition: 50+ rb2b hits tagged by fit score, 90-day outcome tracking
created: 2026-04-22
tags: [play, autonomy]
---

# Autonomy — RB2B Hot-Signal Auto-Book

## What it does

When RB2B posts a de-anonymized visitor to `#rb2b` that scores ≥4 fit AND the company is not in HubSpot AND the visitor title matches CISO/VP Sec/GRC Director, the operator:

1. Stages the account.
2. Multi-threads 2 contacts.
3. Drafts a "saw you on our site today" first-touch to the specific visitor.
4. Proposes 3 Calendar slots for a 20-minute peer call.
5. Posts the full package to `#miles-ai-ops` for single-✅ approval.

## Why

RB2B intent is the freshest signal in the stack — the prospect is literally on the website right now. The existing RB2B flow surfaces visitors in the morning brief (next day). Same-day response converts 5-10x better on intent signals per `external-patterns.md` Apollo/Outreach data. This closes the cycle time from 16h to 30 minutes.

## Trigger conditions

- New `#rb2b` channel post, parsed.
- Company score ≥4 (score-prospect-fit).
- Visitor title matches CISO, VP Security, Chief Security, GRC Director, Director Security, Head of Security.
- Company not in HubSpot with owner ≠ 86806986 (unless owner unset).
- Exclusion-list clean.

## Pipeline

1. **Parse** `#rb2b` post → structured record.
2. **Score** via score-prospect-fit.
3. **Gate** on fit + title + HubSpot + exclusion.
4. **Stage** via onyxia-hunter: account file, multi-thread map, measurement log row.
5. **Draft** via onyxia-drafter: first-touch email specifically referencing "saw you spent time on our <page>" — gated on fresh voice rules.
6. **Calendar-self-booking** (see separate play) proposes 3 slots.
7. **Post to #miles-ai-ops** with one-✅ approval structure:
   - Account card (1 line)
   - Visitor + role + LinkedIn URL
   - Draft body (full)
   - 3 proposed Calendar slots
   - ✅ = send + hold slots | ✏️ = edit before send | 👎 = drop

## Blast radius

Medium. Draft gated on Miles ✅. Account-staging is reversible (archive if wrong). Calendar holds are tentative (not-invited), only confirmed on ✅ + prospect pick.

## Rollback criteria

- ANY territory conflict (Brad-owned account gets staged by mistake) → flip `active: false`, add enhanced HubSpot dedupe, retrain.
- ANY exclusion-list hit that makes it past the gate → immediate kill + investigation.
- Miles 👎 rate on staged packages > 30% in a rolling 14-day window → pause + retrain scoring.

## Measurement precondition

50+ RB2B hits tagged in `measurement-log.md` with score + outcome (meeting booked / draft sent / dropped). The signal-intelligence-plan Workflow 07 + 07b should be live first — it provides the scoring infrastructure.

## Kill switch

Frontmatter flip. Polling 5 minutes.

## Cross-references

- [[../50_Intel/specs/2026-04-21-signal-intelligence-plan]]
- [[./calendar-self-booking]]
- [[./auto-promote-intelligence]]
- [[../50_Intel/icp]]
