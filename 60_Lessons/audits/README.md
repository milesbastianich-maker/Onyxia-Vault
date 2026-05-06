---
type: index
folder: 60_Lessons/audits
created: 2026-05-05
tags: [index]
---

# Audit Logs

Output target for `onyxia-auditor` runs.

- Mini sweep: every Friday as part of `40_Plays/shifts/weekly-synthesis.md`. Tag hygiene, frontmatter, orphans, intelligence promotion candidates.
- Full sweep: quarterly per `40_Plays/quarterly-self-audit.md`. Adds template drift, HubSpot cache freshness, rule fire-rate.
- Ad-hoc: when `onyxia-operator` notices specific drift.

## File naming

`YYYY-MM-DD-{mini|full}.md`

Each finding has an ACK status. Auto-fixable findings (tag style normalization, broken wikilink to single obvious successor, missing `created` frontmatter backfilled from mtime) may be executed immediately. Everything else waits for Miles's `#miles-ai-ops` reaction.

## Why this folder exists

Created 2026-05-05 per the brain audit. Prior to today, the auditor agent referenced this folder in its agent prompt but the folder did not exist — meaning the auditor had likely never written a real audit log. The 2026-05-05 brain + leverage menu audits were doing the auditor's job at opus pricing. Cost-correcting that.
