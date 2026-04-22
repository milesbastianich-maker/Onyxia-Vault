---
type: intel
subtype: hunt-log
date: 2026-04-22
for_send_date: 2026-04-23
created: 2026-04-22
tags: [intel, hunt, signal-log]
---

# Open-Season Hunt — 2026-04-22

Follow-up hunt to the morning's healthcare top-10 (see `2026-04-22-top10-hunt.md`). Miles's brief: "everything is open season unless it's a deal or there's activity within the last month or two." Target: 10 more verified prospects, cross-vertical, clean HubSpot.

## Territory rules

- **Skip** if account has an open deal stage (not closed-lost / closed-won).
- **Skip** if HubSpot activity in the last 60 days.
- **Open season** otherwise, across verticals — including Brad-owned territory that's stale.

## Methodology

| Strategy | Source | Filter |
|---|---|---|
| A. New-seat C-level (30–180 days) | ZoomInfo `search_scoops` + exec-move scoops | CIO / CISO / CSO / CTO / CDIO starts since 2025-11, 500-100K employees |
| B. Role-match tenured | ZoomInfo `search_contacts` by title | CSO/CISO at top-tier regulated verticals (banking, defense, pharma, energy) |
| C. HubSpot dedupe | HubSpot `search_crm_objects` | Exclude any account with open deal or <60d activity |

Composite: ICP fit × trigger-recency × regulatory forcing-function.

## Top 10 locked

Cross-vertical to avoid over-concentration + preserve territory lines. Kept 1-2 per vertical.

| # | Company | Ticker | Rev | Emp | Vertical | Contact | Title | Start | Email | Variant |
|---|---------|--------|-----|-----|----------|---------|-------|-------|-------|---------|
| 1 | SMBC Group | TSE:8316 | $26.3B | 101K | Banking | Donna Hart | CISO (Americas) | tenured | donna.hart@smbcgroup.com | Tightened |
| 2 | Ryerson | NYSE:RYI | $4.47B | 4.3K | Manufacturing | Frank Williams | CIO | 2026-01-01 | frank.williams@ryerson.com | Question-led |
| 3 | V2X | NYSE:VVX | $4.48B | 16.2K | Defense/Gov | Tacuma King | CSO | 2022-08-01 | tacuma.king@gov2x.com | Tightened |
| 4 | CenterPoint Energy | NYSE:CNP | $9.36B | 8.8K | Utility | Bradley Krol | VP & CTO | 2025-11-14 | brad.krol@centerpointenergy.com | Question-led |
| 5 | BioMarin | NASDAQ:BMRN | $3.22B | 3.2K | Pharma | Arpit Davé | EVP & CDIO | 2026-01-01 | adave@biomarin.com | Question-led |
| 6 | Crawford & Company | NYSE:CRD.A | $1.31B | 9.1K | Insurance | Jemin Thakkar | Global CIO | 2026-04-01 | jemin.thakkar@us.crawco.com | Question-led |
| 7 | Discovery Education | private | $238M | 600 | EdTech | Kara Schlageter | CISO | tenured | kara_schlageter@discovery.com | Tightened |
| 8 | Princeton University | private | $2.56B | 9.1K | Higher-Ed | Donna Tatro | CISO | 2026-03-01 | tatro@princeton.edu | Question-led |
| 9 | Fairleigh Dickinson | private | $309M | 2.5K | Higher-Ed | Sean Jameson | VP & CIO | 2026-03-01 | sean_jameson@fdu.edu | Question-led |
| 10 | Messer Construction | private | $1.62B | 1.7K | Construction | Christopher Hickok | VP & CIO | 2025-12-01 | chickok@messer.com | Question-led |

**Variant mix:** 7 Question-led (new-seat 30-180d) + 3 Tightened (tenured / specific-fact). No Acknowledge-the-cold this batch.

## Candidate swaps

- **Cast & Crew → Fairleigh Dickinson University:** Cast & Crew PROTECTED — 2 active deals + 8-day activity. Swapped for FDU (clean, Sean Jameson 6-week new VP+CIO).
- **V2X primary swap:** Mike Uster (CIO) ZoomInfo record still had stale `mike.uster@vectrus.com` (pre-2022 merger domain). Switched primary to **Tacuma King (CSO)** — 98 accuracy, verified `tacuma.king@gov2x.com`, 3+ yr tenure through the merger. Mike Uster stays as Rank 2 (email format-guessed `mike.uster@gov2x.com`, needs verify).

## Princeton deal check

HubSpot shows 2 Princeton records at `dealstage: 58503741`. Last-modified 2024-08 and 2025-10 — likely stale closed-lost but verify stage-label before outreach. If stage is "closedlost", proceed; if active, stop and ask Miles.

## Methodology lessons

- The morning's healthcare hunt hit the Brad-owned territory wall. Going cross-vertical this hunt eliminated that constraint — 9 of 10 are clean HubSpot whitespace (Princeton has 2 likely-stale deals, verify).
- ZoomInfo position-start-date is not populated for all contacts even when validDate is recent. Absence of start date ≠ new-seat; treat as tenured.
- Domain migration after M&A (Vectrus → V2X via gov2x.com) can leave ZoomInfo records stale even on high-accuracy contacts. Always spot-check domain via a second contact at the same company.
- EVP-level C-suite combined roles (e.g., Arpit Davé's EVP & CDIO) are marked `VP-Level` by ZoomInfo's management-level enum but function as C-Level. Respect the title string, not the enum.

## Drafter brief

10 first-touch drafts, routed to hardened `onyxia-drafter` with:
- Variant per row above
- Draft-scoring rubric ≥4/5 required before Gmail create_draft
- NO HTML comments in body
- Personalization Level 3+ required
- Register-A voice only
- Source citation: title + start date + vertical-specific regulatory pressure + company-specific scale metric

## Send queue

All 10 drafts staged in Gmail drafts folder. Awaiting Miles ✅ per-draft.

## Cross-references

- [[../methodology/touch-tracker]]
- [[../methodology/draft-scoring]]
- [[../product/winning-openers]]
- [[../product/forbidden-words]]
- [[./2026-04-22-top10-hunt]] — morning's healthcare hunt
