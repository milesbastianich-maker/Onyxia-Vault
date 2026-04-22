---
type: play
vertical: financial-services
persona: ciso
trigger: nydfs-500-amendments OR dora-enforcement OR new-ciso OR 8k-incident
created: 2026-04-22
tags: [play, v/fins, p/ciso]
---

# Financial Services CISO — First-Touch Sequence

Day 0, Day 5, Day 12. Same pattern as healthcare sequence, different anchors.

## When to run

- NYDFS 500 amendment deadline inside 180 days, OR
- DORA operational enforcement (live since Jan 2025) + EU exposure, OR
- 8-K Item 1.05 cybersecurity disclosure filed within 90 days, OR
- New CISO 30-180 days in.

## Hard rules

Same as healthcare. Reference `forbidden-words.md`, quote verbatim from `quotes.md`, cap 90 words, voice-test before send.

---

## Touch 1 (Day 0) — 8-K trigger variant

**Subject:** `your 8-K and the next 60 days`

**Body:**

> Hi <first>,
>
> The <date> filing moved your cyber program from CISO-owned to board-visible overnight. Most of the CISOs we talk to a week after a material disclosure describe the same 60-day gauntlet: evidence, remediation path, board read-out every two weeks.
>
> Sivan, our CEO and former CISO, built Onyxia to turn that gauntlet into one workflow instead of 40 spreadsheets.
>
> Worth 20 minutes? No slides. Peer-to-peer.
>
> Miles

## Touch 1 (Day 0) — DORA variant

**Subject:** `DORA vendor inventory — where most fins programs are stuck`

**Body:**

> Hi <first>,
>
> DORA has been in force since January. The UK fins CISOs we talk to are still chasing their vendor-inventory completeness score. The article 28 register is the blocker, not the policy text.
>
> One of our fins customers described the before/after as the shift from "spreadsheet-from-hell to automation" (verbatim).
>
> Worth 20 minutes next week? No slides.
>
> Miles

## Touch 1 (Day 0) — NYDFS variant

**Subject:** `NYDFS Part 500 amendments — the two operational items`

**Body:**

> Hi <first>,
>
> The NYDFS Part 500 amendments push two operational items most programs aren't ready for: asset-inventory accuracy and MFA completeness evidence, both on a 72-hour review clock.
>
> Sivan, ex-CISO now Onyxia's CEO, built the platform for that specific evidence-on-demand problem.
>
> 20 minutes next Tuesday? Peer-to-peer.
>
> Miles

## Touch 2 (Day 5) — Bump

**Subject:** `short example — the board slide`

**Body:**

> Hi <first>,
>
> One image, not a deck. It's the single slide our customers use for their audit committee the week a CFR filing lands. No ask if it's not useful.
>
> Miles

## Touch 3 (Day 12) — Breakup

**Subject:** `closing the loop`

**Body:**

> <first>,
>
> No reply so I'll step back. Two moments when this usually becomes timely for fins CISOs:
>
> - 30 days before a DORA operational deadline.
> - Any week the regulator asks for evidence in <72 hours.
>
> Either one, ping me. Otherwise I'll stop.
>
> Miles

## Multi-thread

- Chief Risk Officer (fins-specific Rank 2) same-day thread via `tpl-vpsec-cold.md` adapted — CRO buys the regulatory-risk narrative faster than CFO here.
- Director GRC on Day 3.
- GC on Day 7 if 8-K trigger.

## Runs

- YYYY-MM-DD — [[Account]] — outcome

## Day 5 — Bump template

**Subject:** `NYDFS April 15 cert`

**Subject (DORA variant):** `DORA register Article 28`

**Body (under 40 words):**

> <first>,
>
> Picking up the NYDFS thread. The April 15 Appendix A certification is the first year CISOs own it in writing. The board-reporting requirement is where most programs are behind, not the policy.
>
> Grab 20 minutes this week?
>
> Basti

**Voice-rule audit (collapsed):**
<details>
<summary>Scores</summary>

- avoid-ai-writing detect: 5
- 8-criteria rubric: 4 (specificity names April 15 + Appendix A, no em dashes, hedge-count 0, CTA differs from healthcare, Register-B clean, length 36 words, rhythm varied; Sivan-sentence N/A for bump)
- Level-3+ personalization: pass (names NYDFS Part 500 April 15 certification + board-reporting clause, verbatim from regulatory-calendar.md)
- Register-B phrase grep: clean
- Em-dash count: 0
</details>

## Day 12 — Breakup template

**Subject:** `back-burner for now`

**Body (40-60 words):**

> <first>,
>
> Assuming this is not the right quarter. If an 8-K Item 1.05 lands on your desk, the 60 days of board read-outs that follow is usually when a 20-minute peer call pays back. Same goes if the next NYDFS amendment drops.
>
> Ping me on either and I will come with one slide, not a deck.
>
> Basti

**Voice-rule audit (collapsed):**
<details>
<summary>Scores</summary>

- avoid-ai-writing detect: 5
- 8-criteria rubric: 5 (specificity names 8-K Item 1.05 + NYDFS amendment + 60-day window, no em dashes, hedge-count 0, future-trigger invite not hard ask, Register-B clean, length 56 words, rhythm varied)
- Level-3+ personalization: pass (specific SEC rule subsection + named follow-on regulatory cycle)
- Register-B phrase grep: clean
- Em-dash count: 0
</details>

## Cross-references

- [[../../../50_Intel/verticals/financial-services]]
- [[../../../50_Intel/triggers/sec-cyber-rule]]
- [[../../../50_Intel/triggers/10k-8k-filing]]
- [[../../../50_Intel/industry/regulatory-calendar]]
- [[../healthcare/ciso-first-touch]]
