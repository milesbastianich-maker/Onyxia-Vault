---
type: play
subtype: maintenance
trigger: first business day of each calendar quarter, 09:00 ET
vertical: all
active: true
created: 2026-04-22
tags: [play]
---

# Quarterly Self-Audit

Per CLAUDE.md mandate (Intelligence development loop, Quarterly section). Has never run. This play is the protocol.

## Schedule

**LIVE.** Remote trigger `trig_01Myhs2K7Hh9do959Zq9D85F` wired 2026-04-22.
Cron: `0 13 1 1,4,7,10 *` (UTC). First run: **2026-07-01 09:03 EDT**. Manage at https://claude.ai/code/scheduled/trig_01Myhs2K7Hh9do959Zq9D85F.

### Timezone note

Cron runs in UTC. 13:00 UTC = 09:00 ET during EDT (Apr/Jul/Oct firings). 13:00 UTC = 08:00 ET on Jan 1 (EST). One-hour drift in Q1 only. Acceptable vs. running two separate triggers.

If the first falls on a weekend, the trigger still fires. Miles reacts Monday.

## Protocol

Four audits, in order.

### 1. CLAUDE.md rule audit

- Read every rule in `00_Index/CLAUDE.md`.
- For each rule, grep across `40_Plays/`, `30_Meetings/*-debrief.md`, `60_Lessons/`, and `70_Daily/` for references or enforcements in the last 90 days.
- **Remove** rules with zero references in 90 days. Archive removed text to `99_Archive/claude-md-YYYY-QN-pruned.md`.
- **Promote** rules with 20+ references to "hard" status. Move into the first-paragraph hard-rule block.
- Stable middle ground (1-19 references) stays put.

### 2. Tag vocabulary audit

Use Dataview to count tag usage over 90 days:

```dataview
TABLE length(rows) as "uses"
FROM ""
WHERE file.mtime >= date(today) - dur(90 days)
FLATTEN file.tags as t
GROUP BY t
```

- **Prune** tags with zero uses in 90 days from the CLAUDE.md closed vocabulary.
- **Flag** unknown tags that appear in files (tag drift). Propose canonical replacement per tag.
- Record diffs in the output file.

### 3. Template audit

For each file in `90_Templates/`:

- Pull 10 most recent files created from that template (match on frontmatter structure).
- Compare actual structure to the template.
- If 3 or more have drifted (missing sections, renamed headers, different frontmatter fields), **fix the template at the source**. Do not fix the drifted files; that is retroactive noise. Fix forward.
- Record each drift in the output.

### 4. Play ranking audit

Cross-reference with [[../50_Intel/methodology/measurement-log]]:

- Any play with 0 conversions in 90 days: propose retire.
- Any play ranked top-3 by conversion two quarters running: flag as core, note in `50_Intel/playbook/closed-won-patterns.md`.

## Output

Single file per quarter:

`60_Lessons/quarterly/YYYY-QN-audit.md`

Structure:

```
---
type: lesson
subtype: quarterly-audit
quarter: YYYY-QN
tags: [lesson]
---

# Quarterly Audit YYYY-QN

## Summary
- CLAUDE.md rules removed: N
- CLAUDE.md rules promoted: N
- Tags pruned: N
- Templates fixed: N
- Plays retired: N
- Plays promoted to core: N

## CLAUDE.md diff
Before / after per rule.

## Tag vocabulary diff
Before / after per tag.

## Template diff
Per-template before / after.

## Play ranking delta
Retire + promote list with numbers.
```

## Approval gate

Before any write to `00_Index/CLAUDE.md` or `90_Templates/`:

1. Post the diff summary to `#miles-ai-ops`.
2. Await Miles's ✅ on the full diff (single reaction, single post).
3. On ✅: apply edits, commit with message `claude: quarterly audit YYYY-QN`.
4. On ✏️: Miles posts corrections in thread. Apply thread version.
5. On 👎: log the rejection. No writes. Re-propose next quarter with reason addressed.

The `60_Lessons/quarterly/YYYY-QN-audit.md` file itself can be written before approval (that is analysis, not policy). Only `CLAUDE.md` + `90_Templates/` require the gate.

## What this does NOT do

- Does not delete closed-won/closed-lost playbook files. Those are sacred per session rules.
- Does not touch `99_Archive/`.
- Does not rewrite `10_Accounts/*.md` timelines. Timelines are append-only.

## Runs

- YYYY-MM-DD | quarter | summary
