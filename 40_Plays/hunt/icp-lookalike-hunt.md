---
type: play
subtype: hunt
trigger: Mondays 09:00 ET
vertical: all
created: 2026-04-21
tags: [play]
---

# ICP Lookalike Hunt

Every Monday, refresh the net-new pipeline using the closed-won corpus as the seed.

## When to run
Mondays at 09:00 ET. Feeds the week's top-of-funnel.

## Algorithm

1. Load the closed-won corpus from `50_Intel/playbook/closed-won-patterns.md`:
   - Healthcare wins: Centra Health, WellStar, Premera, Christiana Care
   - Critical infra wins: Port Authority NY/NJ, Summit Utilities, OCTA
   - Identity-adjacent SaaS: Radiant Logic
   - InsurTech: CCC Intelligent Solutions

2. For each seed company, use ZoomInfo to find similar companies:
   - `find_similar_companies(companyId: <seed_id>)` if MCP supports it
   - Fallback: query by same NAICS/industry code + same employee range + same revenue range

3. Aggregate the lookalike pool. Dedupe against HubSpot + vault.

4. For each surviving company:
   - Identify the right persona (CISO/VP Sec) via `search_contacts` with `positionStartDateMin` = 365 days ago (prefer new-in-role)
   - Score fit per `50_Intel/icp.md`
   - Drop anything < 3

5. Rank by fit × (trigger event presence) × (employee count fit).

6. Output: top 10-15 staged to `50_Intel/hunt-queue/YYYY-WW-lookalike.md`

7. Post the staged list to `#miles-ai-ops` with summary.

## Max volume
Stage up to 15/week. Process through daily trigger-event hunt for drafting.

## Don't confuse lookalike with identical
A lookalike might be same industry + size but different geography, different regulatory posture, different maturity. Log those differences in the account note so personalization is accurate.

## Success criteria
Of staged lookalikes, ≥30% should get to a first meeting within 60 days. Below that threshold the lookalike filter needs tightening.

## Runs
Every draft this play creates must append a row to [[../../50_Intel/methodology/measurement-log]] with `play_source = icp-lookalike-hunt`.

| date | seed companies | lookalikes staged | drafts sent | replies | meetings |
|---|---|---|---|---|---|
