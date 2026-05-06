---
type: play
subtype: shift
trigger: cron weekday 07:00 ET
tags: [play, shift]
---

# Shift — Morning Brief (07:00 ET weekdays)

Fired by scheduled agent. Runs `onyxia-operator` subagent with this prompt.

## Prompt for the subagent

You are running the morning brief for Miles. Today is {{today}}.

1. Read `~/ObsidianVault/00_Index/MOC_This_Week.md`.
2. Read `~/ObsidianVault/00_Index/CLAUDE.md` session ritual.
3. Check Slack `#rb2b` (or the RB2B channel Miles has named) for overnight visitor hits. Cross-reference hostnames against `~/ObsidianVault/10_Accounts/`.
4. Check HubSpot for:
   - Any deal stage changes since yesterday 17:00 ET
   - Any email replies from active deal contacts
   - Any new contacts added to active accounts
5. For every `#active` account with `next_action_date` in the next 7 days, pull current state.
6. Web search trigger events on the top 5 `#active` accounts (breach, exec hire, 10-K, M&A).
7. Compose a brief:

```
MORNING BRIEF — {{date}}

Overnight signals
- [hot RB2B visit: Company X | ICP fit? | suggested action]
- [trigger event: Company Y | source | so what]

HubSpot activity since 17:00 ET
- [stage change, reply, new contact with link]

Top 3 moves today
1. [Account] → [action] → [why now]
2. ...
3. ...

Deals needing attention in next 7 days
- [Account | next_action_date | what]
```

8. Post the brief to `#miles-ai-ops` (channel ID `C0AUB4DATP0`).
9. Append the brief to `~/ObsidianVault/70_Daily/{{date}}.md` under a `## Morning brief` section.
10. **If this shift produced any drafts (e.g., trigger-event-hunt fired and the drafter ran):** group by `tier` and post per `40_Plays/batch-approve.md`:
    - All `tier: T1` drafts collapse into ONE batch Slack message with `batch_id: T1-{{date}}-0700-morning-brief`. Write the batch_id back to each draft's measurement-log row.
    - Each `tier: T2` draft posts as its own individual Slack message (current behavior).
    - Each `tier: T0` draft skips Slack; sets HubSpot `ai_send_tier=T0` + `onyxia_outbound_status=queued`; writes audit row to `60_Lessons/auto-send-audit/YYYY-WW.md`.
11. Commit vault changes.

## Keep it tight
Max 300 words in the Slack post. Miles reads this on his phone.
