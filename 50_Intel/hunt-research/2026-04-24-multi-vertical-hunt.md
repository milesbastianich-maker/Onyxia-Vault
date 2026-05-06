---
type: intel
subtype: hunt-research
date: 2026-04-24
tags: [intel, hunt-research]
---

# Multi-Vertical Hunt — 2026-04-24

Massive net-new prospect hunt across 5 expansion verticals. 12 Tier 1 accounts staged. 18 contacts mapped. 12 cold drafts ready for Gmail paste once token reauthed.

## Method

1. Read vault + ICP + voice rules + register-B forbidden list.
2. Pulled 200 most-recent HubSpot companies + ran ZoomInfo searches across 5 verticals: Software, Aerospace & Defense, Hospitality/Gaming, REITs, Higher Ed.
3. 35 candidates curated → deduped against HubSpot by domain IN filter (single search) → 27 already in HubSpot (Brad-owned, mostly stale 0-3 contacts).
4. Final cut: 12 accounts (8 net-new, 3 unowned-claimable, 1 Brad-touched but uncontested).
5. Multi-threaded each — pulled CISO/Sec Director per ZoomInfo `search_contacts` + `enrich_contacts` for verified emails.
6. Drafted Register-A cold opens. No Register-B mail-merge. No em dashes. No HTML comments in body.

## Vertical scoring carryover

Per `2026-04-22-vertical-expansion-ranking.md`:
- #1 SaaS/Tech (9/10) — 1,267 in HubSpot, 3 wins precedent
- #2 Defense (8/10) — CMMC Nov 10 hard deadline = strongest hook
- #3 Retail/Hospitality (7/10) — PCI 4.0.1 active fines
- #4 REITs (6/10) — SEC cyber rule, 2026 first full exam cycle
- #5 Higher Ed (5/10) — NIST 800-171 R3 + GLBA, no precedent

Skipped Legal (#6, 577-day cycle deprioritized).

## Final 12-account staged list

| # | Account | Vertical | ZI ID | HS Status | Fit | Trigger | Primary Contact | CTA Tier |
|---|---|---|---|---|---|---|---|---|
| 1 | Prologis | REIT | 31441750 | NET NEW | 5 | New CISO 2.5mo + SEC cyber rule | Donald Dawson, CISO | **peer-call** |
| 2 | KRATOS | Defense | 158630650 | NET NEW | 5 | CMMC Nov 10 deadline | Richard Gary, CIO | specific |
| 3 | Sierra Nevada Corp | Defense | 81019256 | NET NEW | 5 | CMMC Nov 10 + USAF Tier 1 Superior Supplier | Roben Sargent, VP/CSO | specific |
| 4 | DraftKings | Gaming | 348016779 | NET NEW | 5 | PCI 4.0.1 + state gaming reg + SEC cyber | Sam Bisbee, VP Infosec | specific |
| 5 | AvalonBay | REIT | 13882126 | NET NEW | 4 | SEC cyber + 2026 first full exam | Brett Durbin, Sec Director IT | specific |
| 6 | UIUC | Higher Ed | 4276954 | NET NEW | 4 | NIST 800-171 R3 + GLBA + DoD research | Michael Wrobel, CIO/Privacy | specific |
| 7 | Cornell | Higher Ed | 30247791 | NET NEW | 4 | NIST 800-171 R3 + GLBA + Weill Cornell PHI | Robert Edamala, CISO | specific |
| 8 | AAR Corp | Defense MRO | 151211 | UNOWNED | 5 | CMMC Nov 10 + dual mil/commercial | John Janachowski, VP IT/CISO | specific |
| 9 | VSE | Defense MRO | 41222911 | UNOWNED | 4 | CMMC Nov 10 (DoD MRO) | Daniel Bramer, Sr Dir IT/CISO | specific |
| 10 | Opendoor | RE-Tech | 90227653 | UNOWNED | 4 | SEC cyber + CCPA/CPRA + consumer PII at scale | Tc Niedzialkowski, IT Head Sec | specific |
| 11 | Shift4 | Payments | 206487998 | NET NEW | 4 | PCI 4.0.1 (meta-play, processor + customer) | Matthew Herbert, VP IT | passive |
| 12 | Domino's | QSR Franchise | 36739880 | Brad 1-contact | 4 | PCI 4.0.1 multi-location franchise | Andrew Albrecht, VP CISO | specific |

**Brad-owned-but-stale accounts deferred** (DM Brad before touching): Snowflake, Veeva, Verisk, MSCI, DocuSign, Robinhood, Affirm, Anduril, Triumph Group, StandardAero, FlightSafety, FanDuel, Churchill Downs, IGT, Choice Hotels, Jack in the Box, Simon, Digital Realty, BXP, MSU, Purdue. Most have 0-3 contacts and no recent activity. Worth a Brad ping on Anduril (hot defense), Snowflake, Digital Realty (12 contacts = he has actually worked it).

## Secondary contacts (multi-thread bench, 6 added)

| Account | Secondary | Title | Email |
|---|---|---|---|
| KRATOS | David Gambla | Division VP Security Space, Training & Cyber | david.gambla@kratosdefense.com |
| Sierra Nevada | Robert Palmer | Sr Director Systems Security | rob.palmer@sncorp.com |
| Cornell | Kevin Baradet | Exec Director Infrastructure & IT Security Officer | kb15@cornell.edu |
| AAR | Mark deRu | VP IT Integration & Data Mgmt | mark.deru@aarcorp.com |
| Domino's | Scott Urbach | VP Corporate Security, Safety & Loss Prevention | scott.urbach@dominos.com |
| Shift4 | (Ilya Dubinsky dropped — Israel-based per Sivan exclusion guidance) | — | — |

## Companies ruled out this hunt

- **Flexport** (transportation-SaaS) — no CISO surfaced in ZoomInfo, only Director of Data Analytics. Skip until a security leader appears.
- **Anduril** — Brad-owned 2 contacts. Hot account, worth DMing Brad about.
- **Snowflake / Datadog / Splunk / Palantir / F5 / Okta / Zscaler** — security-adjacent or already in Brad book.
- **Pinterest, Roku, X, Match Group, Faire, Roblox** — consumer products, off-ICP.

## Draft queue

See `2026-04-24-draft-queue.md` for the 12 cold drafts ready for Gmail paste.

## What to verify before Miles approves

1. **Gmail reauth needed.** Token expired this session. Re-auth in Claude.ai connectors panel; then ask me to push the 12 drafts via `create_draft` (one-shot).
2. **Donald Dawson (Prologis)** — confirmed new-CISO 2026-02-01 via positionStartDate. Single peer-call CTA goes here. Use Sivan reservation cap.
3. **Brad-owned dedupe DM** — recommended Slack to Brad before touching Snowflake / Anduril / Digital Realty even though he has barely worked them. Per "Brad doesn't care" SMBC precedent, he often clears on request.
4. **HubSpot writes** — none made yet. Recommend creating the 8 net-new company records + 18 contacts AFTER Miles approves the targeting list, not before.

## Cost / credits used

- ZoomInfo: 4 company-search calls, 4 enrich-companies calls (~30 companies enriched, ~30 credits), 13 contact-search calls, 18 enrich-contacts calls (~18 credits). Total ~50 ZI credits.
- HubSpot: 2 search calls, 0 writes.
- Gmail: 0 (token expired).

## Cross-references

- [[../icp.md]] — fit rubric source
- [[2026-04-22-vertical-expansion-ranking.md]] — vertical priority source
- [[2026-04-22-regulatory-tailwind-scan.md]] — regulatory hook source
- [[../../40_Plays/sivan-peer-intro.md]] — peer-call play (Donald Dawson run added)
- [[../../40_Plays/cta-ladder.md]] — tier choice rule
- [[../product/winning-openers.md]] — Register-A pattern source
- [[../product/forbidden-words.md]] — voice gate
