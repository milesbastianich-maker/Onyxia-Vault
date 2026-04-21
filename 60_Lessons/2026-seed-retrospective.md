---
type: lesson
subtype: seed-retrospective
period: inception to 2026-04-22
tags: [lesson]
created: 2026-04-22
---

# Seed Retrospective, Inception to 2026-04-22

Baseline for Friday synthesis shift to diff against. Not a real weekly review. Numbers sourced from [[../50_Intel/playbook/closed-won-patterns]], [[../50_Intel/playbook/closed-lost-patterns]], [[../50_Intel/methodology/objections]]. HubSpot pull dated 2026-04-21.

## Pipeline snapshot

- Active deals on Miles's book (per CLAUDE.md current focus): **9 live deals, $595K**. Source: [[../00_Index/CLAUDE.md]] Q2 2026 block.
- Active accounts tagged in `10_Accounts/`: 15 files (AKUVO, Cherry Bekaert, ECI, First Horizon Bank, FMOL Health, GenomOncology, Homestead Smart, JRM Construction, Medusind, Metalex Manufacturing, Mitsubishi Heavy, OCC, People Inc, RGA Reinsurance, Starboard Group).
- Historical wins, all reps, all time: **23 closed-won** ($1.77M direct + 3 partner-pipeline). Source: [[../50_Intel/playbook/closed-won-patterns]].
- Historical losses: **113 closed-lost**, ~$7.3M lost pipeline 2023-2026. Source: [[../50_Intel/playbook/closed-lost-patterns]].
- Historical churn: 5 accounts at stage 1012208479 (Brookfield Properties, YAGEO, Belk, Pipl, Monotype). Source: [[../50_Intel/playbook/closed-won-patterns]].
- Avg won deal: **$88K**. Median: **$60K**. Source: [[../50_Intel/playbook/closed-won-patterns]].

## Top winning plays (by closed-won deal count)

Plays are not tagged per-deal in the corpus, so ranking is inferred from source attribution and cycle length in [[../50_Intel/playbook/closed-won-patterns]].

1. **Peer-intro / founder-led (Sivan)** — collapses cycles to 36-72 days. Radiant Logic (36d), OCTA (71d), Vista (72d). See [[../40_Plays/sivan-peer-intro]].
2. **OFFLINE outbound + network + events** — 17 of 20 direct wins. Source: [[../50_Intel/playbook/closed-won-patterns]] source attribution section.
3. **Inbound (direct traffic)** — 1 of 20 wins but biggest single deal (Centra $270K). Rare but converts large.
4. **Social / LinkedIn** — 1 win (Port Authority $135K).
5. **Organic search** — 0 direct wins. All organic-sourced deals landed in losses.

Action for Friday: track play attribution per new deal. The corpus cannot tell us play ROI by count because plays were not tagged retroactively.

## Top winning verticals (by deal count and $)

Verbatim from [[../50_Intel/playbook/closed-won-patterns]] ranking:

1. **Healthcare** — 4 direct wins: Centra, WellStar, Premera, Christiana. Total **$672K**. The #1 winning vertical. See [[../50_Intel/verticals/healthcare]].
2. **Identity / SaaS vendors** — Radiant Logic $165K. Single win but clean ICP match.
3. **Critical infrastructure / transit** — Port Authority + Summit Utilities + OCTA = **$275K**.
4. **Insurance / InsurTech** — CCC $120K, Bausch + Lomb $58K.
5. **Legal / BigLaw** — Simpson Thacher $60K. One data point, 577-day cycle, peer-intro driven.
6. **Travel / Hospitality** — CWT $100K. 585-day cycle.
7. **PE + Real Estate** — Vista, Gaia, Silverstein, Brookfield (churned). Small deals.

Financial services (Miles's stated priority per CLAUDE.md) has zero won deals in the direct-pipeline corpus. First Horizon Bank, RGA Reinsurance, OCC are the active attempts. See [[../50_Intel/verticals/financial-services]].

## Top losing patterns (by frequency in closed-lost)

Verbatim from [[../50_Intel/playbook/closed-lost-patterns]]:

1. **Non-responsive** (~60% of losses). Silence, not competitors. Single-threaded deals drift.
2. **Time frame** (~15%). Decodes to "no economic buyer found, no forcing function."
3. **Budget constraints** (~10%). Also decodes to "no EB found."
4. **Missing integration / feature** (~8%). Real product-fit gap.
5. **Job change** (~3%). Champion left mid-cycle. Fragile single-thread.
6. **Service not of value** (~2%). Veterans United, Keurig Dr Pepper. Decode unknown.
7. **Chose competing service** (~1%, only 1 of 113). Allied World.
8. **In-house method** (~1%). Amdocs.

Structural pattern: **60% of all losses had one contact**. See [[../50_Intel/playbook/closed-lost-patterns]] 1-contact death trap section.

## Top objections (by frequency)

Source: [[../50_Intel/methodology/objections]]. Ranked 1-10 in that file, not by count (count data not captured yet). Frequency ranking is editorial by Miles based on replies to date, not data-driven.

1. "We already have [SIEM / EDR / DLP / GRC tool]." Most common misunderstanding.
2. "Not a priority right now / time frame isn't right."
3. "We don't have budget."
4. "Send me pricing first."
5. "I don't have time for another demo."
6. "We are building this in-house."
7. "We already bought a competitor."
8. "Security teams don't need another dashboard."
9. "Need to run this by board / CFO / legal."
10. Silence. 60% of closed-lost.

Open slots on the watchlist: sovereignty / data residency, FedRAMP, integration gaps (specifics), service-not-of-value decode, deployment complexity verbatim, data exposure concerns. See [[../50_Intel/methodology/objections]] Vault-silent slots section.

## Baseline MEDDPICC coverage

Data cannot be queried at this cutover because account notes use freeform MEDDPICC prose rather than structured frontmatter fields. Dataview query in [[../90_Templates/tpl-weekly.md]] checks `economic_buyer`, `champion`, `paper_process`, `metrics` slots. If those frontmatter keys aren't populated in `10_Accounts/` files, the Friday synthesis will report all 15 active accounts as MEDDPICC gaps.

**Action item for first Friday synthesis:** enforce MEDDPICC frontmatter keys on all 15 active accounts or change the weekly template query. Pick one.

Baseline count for diff purposes (pending fill): **complete: unknown, partial: unknown, empty: unknown.** First Friday run establishes the true baseline.

Rule from [[../50_Intel/playbook/closed-lost-patterns]]: no proposal ships without a named Economic Buyer.

## Open questions for next synthesis

What the first Friday run should diff against:

- **Draft approval rate.** Approvals vs rejections in `#miles-ai-ops` reactions. Captured daily in `60_Lessons/rejections/`. No baseline yet.
- **Reply rate on Miles's outbound.** Per reply-intent-parser runs. No baseline yet.
- **Meeting book rate.** Active accounts to booked first-meeting. No baseline yet.
- **Play conversion.** Which play attribution moves a deal a stage. Requires per-draft play tag first.
- **Multi-thread rate on active deals.** Target is 2 contacts within 30 days of first meeting. Current rate unknown.
- **Single-thread risk queue.** Count of active deals at 1 contact >30 days. Tag per [[../50_Intel/playbook/closed-lost-patterns]] closing action list item 4.
- **Time-in-stage per active deal.** If a deal sits >30 days without stage progression, it matches the silent-death pattern.
- **Named EB coverage.** Count of active deals with Economic Buyer slot filled.
- **Nurture bucket entries.** "Time frame" losses parked for trigger-event re-approach. See [[../50_Intel/playbook/closed-lost-patterns]] mitigation.
- **Competitor mentions in deal notes.** Expected count near zero. If it rises meaningfully, [[../50_Intel/playbook/closed-lost-patterns]] premise needs revisiting. Competitor coverage now lives in [[../50_Intel/competitors/README]] (seeded 2026-04-22).

## Cross-references

- [[../50_Intel/playbook/closed-won-patterns]]
- [[../50_Intel/playbook/closed-lost-patterns]]
- [[../50_Intel/methodology/objections]]
- [[../50_Intel/product/positioning]]
- [[../50_Intel/product/quotes]]
- [[../00_Index/CLAUDE.md]]
