---
type: play
subtype: infrastructure
active: true
owner: automated
tags: [play, intel]
created: 2026-04-21
---

# Continuous Research

Three scheduled Claude agents that keep the vault's intel layer fresh without Miles lifting a finger. Daily, weekly, monthly. Each writes to a defined slot, posts to `#miles-ai-ops`, commits to the repo.

## The three triggers

| Trigger | Cadence | UTC cron | ET | Purpose |
|---|---|---|---|---|
| Daily Signal Scan | Weekdays | `30 10 * * 1-5` | 06:30 EDT | Pre-brief breach + exec-move sweep on top-20 `#active` accounts |
| Weekly Vertical Trends | Mondays | `0 12 * * 1` | 08:00 EDT | Healthcare, finserv, manufacturing, crit-infra trend synthesis |
| Monthly Regulatory Refresh | 1st of month | `0 12 1 * *` | 08:00 EDT | Diff regulatory-calendar.md against live reg state |

RemoteTrigger environment: `env_017PoHnwSxdYMprtq82eES16` (Lil Basti).
Repo: `https://github.com/milesbastianich-maker/Onyxia-Vault`.
Model: `claude-sonnet-4-6`.

## Trigger IDs

Wired 2026-04-22 via RemoteTrigger API.

- Daily Signal Scan: `trig_016oRmWHLmuEjhNHcEQiesJH` — first fire 2026-04-22 06:35 EDT
- Weekly Vertical Trends: `trig_01BdctJWPma1eVLcLUfdF6rr` — first fire 2026-04-27 08:02 EDT Mon
- Monthly Regulatory Refresh: `trig_01NeJDYcKGHpayZxc7EeBi3G` — first fire 2026-05-01 08:02 EDT

Manage at https://claude.ai/code/scheduled.

## What each trigger writes

### Daily Signal Scan (06:30 ET weekdays)

Runs 30 minutes before the morning brief so the brief can read its output.

- Reads top-20 `#active` accounts from `10_Accounts/`, sorted by deal amount.
- Runs ZoomInfo `enrich_scoops` and `enrich_news` for each (last 24h).
- WebSearch: `{company} breach OR CISO OR cyber OR incident` last 24h.
- Classifies severity: critical / high / medium / low.
- Appends to `50_Intel/signal-log/YYYY-MM-DD.md`. One bullet per signal.
- Critical signals: posts to `#miles-ai-ops` with `@here` and writes `50_Intel/signal-log/_morning-queue.md` for the 07:00 brief to pick up.
- Commits `claude: daily signal scan YYYY-MM-DD`, pushes.

### Weekly Vertical Trends (08:00 ET Monday)

- For healthcare, financial-services, manufacturing, critical-infrastructure:
  - WebSearch last 7 days: breach, exec move, regulatory filing.
  - WebFetch SEC EDGAR for recent 10-K / 8-K filings with cyber mentions.
  - Top 3-5 items per vertical.
- Writes synthesis to `50_Intel/industry/weekly-YYYY-WW.md` with wikilinks to affected accounts.
- If an item hits an `#active` account, flags in file + appends to `50_Intel/signal-log/_next-morning-queue.md`.
- Posts summary one-liner + file link to `#miles-ai-ops`.
- Commits `claude: weekly vertical trends YYYY-WW`, pushes.

### Monthly Regulatory Refresh (08:00 ET 1st of month)

- WebSearch: HIPAA, SEC cyber rule, NYDFS 500, OCC cyber guidance, NIST CSF, CMMC, TSA crit-infra, CISA alerts. 60-day forward horizon.
- Diff against `50_Intel/industry/regulatory-calendar.md`. Append new items.
- Items with compliance date in next 60 days get `#window/60d`.
- For each 60-day item, cross-reference `10_Accounts/` by vertical, flag with wikilinks.
- Posts monthly digest to `#miles-ai-ops`.
- Commits `claude: monthly regulatory refresh YYYY-MM`, pushes.

## How the cadence feeds the rest of the system

1. **Daily scan → morning brief.** The brief at 07:00 ET reads `_morning-queue.md` first. Critical signals surface as the first line of the brief.
2. **Weekly trends → Monday planning.** The Monday 09:00 ET icp-lookalike-hunt has fresh vertical context to seed from. The Friday weekly-synthesis reads from `50_Intel/industry/weekly-*.md` when scoring play performance by vertical.
3. **Monthly reg refresh → quarterly audit.** Reg changes with 60-day windows trigger account flags. The quarterly-self-audit play reads 3 months of refresh outputs to re-rank compliance-driven verticals.

## Failure modes

- **Signal log duplication.** If a signal hits in both the daily scan and the weekly trends file, the weekly-synthesis dedupes on source URL.
- **Cron overlap.** Monthly fires on the 1st. If the 1st is a Monday, weekly and monthly both fire at 08:00 ET. Both write to different slots (`industry/weekly-*.md` vs `industry/regulatory-calendar.md`), no collision.
- **API outage.** Each trigger must commit partial output. Never skip the vault write because one API call failed. Mark `_partial pull on {source}_` in the file.

## Operator notes

- Trigger names in RemoteTrigger are `Onyxia Daily Signal Scan`, `Onyxia Weekly Vertical Trends`, `Onyxia Monthly Regulatory Refresh`.
- allowed_tools for all three: `Bash, Read, Write, Edit, Glob, Grep, WebSearch, WebFetch`.
- MCP connections: Slack + ZoomInfo (daily), Slack (weekly + monthly).
- No outbound email. No HubSpot writes. Vault + Slack + git only.

## Cross-references

- [[shifts/morning-brief]]
- [[shifts/weekly-synthesis]]
- [[hunt/trigger-event-hunt]]
- [[quarterly-self-audit]]
