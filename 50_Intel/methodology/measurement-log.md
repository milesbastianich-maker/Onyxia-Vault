---
type: intel
subtype: methodology
topic: per-draft measurement log
created: 2026-04-22
tags: [intel]
---

# Measurement Log (Per-Draft)

Every outbound draft that ships gets a row here. Weekly synthesis re-ranks plays against this data. Without it, there is nothing to learn from.

## Why markdown, not CSV

Vault convention is markdown with frontmatter-queryable tables. Dataview can read inline fields in markdown and return them as a query. Existing `50_Intel/` files (icp.md, closed-won-patterns.md) use the same pattern. CSV would be cleaner to diff but breaks Obsidian reading flow. Keep it in markdown.

## Field definitions

| Field | Values | Source |
|---|---|---|
| `draft_id` | `YYYY-MM-DD-{slug}` | Generated on draft creation |
| `sent_date` | `YYYY-MM-DD` or blank if not sent | Gmail send event |
| `trigger_type` | `new-ciso` / `breach` / `m&a` / `funding` / `compliance-deadline` / `earnings` / `rb2b-visit` / `lookalike` / `reactivation` / `cold-icp` | Play source |
| `vertical` | `healthcare` / `fins` / `mfg` / `ci` / `identity-saas` / `other` | ICP vertical |
| `hook_type` | `trigger-specificity` / `peer-intro` / `compliance-deadline` / `roi-data` / `referral` / `curiosity` | Opener angle |
| `persona` | `ciso` / `grc` / `vpsec` / `cio` / `cfo` / `gc` / `coo` / `other` | Target role |
| `play_source` | `sivan-peer-intro` / `trigger-event-hunt` / `icp-lookalike-hunt` / `intent-signal-hunt` / `vertical-saturation-hunt` / `reactivation-sweep` | Which play generated it |
| `cta_tier` | `passive` / `specific` / `peer-call` | See `40_Plays/cta-ladder.md` |
| `word_count` | integer | Draft body only, no sig |
| `reply_y_n` | `y` / `n` / `pending` | Gmail reply check |
| `reply_intent` | `interested` / `referral` / `not-now` / `hard-no` / `ooo` / `wrong-person` / `competitor` / `pricing` / `objection` / `ambiguous` / `none` | Reply parser output |
| `meeting_booked_y_n` | `y` / `n` / `pending` | Calendar event created |
| `approval_state` | `approved-send` / `rejected` / `edited` / `pending` | Slack reaction |
| `account` | wikilink to `10_Accounts/{Company}.md` | Vault |
| `contact` | wikilink to `20_Contacts/{Name}.md` | Vault |
| `notes` | free text, 1 line max | Human |

## Log entries

One row per draft. Appended by every hunt play + reply parser.

| draft_id | sent_date | trigger_type | vertical | hook_type | persona | play_source | cta_tier | word_count | reply_y_n | reply_intent | meeting_booked_y_n | approval_state | account | contact | notes |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 2026-05-05-plaid-tom-daniels | 2026-05-05 | reactivation | fins | trigger-specificity | ciso | reactivation-sweep | specific | 115 | pending | pending | pending | approved-send | [[Plaid]] | [[Tom Daniels]] | 22mo revival; Apr hiring-spike trigger; spine pain #2 stack drift; Hashal quote |
| 2026-05-05-johnmuir-sanjib-dutt | 2026-05-05 | reactivation | healthcare | trigger-specificity | ciso | reactivation-sweep | specific | 125 | pending | pending | pending | approved-send | [[John Muir Health]] | [[Sanjib Dutt]] | 88d revival w/ 4 prior unanswered; Priti Patel Feb 11 AI training quote; spine #5 multi-framework |
| 2026-05-05-sothebys-steven-kolombaris | 2026-05-05 | reactivation | other | trigger-specificity | ciso | reactivation-sweep | specific | 115 | pending | pending | pending | approved-send | [[Sotheby's]] | [[Steven Kolombaris]] | 14d silent on Apr 21 thread; Apr 23 $1.5B house record trigger; spine #2 stack across surfaces |
| 2026-05-05-inductive-jason-waits | 2026-05-05 | reactivation | mfg | trigger-specificity | ciso | reactivation-sweep | specific | 125 | pending | pending | pending | approved-send | [[Inductive Automation]] | [[Jason Waits]] | 7mo revival; Carl Gould Mar 27 cyber piece; spine #5; UNVERIFIED CTO title + CMMC relevance |
| 2026-05-05-alkami-anand-singh | 2026-05-05 | reactivation | fins | compliance-deadline | ciso | reactivation-sweep | specific | 140 | pending | pending | pending | approved-send | [[Alkami]] | [[Anand Singh]] | 17mo revival; Alex Shootman Apr 24 quote; public-co Item 1.05; spine #3 disclosure clock |

## Dataview queries (once rows exist)

Reply rate by hook_type this quarter:
```dataview
TABLE
  length(filter(rows, (r) => r.reply_y_n = "y")) as "replies",
  length(rows) as "total",
  round(length(filter(rows, (r) => r.reply_y_n = "y")) / length(rows) * 100, 1) as "reply %"
FROM "50_Intel/methodology"
WHERE type = "intel" AND subtype = "methodology"
GROUP BY hook_type
```

Meeting conversion by persona:
```dataview
TABLE persona, meeting_booked_y_n
FROM "50_Intel/methodology"
WHERE meeting_booked_y_n = "y"
```

## Retention

- Rows 90 days old move to `50_Intel/methodology/archive/measurement-log-YYYY-QQ.md`.
- Active file stays trailing-90-days for query speed.

## How plays write to this

Every hunt play's "Runs" section references this log. On draft creation, the play appends a row with `sent_date` blank and `approval_state = pending`. When Miles approves and it sends, the shift updates `sent_date` and `approval_state`. When a reply lands, parser updates `reply_y_n` and `reply_intent`. When a meeting is on calendar with this prospect, `meeting_booked_y_n = y`.

## What this unblocks

- Weekly synthesis re-ranks plays by actual reply + meeting rate.
- A/B hook variants get a ground truth.
- Graduated send authority needs 4+ weeks of data here before it's safe to propose.
- Retire plays with 0 conversions in 30 days = runnable query, not vibes.

## Cross-references
- [[objections]] — objection library, separate log
- [[../playbook/closed-won-patterns]] — historical reference
- [[../../40_Plays/reply-intent-parser]] — feeds reply fields
