---
type: intel
subtype: methodology
topic: touch tracker
created: 2026-04-22
updated: 2026-04-22
source: Gmail thread audit 2026-04-22 + session send log
tags: [intel, methodology, tracker]
---

# Touch Tracker

Single source of truth for every outbound touch and its follow-up cadence. Sort by `next_touch_date` ASC. Updated by EOD shift + weekly-pipeline-review skill + manual edits.

**Auto-update runbook (not yet live — pending Miles ✅ to flip on):**
- Daily EOD: scan Gmail for replies on `reply_state=pending` rows older than 24h. Update `reply_state` + `reply_intent` via `40_Plays/reply-intent-parser.md`.
- Silent 5d + no bounce → flip `next_touch_plan` to Day-5 bump per vertical sequence.
- Silent 12d → flip to Day-12 breakup.
- Silent 30d → `reply_state=silent_30d`, archive from active queue.
- Bounces on send: immediate `reply_state=bounced`, exclude from future touches.

---

## 🔴 PRIORITY — action needed in next 48h

| account | contact | touch# | last_touch | next_touch_date | next_touch_plan | owner | notes |
|---|---|---|---|---|---|---|---|
| [[../../10_Accounts/Mitsubishi Heavy]] | Lucas Parker, Head of Security MHIA | replied | 2026-04-20 | **2026-04-23** | **BLOCKER: Miles reviews Lucas's MNDA (sent 2026-04-14). Lucas bumped 2026-04-20 asking for review.** | Miles | $75K deal, waiting on Onyxia side 8 days. Reply even with ETA. |
| IVISA / Susan Lloyd | susan.lloyd@ivisa.com | reply-confirmed | 2026-04-20 | **2026-04-27 2pm CT** | Meeting booked. Prep needed: address her "tooling = if absolutely needed" soft objection. | Miles | Pappas dinner follow-up. Meeting confirmed at 2pm CT. |
| Rocket / Mike Madero | mikemadero@rocket.com | reply-friendly | 2026-04-21 | **2026-04-24** | Soft follow-up asking if he's back in office yet. | Miles | Pappas. Replied warm, said will find time back in office. |

## 🆕 CI + DIB hunt 2026-04-22 PM (drafts pending in Gmail)

Staged via second hunt of the day. Drafts being created by hardened `onyxia-drafter` sub-agent with all 9 gates (Level 3+ personalization, avoid-ai-writing ≥4, 8-criteria rubric ≥4, em-dash zero, Register-B grep zero, source-citation HTML comment mandatory). Touch-tracker rows will be updated with Gmail draft IDs when the sub-agent reports.

**Status: 8 of 9 drafts STAGED in Gmail drafts folder. Scored 8/8 on the 8-criteria rubric across all 8. Zero em dashes, zero Register-B, zero banned phrases. Awaiting Miles ✅ to send.**

| Subject | Contact | Gmail Draft ID | Score | Trigger |
|---|---|---|---|---|
| `first 30 days at FirstEnergy` | [[../../20_Contacts/Brian Harrell]] CSO | `19db62017cf175a2` | 8/8 | new-CSO 2026-03-23 (30d), ex-CISA, ex-Avangrid |
| `reporting line reshuffle` | [[../../20_Contacts/M. Scott Hipkins]] VP & CISO | `19db6202ee02cbb9` | 8/8 | 22-yr tenure + new-CSO-above-him |
| `NERC-CIP evidence in the new org` | [[../../20_Contacts/Jason McCormick]] Gov Dir Cyber | `19db62049952796a` | 8/8 | 15-mo governance seat + Brian's first 90d |
| `20 years of SJI systems` | [[../../20_Contacts/Patrick Finnegan]] VP IS | `19db62060219d46a` | 8/8 | 20-yr tenure + new-CIO Bhupesh transition |
| `Bhupesh's 90-day list` | [[../../20_Contacts/Sarah Brooks]] Dir Office of CIO | `19db62074b2e5bc8` | 8/8 | direct-report to new CIO + TSA Pipeline May renewal |
| `stack under TSA Pipeline` | [[../../20_Contacts/Michael Bizzoco]] Service Delivery VP IT | `19db620892726ef7` | 8/8 | TSA Pipeline SD 2021-02F May renewal |
| `CMMC 7 months out` | [[../../20_Contacts/Jan Mast]] Global Dir Cybersecurity | `19db6209f7e4c5dc` | 8/8 | CMMC Nov 10 (203 days) + UAS/DFARS CUI |
| `infra signal into Jan's program` | [[../../20_Contacts/Scott Tasem]] Sr Dir IT Infra | `19db620aa8b0a9d4` | 8/8 | CMMC infra-side + Jan Mast named peer |
| *(pending)* | [[../../20_Contacts/Aniket Majumder]] CIO | — | — | email enrichment blocked (data lag on Dec 2025 promotion) |

**Bonus draft spotted in Gmail drafts folder** (auto-drafted by another agent earlier):
- `RE: Onyxia <> MHIA: Follow up & Next steps` → Lucas Parker / MHIA. ID `19db611c49437b3c`. Contains `[MILES: insert status — redlines coming / clean / sent to legal — and target date before sending.]` placeholder. **Miles must fill the placeholder before sending.**

## 🟡 PRIORITY — next 7 days

| account | contact | touch# | last_touch | next_touch_date | next_touch_plan | owner | notes |
|---|---|---|---|---|---|---|---|
| Ada / Steph Afamefuna | steph.afamefuna@ada.support | 1 | 2026-04-21 | 2026-04-25 | Bump if silent — new angle on DevSecOps tool sprawl. Sivan cc'd. | Miles | Pappas follow-up. Sivan replied same-day. Awaiting Steph. |
| HP / Dorai Babu | dorai.babu@hp.com | 1 | 2026-04-21 | 2026-04-25 | Bump if silent — reference the Info Sec Executive seat specificity. Sivan cc'd. | Miles | Pappas follow-up. |
| [[../../10_Accounts/People Inc]] | Christina Jonsson | reply-paused | 2026-04-20 | 2026-05-04 | Wait per her "bandwidth-constrained" signal. Light touch at 14 days with a new angle, not a bump. | Miles | $150K biggest in pipeline. She said "waiting to hear back from her side." |
| [[../../10_Accounts/Nordson]] | [[../../20_Contacts/Adam Petrelle]] | 1 | 2026-04-22 | 2026-04-27 | Day-5 bump if silent. Angle: NDSN Q1 earnings (if filed) + control-drift framing. | Miles | Mfg hunt send. Draft score 4/5. |
| [[../../10_Accounts/Mustang Cat]] | [[../../20_Contacts/Lance Feldhousen]] | 1 | 2026-04-22 | 2026-04-27 | Day-5 bump if silent. Angle: specific CAT dealer network signal. | Miles | Mfg hunt. Draft score 4/5. Glenn Haddock email still unresolved. |
| [[../../10_Accounts/Milacron]] | [[../../20_Contacts/Jeffrey Mowry]] | 1 | 2026-04-22 | 2026-04-27 | Day-5 bump if silent. Angle: second-VP-IT restructure signal follow-through. | Miles | Mfg hunt. Draft score 4/5. |
| [[../../10_Accounts/Biomerics]] | [[../../20_Contacts/Jesse Moore]] | 1 | 2026-04-22 | 2026-04-27 | Day-5 bump if silent. Angle: FDA QSR + ISO 13485 specific evidence challenge. | Miles | Mfg hunt. Draft score 3.5/5 (em dash violation shipped). |
| [[../../10_Accounts/Graco]] | [[../../20_Contacts/Kathryn Schoenrock]] | 1 | 2026-04-22 | 2026-04-27 | Day-5 bump if silent. Angle: year-3 CIO re-evaluation specific decision. | Miles | Mfg hunt. Draft score 3/5 (lowest, two em dashes + hedges). Highest risk of silent-death. |
| [[../../10_Accounts/Klein Tools]] | [[../../20_Contacts/Bryan McGraw]] | 1 | 2026-04-22 | 2026-04-27 | Day-5 bump if silent. Angle: principal-close decision model specific reporting demand. | Miles | Mfg hunt. Draft score 4/5. |

## 🟢 Register-A cold cohort — touch 1 awaiting reply (15 sends)

All healthcare + fins + defense + med-device. Draft score average ~4/5. Personalization Level 4 (individual-specific) across the board. Expected reply rate 3-8% per industry benchmark. Day-5 bumps trigger 2026-04-26 through 2026-04-28 if silent.

| account | contact | send_date | subject | ai_score | reply_state | next_touch_date |
|---|---|---|---|---|---|---|
| [[../../10_Accounts/Medusind]] | Megan Marshall | 2026-04-21 | after the settlement | 4 | pending | 2026-04-26 |
| [[../../10_Accounts/First Horizon Bank]] | Leilani Farol | 2026-04-21 | the first 90 days at First Horizon | 5 | pending | 2026-04-26 |
| [[../../10_Accounts/OCC]] | Jessica Kruse | 2026-04-21 | GRC at OCC with clearing member cyber obligations | 4 | pending | 2026-04-26 |
| [[../../10_Accounts/Metalex Manufacturing]] | Hunter Jackson | 2026-04-21 | CMMC + aerospace manufacturing security | 4 | pending | 2026-04-26 |
| [[../../10_Accounts/RGA Reinsurance]] | Gabriella Kirkpatrick | 2026-04-21 | compliance across 70 countries at RGA | 4 | pending | 2026-04-26 |
| [[../../10_Accounts/FMOL Health]] | Britani Tullier | 2026-04-21 | HIPAA reporting across a growing system | 4 | pending | 2026-04-26 |
| [[../../10_Accounts/GenomOncology]] | Justin Yeakley | 2026-04-21 | securing genomic data at scale | 4 | pending | 2026-04-26 |
| Cross Country Healthcare | Marlon Clarke | 2026-04-22 | Chris Tyrell's first 90 days | 5 | pending | 2026-04-27 |
| MedStar | Andrew Puller | 2026-04-22 | 160 hours a month | 5 | pending | 2026-04-27 |
| MedStar | William Pallozzi | 2026-04-22 | separate note on MedStar's board reporting | 4 | pending | 2026-04-27 |
| Main Line Health | Aaron Weismann | 2026-04-22 | board reporting at Main Line | 4 | pending | 2026-04-27 |
| Luminis Health | Jason Taule | 2026-04-22 | Luminis scale and the reporting stack | 4 | pending | 2026-04-27 |
| Cone Health | Robert Patto | 2026-04-22 | Cone and the 13K match | 4 | pending | 2026-04-27 |
| Advocate Health | Daniel | 2026-04-22 | Advocate's 50K-employee reporting math | 4 | pending | 2026-04-27 |
| WellSpan | John Sherouse | 2026-04-22 | WellSpan's reporting stack | 4 | pending | 2026-04-27 |
| Virginia Mason Franciscan | Ron Yeager | 2026-04-22 | VMFH CISO seat | 4 | pending | 2026-04-27 |

## 🚫 Register-B cohort — FLAGGED DO-NOT-BUMP (≥100 sends)

All sent 2026-04-21 UTC ~17:18-17:33 (Tuesday PM ET). Miles flagged "awful, all the same, not personalized" on 2026-04-22. Register-B mail-merge pattern: identical body across all recipients with only [First] and [Company] swapped. Personalization Level 2 (role-aware generic) — below the Level 3 minimum gate now enforced in `onyxia-drafter.md`.

**Policy per Miles 2026-04-22:** `next_touch_plan = do-not-bump-unless-trigger`. Do not send Day-5 bumps. Do not send Day-12 breakups. Only re-engage if a genuine new trigger lands (exec hire, breach, 8-K, settlement, funding round, deadline). Treat as cold-outreach burnt until trigger-signal surfaces.

### Bounces (3 confirmed, exclude from future re-touch permanently)
- Symphony / Mitchell Hibbs — `mitchell.hibbs@symphony.com` — permanent fatal error, address not found
- Papaya Global / Aaron Slutsky — `aaron.slutsky@papayaglobal.com` — address not found
- Mutual of America / Mary McCarren — `m.mccarren@mutualofamerica.com` — permanent fatal error

### Sample sends (9 hook variants × ~10-15 each)

Full Gmail query to re-pull: `from:me newer_than:2d (subject:"a map for the security stack" OR subject:"CPM for" OR subject:"stack sprawl" OR subject:"audit-season prep" OR subject:"board deck on autopilot" OR subject:"proving the security program" OR subject:"visibility across" OR subject:"tool stack dilemma" OR subject:"CPM built for" OR subject:"quick look at Onyxia")`.

Known recipients (non-exhaustive, extend by Gmail re-pull):
- "a map for the security stack": Warner Music, DigitalOcean, Cyera, Spring Health, URBAN ONE, Grafana Labs, Savills, Compass, Circle, IAC, Medidata, Arcesium (x2), ValueMomentum
- "CPM for [Company]": Jefferies, Daybright Financial, Blue Owl Capital, Interactive Brokers, Dime Community Bank, Flagstar Bank, Cross River Bank, Equitable, Bessemer Trust, CIT Bank, Lazard, Two Sigma (x2), Transamerica, Galaxy, Sohar International
- "stack sprawl @ [Company]?": Datadog, Symphony (BOUNCE), Ro, Optimizely, Papaya Global (BOUNCE), The Motley Fool, Exiger, Questel
- "audit-season prep made boring": Oliver Wyman, Savills, Zillion Technologies, Progyny, Epiq (x3 — John Orleans, David Evans, Joe Whittingham), MedMetrix, University Hospital, UnitedLex, Execo
- "your board deck on autopilot?": DTCC, General Atlantic, AmTrust Financial, Provident Bank, Open Society Institute, Mutual of America (BOUNCE), Great American Insurance, Brown Brothers Harriman, TPG, Nasdaq, MSCI, RenaissanceRe, Jefferies (Wyatt Felger)
- "proving the security program at [Company]": SUNY Downstate, Valley Health System, ISS (x2 — Josh Lukens, Kevin O'Leary), Kroll, AlixPartners, SitusAMC, SSA (dubious — SSA is government, may not be ICP), Children's Place
- "visibility across the [Company] stack": Parx Casino, Sotheby's, NHL, MLB, AriZona Beverages, Breakthru Beverage, BMW Motorcycles, Children's Place (x2 — Bruce Carpenter)
- "the [Company] tool stack dilemma": Olo, Scholastic, Minute Media, Braze, iCIMS, ROKT, BlackBerry, McGraw Hill, IAC (x2)
- "CPM built for [CISOs/CSOs/VPs/security leaders]": Epiq (Alyssa Miller, Jason Burzenski), IMP (Daniel D'Amico), Kroll (x2 — Brett Davido, Jeffrey Evans, Jacob Elle), Debevoise, AlixPartners (Shawn Jezierski, Jeremy Domonkos), Kravet
- "quick look at Onyxia": NFL / Tomás Maldonado, BNED / Richard Davidson, J.Crew / Frank Parato

## Live deals in flight (not from current-session cold cohort)

| account | contact | stage | last action | next action |
|---|---|---|---|---|
| [[../../10_Accounts/Mitsubishi Heavy]] | Lucas Parker | MNDA review | Lucas sent MNDA 2026-04-14, bumped 2026-04-20 | **Miles reviews MNDA — BLOCKER** |
| IVISA | Susan Lloyd | meeting booked | booked 2pm CT Mon 2026-04-27 | Prep for soft-tooling-objection |
| Rocket | Mike Madero | warm-reply | Mike said "find time back in office" 2026-04-21 | Soft check-in 2026-04-24 |
| Ada | Steph Afamefuna | post-event | Miles + Sivan follow-up 2026-04-21 | Bump if silent 2026-04-25 |
| HP | Dorai Babu | post-event | Miles + Sivan follow-up 2026-04-21 | Bump if silent 2026-04-25 |
| [[../../10_Accounts/People Inc]] | Christina Jonsson | paused | paused 2026-04-20 per her bandwidth | Light re-engage 2026-05-04 |

---

## Schema (all fields)

```yaml
send_id: string (timestamp or UUID)
account: wikilink to 10_Accounts/{Company}.md
contact: wikilink to 20_Contacts/{First Last}.md
touch_number: 1 | 2 | 3 | breakup | reply
send_date: ISO date (YYYY-MM-DD) or datetime
subject: verbatim string
body_word_count: integer
personalization_level: 3 | 4 | 5 (below 3 must not ship)
personalization_source: URL + retrieval date
ai_writing_score: 1-5 (avoid-ai-writing skill, detect mode)
drafter_rubric_score: 1-5 (8-criteria rubric in draft-scoring.md)
ai_tells_flagged: comma list or "none"
reply_state: pending | replied | bounced | unsubscribed | silent_30d | silent_60d | reply-paused | reply-friendly | reply-confirmed
reply_intent: positive | objection | not_interested | referral | ooo | unknown | n/a
next_touch_date: ISO date | null
next_touch_plan: one-line description
meeting_booked: Y | N | null
notes: optional one-line
```

## Seeding provenance (2026-04-22)

- **Mfg cohort (6 rows):** seeded from session Gmail drafts created + sent 2026-04-22 14:23-14:24 UTC. Draft scores from `draft-scoring.md` self-audit.
- **Register-A healthcare cohort (15 rows):** seeded from Gmail sent folder query, Miles's own 2026-04-21 + 2026-04-22 outbound. Captured in `winning-openers.md` as Register-A voice anchors.
- **Register-B cohort (~100 rows):** seeded from Gmail sent 2026-04-21 17:18-17:33 UTC query. 3 bounces confirmed. Full list re-pullable via Gmail query above.
- **Live deals (6 rows):** seeded from Gmail replies inbox scan 2026-04-22. MHIA NDA blocker, IVISA booked meeting, Pappas trio warm follow-ups, People Inc paused.

## Cross-references

- [[./draft-scoring]] — 8-criteria rubric
- [[./measurement-log]] — per-play run logs (complementary; tracker is per-send)
- [[./discovery-framework]] — Convergence Discovery
- [[../product/winning-openers]] — Register-A corpus
- [[../product/forbidden-words]] — banned phrases including Register-B patterns
- [[../../.claude/agents/onyxia-drafter]] — the agent that writes + scores drafts
- [[../../40_Plays/sequences/README]] — cadence index (Day 0 / 5 / 12 / 14 / 30 / 60)
- [[../../40_Plays/reply-intent-parser]] — reply classification
