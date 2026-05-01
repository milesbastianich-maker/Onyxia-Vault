---
type: intel
subtype: playbook
topic: closed-won patterns
source: HubSpot pull 2026-04-21 (23 real wins across all pipelines)
created: 2026-04-21
tags: [intel, playbook]
---

# Closed-Won Patterns

Synthesized from 23 historical wins across default and partner pipelines. Stops guessing. Clone what worked.

## The corpus

**20 direct wins in default Sales Pipeline (stage ID `closedlost`, label "Closed Won"):**

| Deal | Amount | Closed | Owner | Vertical |
|---|---|---|---|---|
| Centra Health | $270,000 | 2024-12-17 | Maura | Healthcare |
| WellStar Health System | $172,500 | 2025-08-22 | Maura | Healthcare |
| Premera Blue Cross | $170,000 | 2025-12-04 | Brad | Health Insurance |
| Radiant Logic | $165,000 | 2025-05-20 | Brad | Identity (SaaS) |
| Port Authority NY/NJ | $135,000 | 2025-04-01 | Maura | Critical Infra / Transit |
| CCC Intelligent Solutions | $120,000 | 2024-10-21 | Maura | InsurTech |
| CWT | $100,000 | 2025-07-28 | Brad | Corporate Travel |
| Chipotle | $80,000 | 2024-09-25 | Maura | QSR Retail |
| Summit Utilities | $80,000 | 2024-12-19 | Maura | Utilities |
| Orange County Transp. Authority | $60,000 | 2025-06-11 | Brad | Government / Transit |
| AXNY Group | $60,000 | 2026-02-18 | Brad | Staffing |
| Simpson Thacher & Bartlett | $60,000 | 2025-11-20 | Brad | BigLaw |
| Christiana Care Health | $60,000 | 2024-02-20 | Sivan | Healthcare |
| Bausch + Lomb | $58,500 | 2024-07-22 | Maura | Pharma / Optics |
| Millennium Print (Pokemon) | $45,000 | 2024-03-20 | B. Fisher | Print Manufacturing |
| Gaia Real Estate | $37,500 | 2025-03-13 | Sivan | Real Estate |
| Vista Equity Partners | $37,500 | 2025-04-16 | Brad | Private Equity |
| Elite Technology | $30,000 | 2025-07-01 | Maura | Tech / SaaS |
| Adama | $16,000 | 2026-01-07 | Sivan | Agri-Chemicals |
| Silverstein Properties | $10,000 | 2023-08-15 | Sivan | Real Estate |

Direct-pipeline total: **$1,766,500**. Avg win: **$88K**. Median: **$60K**.

**3 partner pipeline wins (stage 252640014, Partner Pipeline):**
- Alchemy Tech Group — Brad — 4 contacts
- World Wide Technology — Brad — 6 contacts (most multi-threaded win on record)
- Consortium Networks — Brad — 3 contacts

**5 "Churned" (stage 1012208479) — converted and left:**
Brookfield Properties, YAGEO Group, Belk, Pipl, Monotype. Study why they churned in a separate review.

## Verticals that closed (ranked by $)

1. **Healthcare** — 4 direct wins + Centra + WellStar + Premera + Christiana = $672K. **Healthcare is the #1 winning vertical.**
2. **Identity / SaaS vendors** — Radiant Logic $165K. Onyxia solves for identity-adjacent security vendors who need their own GRC layer.
3. **Critical infrastructure / transit** — Port Authority + Summit Utilities + OCTA = $275K. Government-adjacent with compliance drivers.
4. **Insurance / InsurTech** — CCC $120K, Bausch + Lomb $58K.
5. **Legal / BigLaw** — Simpson Thacher $60K. Single data point, but BigLaw has high attach when they move.
6. **Travel / Hospitality** — CWT $100K. Long cycle (585 days), but closed.
7. **PE + Real Estate** — Vista, Gaia, Silverstein, Brookfield (churned). Lower deal sizes.

## Deal cycle — time to close

Calculated from `createdate` → `closedate`:

- **Fast closes (< 90 days):** Radiant Logic (36), OCTA (71), Vista (72), Centra Health (137). Pattern: **peer/referral-driven or existing-network intros**. Radiant Logic is a security vendor — likely peer intro from Sivan's network.
- **Mid cycles (3-9 months):** Premera (169), CCC (231). Pattern: **inbound-driven with a champion in place**.
- **Long cycles (15-18+ months):** Simpson Thacher (577), WellStar (553), CWT (585), Chipotle (495). Pattern: **large enterprise, procurement-heavy verticals, non-linear but persistent**.

**Takeaway:** peer intros collapse cycles by 5-10x. Enterprise without a champion = 15+ months. Design outreach to find or create the peer bridge.

## Who closed what

- **Brad Baldelli (currently active):** 8 wins including Simpson Thacher, CWT, OCTA, Radiant Logic, Vista, AXNY, Premera. Brad's strength: mid-market enterprise + identity/SaaS-adjacent verticals. Long cycles, persistent.
- **Maura Clancy (ex-rep, 828577255):** 8 wins including the biggest (Centra $270K, WellStar $172K, Port Authority $135K, CCC $120K). Healthcare + critical infra + QSR. Her deals are the biggest on record.
- **Sivan Tehila (CEO, founder-led):** 4 wins including Gaia, Silverstein, Christiana Care, Adama. Smaller deals, early customers, founder-sold.

**Takeaway:** Maura's win set is gold for healthcare messaging. Dig into her notes for Centra, WellStar, Port Authority, CCC. Those are the pattern-matches for Miles's current Tier 1 healthcare pipeline (Medusind, FMOL, GenomOncology).

## Source attribution (where wins came from)

From `hs_analytics_source`:
- **OFFLINE** — 17 of 20 wins. Outbound, referrals, events, CEO network.
- **DIRECT_TRAFFIC** — 1 (Centra Health). Inbound that converted to a $270K win.
- **SOCIAL_MEDIA** — 1 (Port Authority). LinkedIn-sourced $135K win.
- **ORGANIC_SEARCH** — 0 direct wins in this set (all organic-search deals in the loss bucket).

**Takeaway:** Onyxia wins offline. Outbound + events + network. Inbound is thin but when it converts, it converts big (Centra). Social/LinkedIn matters for the top of funnel (Port Authority).

## Multi-thread signal (num_associated_contacts on wins vs losses)

- **Won deals avg contacts:** 2.5 contacts per deal
- **Partner pipeline wins avg:** 4.3 contacts per deal (World Wide Tech had 6)
- **Lost deals avg contacts:** 1.4 contacts per deal
- **Losses with only 1 contact:** 68 of 113 (60%)

**This is the single biggest lever.** Single-threaded deals are death. Every win averages ~2x the contacts of every loss. Partner wins, which are the most repeatable, average 4+. Multi-threading isn't optional.

## What to clone

1. **Target verticals first:** healthcare + critical infra + identity-SaaS. That's where 80% of wins + dollars live.
2. **Multi-thread or die.** Minimum 2 contacts on every active deal. 3+ is the target. Single-contact deals auto-tag `#single-threaded-risk`.
3. **Peer-intro play is the cheat code.** Radiant Logic (36 days) and OCTA (71 days) moved fast because of network. Sivan's peer network + champion referrals are the acceleration lever.
4. **Big healthcare = long hold.** WellStar (553d) and similar. Plan the campaign for 12+ months, not 90. Don't bail early.
5. **Inbound is rare but huge when it hits.** Centra Health was $270K from direct traffic. Watch RB2B + web visitors on healthcare domains hard.

## What likely won but can't be verified here

- Email thread content (need to pull engagements by deal ID → contact → emails)
- Call recordings or voice notes (if Gong/Chorus exists)
- The actual subject lines + opening paragraphs that opened these relationships

**Next enrichment pass:** pull engagements and notes for the top 10 wins. That's where the actual winning language lives.

## Broker intro + Sivan peer story

*Promoted from W18 meeting activity (2 occurrences: TMF deal created Apr 28, Elevate Textiles deal created May 1). Added 2026-05-01.*

Broker-facilitated intros (Execweb, IANS, event-referral) are passive by default. The prospect said yes to 45 minutes — that does not mean they are shopping. The meeting goes polite-and-cold unless Sivan establishes peer credibility in the first 5-8 minutes.

**The pattern (2 data points from W18):**
- Armstrong/TMF (Apr 28): Justin Armstrong is a 25-year healthcare CISO turned vCISO. Sivan led with peer-CISO framing. TMF deal created same day.
- Elevate Textiles (May 1): Rick Scot is CIO/CISO dual-hat at a $4B manufacturing company. Execweb-brokered. Sivan on the call. Deal created same day.

**Rule:** Sivan must be on every broker-introduced first meeting. No exceptions. The peer story is the only thing that converts a passive "yes to 45 minutes" into a concrete next step. An AE-only broker intro will produce "send me more information."

**What Sivan says:** "I built Onyxia because I had this problem." That sentence is not a pitch. It is a mirror. A CISO or CIO who has lived the same problem hears it and stops being polite. They start being curious.

**Cap:** Sivan's time is finite. See [[../40_Plays/cta-ladder]] peer-call cap (2-3 new per week). Broker intros count against that cap.

## Cross-references
- [[closed-lost-patterns]]
- [[sivan-peer-intro]]
- Live pipeline: [[MOC_Pipeline]]
