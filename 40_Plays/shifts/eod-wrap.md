---
type: play
subtype: shift
trigger: cron weekday 16:30 ET
tags: [play, shift]
---

# Shift — EOD Wrap (16:30 ET weekdays)

End-of-day accountability + tomorrow's setup.

## Prompt for the subagent

You are running the EOD wrap for Miles. Read vault baseline including `40_Plays/rejection-feedback.md` and `40_Plays/reply-intent-parser.md`.

1. Read today's daily note + all vault commits since 07:00 ET.
2. Check HubSpot for activities logged today across all Miles-owned deals.
3. **Run reply parser final pass** per `40_Plays/reply-intent-parser.md` on any Gmail replies received since midday check.
4. **Run rejection capture** per `40_Plays/rejection-feedback.md`:
   - Scan `#miles-ai-ops` for 👎 / ✅ / ✏️ reactions on today's draft posts
   - For each 👎 without an in-thread reason, post a follow-up asking Miles for a one-line reason
   - Write `60_Lessons/rejections/YYYY-MM-DD.md` summarizing approvals, rejections, reasons
5. Summarize:

```
EOD WRAP — {{date}}

What I did today
- [drafted / enriched / researched / logged — with links]

Awaiting Miles's approval
- [draft for X — in Gmail + in ops channel]
- [follow-up to Y — in ops channel]

What slipped
- [task / account / action that didn't happen + why]

Tomorrow's top 3
1. ...
2. ...
3. ...
```

4. Post to `#miles-ai-ops`.
5. Update `~/ObsidianVault/00_Index/MOC_This_Week.md` "Top 3 to push" if day's events shifted priority.
6. Commit vault.
