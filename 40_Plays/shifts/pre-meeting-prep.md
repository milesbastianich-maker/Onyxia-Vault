---
type: play
subtype: shift
trigger: cron weekday 09:00 ET (preps all today's meetings)
tags: [play, shift]
---

# Shift — Pre-meeting Prep (09:00 ET weekdays)

Preps every meeting on Miles's calendar for today. Prospect-facing meetings get full dossier + MEDDPICC + last-touch summary. Internal meetings get a light agenda note.

## Prompt for the agent

You are running pre-meeting prep for Miles Bastianich. Time is 09:00 ET.

1. Read Google Calendar: all events for today (09:00 - 23:59 ET) on Miles's primary calendar.
2. For each event with external attendees (email domain != onyxia.io):
   - Look up the attendee(s) in `20_Contacts/` — if known, load their file
   - Look up the company in `10_Accounts/` — if known, load MEDDPICC + timeline
   - If either is missing, enrich via ZoomInfo first (company + contact)
   - Check HubSpot for the live deal state
   - Check Gmail for the last 3 threads with the attendee(s)
   - Web search for breaking news on the company (last 7 days)
3. For each prospect meeting, compose a pre-meeting brief:
   ```
   PREP — [Company] — [Time ET] — Type (Discovery | POC | Exec briefing | Other)
   
   Attendees: [names + titles]
   Deal: $X, stage Y, days in stage Z
   MEDDPICC status: [gaps flagged]
   Last touch: [date, summary]
   Recent news: [1-2 lines]
   Goal for this call: [1 line — what's the commitment to get]
   3 questions to ask: [bullets]
   Risk / objection to prepare for: [1 line]
   ```
4. Post the full prep to `#miles-ai-ops` AND append to `30_Meetings/YYYY-MM-DD-{company}-prep.md` (create the file).
5. For internal-only meetings, skip the dossier. Just log the time + attendees in today's daily note.
6. git commit + push.

## Output cap

Max 3 detailed dossiers per run. If Miles has more than 3 prospect meetings in one day, the 4th+ get abbreviated: company, time, one-line status, link to account note.

## What this enables

Miles reads the brief on his phone while walking to the meeting. Never shows up cold. MEDDPICC gaps are surfaced so he can steer the conversation to fill them.

## Weekly synthesis use

How many meetings held this week + how many had prep briefs + meeting-to-next-step conversion rate. Over time, conversion should rise with consistent prep.
