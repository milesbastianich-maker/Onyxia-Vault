---
type: intel
subtype: hunt-research
date: 2026-04-22
tags: [intel, hunt-research]
---

# Vertical-Density Analysis — Non-Covered Verticals in HubSpot

Raw HubSpot query counts as of 2026-04-22. Each row sourced from a `search_crm_objects` `total` field, not inferred.

## Company counts by non-covered industry

| HubSpot Industry Code | Company Count | Verdict |
|---|---|---|
| COMPUTER_SOFTWARE | **1,267** | Massive. Need to filter out security vendors per exclusion rules. |
| HIGHER_EDUCATION | **286** | Massive. Likely unified by IT/compliance office patterns. |
| REAL_ESTATE | **243** | Large. Silverstein + Gaia closed-won precedents. |
| RETAIL | **206** | Large. Chipotle closed-won precedent. |
| LEGAL_SERVICES | **141** | Mixed (BigLaw + municipal). Simpson Thacher precedent. |
| OIL_ENERGY | **88** | Moderate. Public filers, good for SEC cyber hook. |
| DEFENSE_SPACE | **83** | Moderate. CMMC Phase 2 tailwind. |
| GOVERNMENT_ADMINISTRATION | **83** | Moderate. DHS + cities. StateRAMP adjacency. |
| LAW_PRACTICE | 3 | Too sparse. Real BigLaw is tagged LEGAL_SERVICES in HubSpot. |
| VENTURE_CAPITAL_PRIVATE_EQUITY | 3 | Too sparse. Vista win likely tagged elsewhere. |

## Contact title-density across all industries

| jobtitle contains | Total Contacts |
|---|---|
| CISO | **2,247** |
| Security (broad) | **10,124** |

Interpretation: Miles's HubSpot holds ~100x more CISO-titled contacts than the 23 closed-won deals. The bottleneck is not address-book depth. It is coverage prioritization across industries and the territory overlap with Brad.

## First-page samples surfaced in queries (for cross-reference)

**Higher Education samples:** University of Oxford, University of Houston, Miami Dade College, The City University of New York (100K emp), State University of New York (50K), University of New Brunswick, Saint Leo, Concordia, IIT Kanpur, ENSAE Paris.

**Defense/Aerospace samples:** Qarbon Aerospace, DSCA Arms Sales, Mercury Systems, JHU Applied Physics Lab, MITRE, Woodward, Astrion, Ducommun, General Dynamics (117K), King Aerospace.

**Retail samples:** Cart, Mohawk Industries, SmartCentres, El Corte Inglés, MSX International, TFG Limited, American Woodmark, Circle K (QSR).

**Real Estate samples:** Howard Hanna, Douglas Elliman, Sun Communities, Brookfield Properties (existing win, now "Churned" per playbook), KBS, L&Q Group, Heimstaden Bostad, REA Group, OSC Canada, Ontario Securities Commission.

**Legal Services samples:** Stephenson Harwood, Smith Gambrell Russell (BigLaw), City of Lakewood + Elk Grove PD + Luxembourg Government (municipal mis-tagged), Gouvernement luxembourgeois.

**Oil/Energy samples:** Ovintiv, Kinder Morgan (10.9K), Transocean (6.6K), ECC, Nextpower.

**Computer Software samples:** Argano, LTS, MetTel, BEIT, Business Technology Partners (mostly smaller system-integrator-type firms in first page, need employee-count filter to surface real SaaS enterprise targets).

## CISO contacts surfaced in first-page sweep

Illustrative examples of depth (non-covered industries):
- Michael Marszalek, Global CISO, Tower Research Capital (quant trading / fins — covered but interesting)
- Nimit Suri, VP CISO, WeightWatchers (retail / health / consumer)
- Sadiq Khan, VP Head of Security & CISO, Insight Partners (PE/VC)
- Bara Hur, US CISO Strategy, RBC Capital Markets (fins — covered)
- Matthew Chung, Partner / Global CISO, Goldman Sachs (fins — covered)
- Ryan Weeks, CISO, Vimeo (media/SaaS)
- Tom Daniels, CISO, Cursor (AI/SaaS)
- Sabeena Lalwani, CISO, Magnite (ad-tech)
- Henry Jiang, CISO, Ensora Health (healthcare — covered)
- Denis Andreyev, CIO+CSO, Focus Partners (financial services)

## Key finding

Non-covered verticals where Miles has HubSpot presence AND closed-won precedent (2+ wins in corpus):
- **Real Estate** (243 companies + 2 wins: Gaia, Silverstein)
- **Retail + Hospitality** (206 companies + multiple wins: Chipotle, CWT, Starboard Group pipeline)
- **Legal Services (BigLaw slice)** (141 companies + Simpson Thacher win)

Non-covered with HubSpot presence but singleton or no wins:
- **Higher Education** (286 companies, 0 wins — untouched market)
- **Computer Software / SaaS** (1,267 companies, 1 win — Radiant Logic, excluding security vendors)
- **Defense/Aerospace** (83 companies, 0 wins, CMMC tailwind)

## Phase 1 budget used

6 company-industry queries + 2 contact-title queries = 8 of 15 tool call cap. 7 calls preserved for contingency.
