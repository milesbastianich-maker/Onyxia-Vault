---
type: play
vertical: manufacturing
persona: ciso
trigger: cmmc-countdown OR ot-breach-news OR defense-contract-win OR new-ciso
created: 2026-04-22
tags: [play, v/mfg, p/ciso]
---

# Manufacturing CISO — First-Touch Sequence

CMMC is the biggest forcing function through 2026-11-10. Second-biggest: OT-specific breach coverage in the press.

## When to run

- CMMC 2.0 enforcement inside 180d for accounts in DIB supply chain, OR
- OT or industrial-control breach in the account's sub-vertical within 90d, OR
- Defense contract award triggers compliance scoping, OR
- New CISO / new Head of OT Security.

## Touch 1 (Day 0) — CMMC variant

**Subject:** `CMMC November 10 — where most DIB programs are stuck`

**Body:**

> Hi <first>,
>
> CMMC Level 2 assessment windows are filling. The DIB CISOs I talk to are not worried about the 110 controls. They're worried about defensible evidence under a C3PAO review.
>
> Sivan, our CEO and former CISO, built Onyxia for the evidence-mapping problem specifically.
>
> 20 minutes next Tuesday? No slides.
>
> Miles

## Touch 1 (Day 0) — OT-breach variant

**Subject:** `the <competitor/peer> incident and the OT/IT split`

**Body:**

> Hi <first>,
>
> The <peer company> incident two weeks ago is every manufacturing CISO's "tomorrow could be us." The OT/IT split is where the reporting falls over, not the detection.
>
> One of our mfg customers described their pre-Onyxia state as "two different languages in two different dashboards with one board."
>
> Worth 20 minutes next week? Peer-to-peer.
>
> Miles

## Touch 2 (Day 5) — Bump

**Subject:** `C3PAO-ready evidence flow — one image`

**Body:**

> Hi <first>,
>
> One image. It's how our manufacturing customers show a C3PAO the evidence chain for the 110 Level 2 controls in a single view.
>
> If it lands, 20 minutes. If not, ignore.
>
> Miles

## Touch 3 (Day 12) — Breakup

**Subject:** `closing the loop`

**Body:**

> <first>,
>
> Stopping here. Two windows when this usually becomes timely for manufacturing CISOs:
>
> - 60 days before a CMMC assessment.
> - Any week an OT incident makes it to the board.
>
> Ping me if either hits.
>
> Miles

## Multi-thread

- Head of OT Security or Plant Security same-day (if exists).
- CIO on Day 3.
- Head of Supply Chain Risk on Day 7 for DIB accounts.

## Runs

- YYYY-MM-DD — [[Account]] — outcome

## Day 5 — Bump template

**Subject:** `C3PAO wait times update`

**Body (under 40 words):**

> <first>,
>
> Back to the CMMC thread. New data point: C3PAO wait times for new clients are projected past 18 months by Q3. With enforcement on November 10, the assessment-slot math is the part of the problem most DIB programs underestimate.
>
> Want 20 minutes?
>
> Basti

**Voice-rule audit (collapsed):**
<details>
<summary>Scores</summary>

- avoid-ai-writing detect: 5
- 8-criteria rubric: 5 (specificity cites 18-month wait projection + Nov 10 + Q3 timing, no em dashes, hedge-count 0, CTA unique from other verticals, Register-B clean, length 39 words, rhythm varied)
- Level-3+ personalization: pass (cites C3PAO capacity constraint specifically)
- Register-B phrase grep: clean
- Em-dash count: 0
</details>

## Day 12 — Breakup template

**Subject:** `stepping back on CMMC`

**Body (40-60 words):**

> <first>,
>
> No reply so I will assume the CMMC prep is on somebody else's desk right now. When the C3PAO books your Level 2 assessment window, or when NIST IR 8183r2 finalizes on the CSF 2.0 Manufacturing Profile, that is usually when the evidence-chain conversation becomes useful.
>
> I will be here either way.
>
> Basti

**Voice-rule audit (collapsed):**
<details>
<summary>Scores</summary>

- avoid-ai-writing detect: 5
- 8-criteria rubric: 5 (specificity names C3PAO Level 2 booking + NIST IR 8183r2 + CSF 2.0 Manufacturing Profile, no em dashes, hedge-count 0, future-trigger invite, Register-B clean, length 56 words, rhythm varied)
- Level-3+ personalization: pass (two vertical-specific regulatory anchors both sourced from regulatory-calendar.md)
- Register-B phrase grep: clean
- Em-dash count: 0
</details>

## Cross-references

- [[../../../50_Intel/verticals/manufacturing]]
- [[../../../50_Intel/verticals/defense-aerospace]]
- [[../../../50_Intel/triggers/breach-event]]
- [[../healthcare/ciso-first-touch]]
