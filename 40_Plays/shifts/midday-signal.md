---
type: play
subtype: shift
trigger: cron weekday 12:00 ET
tags: [play, shift]
---

# Shift — Midday Signal Check (12:00 ET weekdays)

Short midday pulse.

## Prompt for the subagent

You are running the midday signal check. Read vault baseline first.

1. Check RB2B channel since 07:00 ET for new visitors. Cross-ref against active accounts.
2. Check HubSpot for replies and stage changes since morning brief.
3. Check Gmail for responses to recently-sent drafts.
4. If anything is hot, post to `#miles-ai-ops`:

```
MIDDAY — {{timestamp}}

Replies
- [Contact @ Account] → [one-line summary]

Stage changes
- [Account] → [from stage → to stage]

Hot visitors
- [Company] → [fit check] → [action]

Nothing hot → post "midday clean" and move on.
```

5. Append findings to today's daily note.

## Short post rule
If there's nothing material, post a one-liner: "midday clean, next shift at 16:30 ET." Don't pad.
