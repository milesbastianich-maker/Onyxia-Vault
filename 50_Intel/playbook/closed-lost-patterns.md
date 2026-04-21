---
type: intel
subtype: playbook
topic: closed-lost patterns
source: HubSpot pull 2026-04-21 (113 closed-lost deals + 1 archived)
created: 2026-04-21
tags: [intel, playbook]
---

# Closed-Lost Patterns

113 deals lost at stage ID `71106477` (default pipeline, label "Closed Lost"). Roughly **$7.3M in lost pipeline across 2023-2026**. This is the cautionary tale.

## Loss reason breakdown (of deals with reason populated)

| Reason | Approximate share | Implication |
|---|---|---|
| **Non-responsive** | ~60% | Attention/timing problem. Prospects went dark. |
| **Time frame** | ~15% | Not urgent enough. Pain wasn't acute. |
| **Budget constraints** | ~10% | No economic buyer or no event-budget trigger. |
| **Missing integration / feature** | ~8% | Real product gap or perceived fit issue. |
| **Chose competing service** | **~1% (only 1 deal)** | Allied World. |
| **Job change** | ~3% | Champion left mid-cycle. |
| **Service not of value** | ~2% | Veterans United, Keurig Dr Pepper. |
| **In-house method** | ~1% | Amdocs. |

## The #1 insight (this is the whole playbook in one line)

**Onyxia does not lose to competitors. Onyxia loses to silence.**

Out of 113 documented losses, only ONE was lost to a competing service. The other 112 were lost to attention, timing, budget, or champion churn. The product wins every head-to-head. The losses are sales-motion problems, not product problems.

This changes the entire messaging strategy: stop defending against competitors that aren't there. Start engineering against silence.

## The silent-death pattern

Losses tagged "Non-responsive" share these features:
- **Single contact on the deal** (68 of 113 losses had only 1 contact)
- **Long gap between createdate and closedate** without stage progression. Deal sits in stage for months, then gets marked lost.
- **No second champion.** One point of failure. When they go quiet, the whole deal goes quiet.

**Mitigation playbook:**
- Every active deal must have ≥2 engaged contacts within 30 days of first meeting.
- Follow-up cadence: day 3, day 7, day 14, day 30, day 60. Pattern-break at day 14 with a different format (voicemail, Loom, LinkedIn message).
- Day 45 with no response = breakup email. Day 60 with no response = disqualify and move to nurture.

## The BigLaw pattern

Sullivan & Cromwell, Milbank, Lowenstein Sandler — all $50-100K, all "Non-responsive." Simpson Thacher is the ONE BigLaw that closed, and it took 577 days.

**Implication:** BigLaw has a loud security buzz but a silent buying process. Expect non-response to be the default. Simpson Thacher likely had a peer-intro from Sivan's network. Don't target BigLaw without a warm path in.

## The Healthcare pattern (losses)

Montefiore, Cleveland Clinic, Main Line Health, Hoag, Christ Hospital Health Network, Healthfirst, Brighton Health Plan Solutions, University of Illinois Hospital, Kansas Med Center, Oscar Health, Temple Health, Smile Brands, Blink Health, Christian Care Ministry, Delta Dental.

**Healthcare losses vs healthcare wins (Centra, WellStar, Premera, Christiana):**
- Wins average 2-5 associated contacts. Losses average 1-2.
- Wins have a clear champion named in HubSpot. Losses don't.
- Won healthcare deals spent $60K-$270K. Lost healthcare deals also spent at the same size — so **deal size is not the differentiator. Multi-thread + champion is.**

## The high-value loss pattern

Biggest losses by dollar:
- Centra Health (won after loss attempts) — $270K
- WellStar (won) — $172K
- Premera (won) — $170K
- Interpublic Group (IPG) — $150K — non-responsive
- Radiant Logic (won) — $165K
- HarbourVest — $125K — non-responsive
- Port Authority NY/NJ (won) — $135K

**Notice:** The biggest "losses" were often re-won later. The pattern is that persistence on large enterprise accounts eventually wins. This is an argument for **not disqualifying enterprise accounts after initial non-response.**

## The 1-contact death trap

60% of losses had only 1 associated contact. This is the single most predictive feature in the data.

**Rule:** If a deal sits at 1 contact for > 30 days after first meeting, it is in the at-risk column. Flag it in the weekly review. Either multi-thread it or disqualify.

## The time-frame excuse

"Time frame" losses include Delta Dental, Covered California, Cleveland Clinic, Temple Health, Hoag, Alteryx, Postman, Bill.com, Auror, Digital Realty, Smile Brands, Brighton Health, Drake Software (job change variant), CCC (before it was won).

**Decode:** "Time frame" usually means "no economic buyer + no event trigger." Pain wasn't expensive enough relative to the other fires.

**Mitigation:** For Tier 1 accounts that come back with "time frame," don't disqualify. Add them to a `50_Intel/nurture/` list and re-approach on a new trigger event (breach news, new CISO, funding round, M&A).

## The job-change champion collapse

3 deals died because the champion left: Drake Software, PointHR, Ted Baker.

**Mitigation:** Multi-thread from the start. Ideally your champion + their boss + a peer. Champion singularity = fragile deal.

## The Israeli-vendor pattern (Sivan flagged this on 2026-04-15)

Sivan's quote: *"these Israelis... they are very annoying. Even if they like something they wont tell you and they are also cheap."*

Watch for Israeli-market deals. Examples from the loss set: Coca-Cola Israel, Mesh Payments, AppsFlyer, Sumitomo (not Israeli), Fireblocks. Pattern: Israeli buyers will demo, engage, and never commit. Disqualify faster for Israeli entities than US entities.

## The budget-constraint pattern

Budget losses: Montefiore, Main Line Health, CSC, Insulet, Lowenstein Sandler, Fitch Group, Christian Care Ministry, Inspectiv.

**Decode:** Budget is often code for "no economic buyer found." We never got to the person who signs off.

**Mitigation:** Enrichment must include org-chart / reports-to data. Identify the CFO / CIO / CISO before the first meeting. MEDDPICC Economic Buyer slot must be named before any proposal is sent.

## What to do differently (action list for Miles)

1. **Stop tracking "non-responsive" as a fatalism.** Treat it as a diagnostic: we missed the multi-thread window. Engineer against it.
2. **Multi-thread every deal to ≥2 contacts within 30 days.** No exceptions on Tier 1.
3. **Don't chase BigLaw without a warm path.** Use Sivan's network or don't pursue.
4. **Add an "at-risk-single-thread" tag and a Dataview query** in MOC_Pipeline. Weekly review surfaces these.
5. **Build a nurture bucket for "time frame" losses on Tier 1.** Re-approach on trigger events.
6. **Disqualify Israeli entities faster.** Sivan said so. Data backs it.
7. **Economic Buyer must be named before proposal.** No proposal goes out with an empty EB slot.

## Cross-references
- [[closed-won-patterns]]
- [[MOC_Pipeline]]
- [[sivan-peer-intro]]
