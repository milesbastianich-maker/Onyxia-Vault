---
type: meeting
subtype: index
tags: [meeting]
---

# 30_Meetings

Meeting prep and debrief notes. One file per meeting.

## Filename convention

`YYYY-MM-DD-{company-slug}-{prep|debrief}.md`

Example: `2026-04-25-acme-prep.md`, `2026-04-25-acme-debrief.md`.

## Prep template

See `90_Templates/tpl-meeting-prep.md`. Full structure used by the pre-meeting-prep shift:

```
---
type: meeting
subtype: prep
date: YYYY-MM-DD
company: "[[../10_Accounts/{company}]]"
attendees: ["[[../20_Contacts/{contact}]]", ...]
meeting_type: discovery | demo | poc | negotiation | check-in
duration_min: X
tags: [meeting, #stage/{stage}]
---

# {Company} — {meeting_type} prep — YYYY-MM-DD

## Meeting context
## Account state (MEDDPICC pull)
## Last-touch thread
## Trigger events (last 14 days)
## Proposed agenda
## MEDDPICC gaps to close this meeting
## Likely objections
## CTA ladder choice
## Wikilinks
```

## Debrief template

See `90_Templates/tpl-meeting-debrief.md`.

## Owning play

`40_Plays/shifts/pre-meeting-prep.md` (daily 09:00 ET). Pre-14-day sweeps run from the same play.

## 14-day pre-work scan log

- **2026-04-22** — scan attempted for next 14 days (2026-04-22 through 2026-05-06). Google Calendar MCP tool not available in this agent's environment (`mcp__claude_ai_Google_Calendar__list_events` not loaded). Zero dossiers written. Friday synthesis should re-run once calendar tool is reattached, or main thread should provide a manual event list.
