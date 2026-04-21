---
type: play
subtype: reply-branch
trigger: reply parser "Interested" branch with meeting-booking intent
vertical: all
active: false
created: 2026-04-22
tags: [play]
---

# Calendar Self-Booking

Sub-flow of [[reply-intent-parser]]. When a reply is classified "Interested" AND the body contains booking-intent language, this play proposes 3 specific times, drafts the reply, and (on approval) places a tentative hold on Miles's calendar.

Switch flips when n8n sub-flow in `~/onyxia-autopilot/SPEC.md` lands. Until then: `active: false`.

## Trigger conditions

All must be true:
1. Parser classified the reply as `Interested`.
2. Reply body contains one or more booking-intent tokens: "what times", "when works", "calendar", "book", "meet", "availability", "send times".
3. `active: true` in this file's frontmatter.

If any condition fails, fall back to the standard Interested branch (Calendly link or two-time propose per reply parser spec).

## Sub-flow

### Step 1. Read calendar

Pull Google Calendar for the next 7 business days. Exclude weekends.

### Step 2. Find 3 candidate slots

Constraints:
- Duration: 30 minutes.
- Start: 10:00 ET or later.
- End: 16:00 ET or earlier.
- No back-to-back. At least 15 minutes buffer before and after.
- No overlap with events tagged `focus-time`.
- No overlap with existing `tentative` holds from prior runs of this play (avoid double-booking same slot).
- Prefer 2 same-day-of-week options (Tue/Thu) plus 1 fallback, so Miles gets a real pick.

If fewer than 3 slots clear, return 2. If fewer than 2, fall back to the standard Interested branch with note "calendar too full for self-book this week, proposing manually."

### Step 3. Draft reply

Draft in Miles's voice. Short. No em dashes. No corporate jargon. Template:

```
Thanks, [First].

Three options next week:
- [Day, Mon DD, HH:MM ET]
- [Day, Mon DD, HH:MM ET]
- [Day, Mon DD, HH:MM ET]

Pick whichever. 30 minutes. If none work, send a window and I will match.

Miles
```

No em dashes. Parens fine.

### Step 4. Post to #miles-ai-ops

Standard draft-and-approve. Post includes:
- Thread link
- Classified intent + booking-intent tokens that matched
- The 3 proposed slots
- The draft

Await ✅ / ✏️ / 👎 per [[reply-intent-parser]] rules.

### Step 5. On approve

Two actions in sequence:
1. Send reply via Gmail.
2. Create three calendar holds, one per proposed slot:
   - Status: `tentative`
   - Title: `(hold) Onyxia + {Company}`
   - Attendees: prospect email added as OPTIONAL, not invited yet (Google Calendar API: `optional: true` + `sendUpdates: "none"`)
   - Description: links to the HubSpot contact + account note wikilink

The optional-not-invited detail matters. We do not send a calendar invite until the prospect picks one. Holds are for Miles's view only.

### Step 6. On prospect acceptance

When the reply parser classifies a follow-up reply as "Interested" AND body references one of the 3 proposed times:
1. Identify the chosen slot.
2. Promote that hold from `tentative` to `confirmed`.
3. Add prospect as REQUIRED attendee, `sendUpdates: "all"` (sends the invite).
4. Delete the other 2 holds.
5. Update title from `(hold)` to `Onyxia + {Company} ({Miles + First})`.
6. Post confirmation to `#miles-ai-ops`.

### Step 7. On edit or reject

- ✏️: Miles posts the corrected draft in thread. Bot sends the thread version. Calendar holds still created on send.
- 👎: Log rejection. No send. No holds. Fall back to manual.

## Edge cases

- **Prospect picks a time not on the list.** Parser detects a time token not matching any of the 3 holds. Flag to Miles, do not auto-confirm. Miles handles manually.
- **Prospect asks to reschedule.** Not handled by this play. Falls to manual branch.
- **Timezone mismatch.** If the reply signals a non-ET timezone, still propose in ET but include `({prospect tz} equivalent)` after each time. Pull tz from prospect's signature or ZoomInfo location.
- **Sivan loop needed.** If account note flags CISO persona + peer-call tier, add "Sivan may join" line to the draft but do NOT add Sivan as an attendee until Miles confirms.

## What this does NOT do

- Does not send calendar invites without Miles's approval on the reply.
- Does not auto-reschedule.
- Does not handle reply classifications other than "Interested" with booking intent.
- Does not bypass draft-and-approve. Reply still goes through Slack.

## Dependencies

- n8n sub-flow in `~/onyxia-autopilot/SPEC.md` must implement Google Calendar read + create + update with optional/required attendee toggle.
- Reply parser must pass booking-intent token detection into this branch.
- `focus-time` tag must be consistently applied on Miles's calendar (Miles's responsibility).

## Runs

- YYYY-MM-DD | [[Account]] | slots proposed, outcome
