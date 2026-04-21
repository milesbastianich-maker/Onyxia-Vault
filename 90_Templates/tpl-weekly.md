---
type: lesson
week: <% tp.date.now("YYYY-[W]WW") %>
period_start: 
period_end: 
tags: [lesson]
---

# Week <% tp.date.now("YYYY-[W]WW") %>

## Pipeline movement
```dataview
TABLE stage, amount, last_touch
FROM "10_Accounts"
WHERE contains(tags, "active") AND date(last_touch) >= date(today) - dur(7 days)
SORT last_touch DESC
```

## MEDDPICC gaps (at-risk deals by definition)
Active accounts where any key slot is empty.

```dataview
LIST
FROM "10_Accounts"
WHERE contains(tags, "active") AND (!economic_buyer OR !champion OR !paper_process OR !metrics)
```

## Meetings held
Count: 
Advanced to next stage: 
Top insight per meeting (one bullet each):

## Touches
Emails: 
Calls connected: 
Voicemails: 
Best-performing play this week: [[]]

## Wins
What closed. What advanced. What a champion escalated for us.

## Losses / stalls
Deals slipped or quiet >14 days. One-sentence hypothesis each.

## Lesson of the week
One paragraph. A pattern that showed up twice. What I will do differently next week.

## Next week
Top 3 deals to push.
Top 3 new conversations to open.
One play to run.
