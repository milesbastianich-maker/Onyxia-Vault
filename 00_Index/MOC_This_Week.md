# MOC — This Week

Hand-maintained focus file. Claude reads this first every session.

Week: 2026-W18 (Apr 27 - May 3)

## Top 3 to push
1. **People Inc** — $150K. MEDDPICC blank, Jul 31 close. Still 1 anonymous contact in HubSpot. ZoomInfo enrich CIO/CISO is the first move. Single-contact death pattern.
2. **Rocket Companies** — Discovery call was Apr 24. No HubSpot deal created, no debrief, no Chris Burrows thread. Six days post-call. This is the edge.
3. **Starboard Group** — $50K, POC, May 31 close. "Rob Intro" call Apr 30 at 11:30 AM ET. 44 days since last note. Prep before the call, qualify Rob's authority.

_(Medusind: Jigar Shah thread live. Bala Iyer / John DeJager multi-thread not started — still a priority but pushed to #4 by Starboard's live meeting.)_
_(Mitsubishi Heavy: MNDA forwarded Apr 20, nine days no response. Follow up or flag as stalled.)_
_(JRM: Justin Hershkowitz confirmed Manager of InfoSec. Asked about VARs Apr 29 — soft buying signal. Miles to respond manually.)_

## Top 3 new conversations to open
1. **Jessica Kruse** (OCC) — MD GRC, SEC clearing cyber obligations. Draft has been ready. Overdue.
2. **Leilani Farol** (First Horizon Bank) — sent Apr 22. Waiting reply.
3. **CyberDiligent (Russell Okoth)** — 2x CISO, IANS Faculty, met Apr 29. Potential finserv referral channel. Follow-up email to establish partner motion.

## One play to run this week
Sivan peer-intro. Russell Okoth (CyberDiligent) is a candidate to co-host or refer into finserv accounts.

## Upcoming
- **Apr 30:** Akuvo POC placeholder (11 AM ET). Starboard "Rob Intro" (11:30 AM ET). Spire Orthopedic (2:30 PM ET).
- **May 13:** Onyxia & Meyer (Hold).
- **May 19:** NYC Cyber Leadership Dinner. 5 RSVPs in today (Stanley Garcia, Rich Warner, Ashraf Gad, Eric Karpman, Diana).
- **May 21:** Onyxia @ Yankee Stadium.
- Fri 4pm: weekly review → `60_Lessons/2026-W18-review.md`.

## Deals requiring attention in next 7 days
```dataview
TABLE stage, amount, next_action_date
FROM "10_Accounts"
WHERE contains(tags, "active") AND next_action_date <= date(today) + dur(7 days)
SORT next_action_date ASC
```
