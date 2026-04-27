---
type: play
subtype: hunt
trigger: cron Sunday 20:00 ET (weekly, targeting biweekly volume)
vertical: all
created: 2026-04-21
tags: [play]
---

# Reactivation Sweep

Mine the dormant pool. 80 of 113 historical losses are re-attackable on the right trigger. No one is working them. This shift works them.

## When to run

Sunday 20:00 ET. Feeds Monday's morning brief with 10-15 pre-researched re-engagement plays ready for Miles to approve.

## The 4 dormant buckets

Every surviving HubSpot account + contact fits one of these at any given time.

### Bucket 1 — Closed-lost, non-responsive (high-signal reactivation)
Closed-lost where reason is "Non-responsive" or empty. Approximately 60-68 of 113 losses. These died of silence, not rejection.

**Reactivation trigger:** new CISO, new breach, new compliance deadline, new earnings call mentioning cyber, M&A.

### Bucket 2 — Closed-lost, budget / time frame (event-triggered reactivation)
Closed-lost where reason is "Budget constraints" or "Time frame." Approximately 25-30 of 113 losses. Died of bad timing.

**Reactivation trigger:** new fiscal year start, new funding round, new compliance mandate forcing spend, leadership change.

### Bucket 3 — Closed-lost, champion left (new-champion reactivation)
Closed-lost where reason is "Job change" OR the original champion moved. 3+ known, likely more hidden.

**Reactivation trigger:** former champion lands at a new company (net-new account opportunity) OR the replacement is named at the original account.

### Bucket 4 — Old MQL / engaged-then-ghosted, never worked
Contacts who filled a form, attended an event, or opened 3+ emails but never got a deal created. Not in HubSpot as lost, just dormant.

**Reactivation trigger:** any ICP-fit signal, often just "it's been 6+ months, re-approach with fresh trigger."

## Algorithm

1. Query HubSpot for bucket 1: `dealstage = "71106477"` (actual closed-lost) AND `closed_lost_reason IN ("Non-responsive", "")`.
2. Query bucket 2: same stage AND `closed_lost_reason IN ("Budget constraints", "Time frame")`.
3. Query bucket 3: same stage AND `closed_lost_reason = "Job change"` OR champion contact not currently at the company per ZoomInfo.
4. Query bucket 4: HubSpot contacts with `lifecycle_stage = "marketingqualifiedlead"` and no associated deal, or form submissions without follow-through.
5. For each candidate, check:
   - Does the company still exist (ZoomInfo lookup)
   - Has there been a trigger event in the last 90 days (ZoomInfo Scoops + news)
   - Is the original champion still there, or is there a new one
6. Score:
   - +2 for fresh trigger event (last 30 days)
   - +1 for industry tailwind (compliance deadline, breach in sector)
   - +1 for new CISO/VP Sec
   - -2 if contact left the company AND no replacement known
   - -1 if account has been silent >24 months
7. Rank. Take top 15.
8. Enrich the current right-person at each top-15 account via ZoomInfo before drafting. **Hard gate: no draft until ZoomInfo confirms the contact is current, email accuracy ≥85.**
9. Draft per the playbook — reference the trigger event, NOT the prior deal. The prospect doesn't need a reminder they said no.
10. Post a ranked list to `#miles-ai-ops`:
    - Top 3: full dossier + draft ready
    - 4-10: one-line summary + trigger + link to account note
    - 11-15: line items only, for Miles to prioritize next week if these 10 stall

## Output format

```
REACTIVATION SWEEP — YYYY-MM-DD

Bucket mined: Non-responsive losses (X), Budget/Time (Y), Champion-left (Z), Old MQL (W)

TOP 3 (drafts queued in Gmail)
1. [Prospect] — [Trigger] — [Why now in one line]
2. ...
3. ...

NEXT 7 (one-line)
4. [Prospect] — [Trigger]
...

NEXT 5 (line items, rank only)
11-15. [Name] [score]
```

## Hard rules

- **Enrich before draft.** No draft goes out without a fresh ZoomInfo match on the current contact. Lose one 8-month-old email address and you land in spam.
- **Reference the trigger, not the old deal.** "Saw your new CISO announcement" not "following up on our conversation from 2024."
- **One draft per run per account.** Don't stack 3 drafts on the same prospect.
- **Cap total output at 15.** Volume for volume's sake is noise.
- **Territory check.** Skip anyone owned by another active rep (Brad 77002456, Sivan 328493480) unless they've been dormant >12 months.

## Expected output volume

Weekly: 10-15 enriched + 3 drafted.
Quarterly: ~120 re-engagement attempts, targeting 8-12% reply rate on fresh triggers.

## Retiring a record

After 2 reactivation attempts in a 12-month window with no reply, move to `99_Archive/` and stop touching. Not every loss is revivable. The sweep is not a guilt trip.

## Runs
Every draft this play creates must append a row to [[../../50_Intel/methodology/measurement-log]] with `play_source = reactivation-sweep`.

| date | bucket 1 | bucket 2 | bucket 3 | bucket 4 | drafts staged | replies | meetings |
|---|---|---|---|---|---|---|---|
| 2026-04-27 | 68 | 28 | 3 | 0 | 3 | — | — |

