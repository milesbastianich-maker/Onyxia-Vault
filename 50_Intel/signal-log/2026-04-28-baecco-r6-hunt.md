---
type: hunt-log
hunt_pattern: vertical-saturation
date: 2026-04-28
event: Baecco Dinner NYC Round 6
tags: [intel, hunt]
---

# Hunt Log -- Baecco Dinner R6 Wide Pool 2026-04-28

## Summary

hunt_pattern: vertical-saturation (wide geo + all tiers + all verticals)
vertical: all
candidates_raw: 654 (NY C-level 254, NY VP-level 258, NY Director-level 602, NJ VP-level 40, NJ Director-level 120, CT all tiers 90)
candidates_post_exclusion: ~180 (excluded R1-R5 repeats, territory blocks, geo fails, title fails)
candidates_post_hubspot_dedupe: ~60 clean (many already in HubSpot under other owners or Miles)
candidates_scored_geq_3: 50
accounts_staged: 50 candidates appended to baecco-dinner-nyc-hunt-2026-04-27.md
contacts_enriched: 38 (hit enrichment limit)
log_file: 50_Intel/signal-log/2026-04-28-baecco-r6-hunt.md
territory_conflicts: 0 (Brad territory has healthcare/fins -- checked; Ryan Qiao at Horizon BCBS NJ is clean since prior contact was an admin assistant, not CISO)

## Methodology

1. HubSpot pull: 173 CISO-title contacts in NY/NJ/CT. Mapped ownership.
2. ZoomInfo C-level (CISO/CSO/CRO): NY 254 results, NJ 29 results, CT from combined run.
3. ZoomInfo VP-level (VP InfoSec/Security): NY 258 results, NJ 40 results.
4. ZoomInfo Director-level (Dir IS/Cyber/GRC): NY 602 results, NJ 120 results, CT 90 results.
5. Personal location filter applied (Person search type across all ZI queries).
6. Exclusion pass: dropped all 70+ prior-round names, active deals, territory blocks.
7. Geo filter pass: dropped confirmed out-of-zone (Lincoln Financial/Radnor PA, Liberty Bank/Middletown CT, UConn/Storrs CT).
8. Enrichment batch: 38 contacts enriched, 12 hit limit (email unconfirmed -- flagged for next run).
9. HubSpot dedupe: cross-checked company names for conflicts. 0 new Brad-territory conflicts.

## Unconfirmed emails (enrich on next run)

- Damon Santangelo, 1-800-Flowers (ZI 2956257422)
- Kraig Elliott, Kimco Realty (ZI 9157707284)
- Jason Schott, Valley Bank (ZI 3148288765)
- Jonathan Fox, MSC Industrial Direct (ZI 9459237279)
- Kenny Chu, Icahn School of Medicine at Mount Sinai (ZI 15302549585)
- Sayeed Gulmahamad, Lazard (ZI -1572698134)
- Donald Babcock, UConn (ZI 14772756685 -- geo uncertain, hold)
- James Zdru, Avangrid (ZI 1773301737 -- borderline geo, confirm personal address)

## Vertical distribution (Round 6 candidates)

- Financial Services / Banking / Fintech: 14 (28%)
- Healthcare / Digital Health: 6 (12%)
- Technology / Digital Media: 7 (14%)
- Manufacturing / Specialty Chemicals: 4 (8%)
- Real Estate / REIT: 2 (4%)
- Energy / Utilities: 1 (2%)
- Professional Services / Legal: 3 (6%)
- Publishing / Education: 3 (6%)
- Commodities / Trading: 1 (2%)
- Other: 9 (18%)

Finance still heavy but significantly more diversified than prior rounds due to wide-filter approach.

## Tier distribution (Round 6)

- Tier 1 (CISO/CSO/CRO/VP Sec): 24 (48%)
- Tier 2 (Deputy CISO/VP GRC/VP Cyber Risk): 5 (10%)
- Tier 3 (Director IS/Cyber/GRC/Head GRC): 17 (34%)
- Tier 4 (Senior Director IS/Cyber): 4 (8%)

## Geo distribution (Round 6)

- Manhattan / NYC: 27 (54%)
- Long Island (Nassau / LIRR): 6 (12%)
- North NJ (PATH / NJT): 10 (20%)
- Central NJ (NJT NEC): 3 (6%)
- Connecticut Coast (Metro-North): 4 (8%)
- Geo fails (dropped): 3 (Radnor PA, Middletown CT, Storrs CT)

## Key new pain signals surfaced

- Ryan Qiao at Horizon BCBS NJ (brand new CISO Jan 2026) -- best trigger in the round
- Sadiq Khan at Insight Partners (new CISO Oct 2025)
- James Zhou at Noom (new CISO Apr 2025)
- Justin Marshall at Balchem (new Dir Cyber Sep 2025)
- Daniel Peluso at The Associated Press (new Senior Dir IS Jun 2025)
- John Gambardella at NewtekOne (new CTO/CISO Feb 2025, bank charter conversion trigger)
- Flagstar Bank near-collapse + PE rescue (Gerard Varrichio pain)
- Teladoc Livongo impairment + new Deputy CISO (Maloney, Dec 2024)

## Gaps remaining after 6 rounds

- Defense/aerospace primes: zero NYC metro 500-10k CISO/VP Sec found across all rounds.
- Biotech non-pharma: Moderna covered; Regeneron (Mark Leary) is 828577255-owned.
- Legal/BigLaw: Weil covered (Billing). Sullivan & Cromwell shows Associate Director only (too junior). Cravath shows Director (Alexander Eames -- not enriched yet).
- Logistics / Supply Chain: zero in this round. Separate vertical-saturation run recommended.
