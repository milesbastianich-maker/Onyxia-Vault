---
type: play
vertical: healthcare
persona: ciso
trigger: new-CISO OR post-breach OR HIPAA-NPRM-countdown
created: 2026-04-22
tags: [play, v/healthcare, p/ciso]
---

# Healthcare CISO — First-Touch Sequence

Day 0, Day 5, Day 12. Three touches. If silent by Day 14, pattern-break per `50_Intel/methodology/objections.md` #10 (LinkedIn voice note or voicemail).

## When to run

Any healthcare CISO on a staged account where:
- New CISO 30-180 days in, OR
- Post-breach / post-settlement window ≤90 days, OR
- HIPAA Security Rule NPRM deadline within 180 days (target May 2026).

## Hard rules

- Reference `50_Intel/product/forbidden-words.md` — grep every draft before send.
- Quote customer verbatim only from `50_Intel/product/quotes.md`. The 160-hours quote is the load-bearing line for healthcare.
- Grep exclusion list before every send.
- Sivan peer-call (Touch 1) reserved for: trigger event ≤90 days + fit score ≥4 + Sivan's weekly cap (2-3) not saturated. Otherwise specific CTA.
- Under 90 words per touch. Longer = cut.

---

## Touch 1 (Day 0)

**Subject:** `HIPAA Security Rule — 3 items most programs aren't instrumented for`

**Body:**

> Hi <first>,
>
> HIPAA Security Rule finalization is targeted for May 2026. Asset inventory, network map, 72-hour restoration. Most healthcare programs we've looked at aren't instrumented for any of the three.
>
> One healthcare CISO described the before/after to us verbatim: "160 working hours a month that one full-time analyst would traditionally spend on manual reporting."
>
> Sivan, our CEO and former CISO, built Onyxia for this specific workflow problem.
>
> Worth 20 minutes next Tuesday or Thursday? No slides, no demo. CISO to CISO.
>
> Miles

**Trigger substitution:**
- Post-breach → swap sentence 1 for: "Post-settlement remediation is the hardest 90 days of a CISO's year. The board wants a path, and they want it this week."
- New CISO → swap sentence 1 for: "Congrats on the <Company> seat. The 90-day strategy slide is usually the hardest one in the first 90."

## Touch 2 (Day 5) — Bump

**Subject:** `one-pager — HIPAA program-reporting workflow`

**Body:**

> Hi <first>,
>
> Small attachment, no ask. Page 1 shows the control-mapping workflow that saved WellStar's team about a week per month of audit prep. Page 2 is Phase 3 OCR defensibility.
>
> If it lands, happy to pull up a shared screen for 20 minutes. If not, ignore.
>
> Miles

## Touch 3 (Day 12) — Breakup

**Subject:** `closing the loop`

**Body:**

> <first>,
>
> No reply so I'll assume the timing isn't right. Two specific moments when this usually becomes timely for healthcare CISOs:
>
> - 45 days before a board read-out.
> - The week after a covered-entity breach hits the news in your region.
>
> If either shows up, I'm here. Otherwise I'll stop cluttering your inbox.
>
> Miles

## Pattern-break (Day 14 if silent)

- LinkedIn voice note (<60s). Reference the specific regulatory trigger. No pitch.
- OR voicemail via ElevenLabs (Miles cloned voice). Under 25 seconds. Call out the specific account signal (new CISO, breach, deadline).

## Multi-thread

Parallel thread to GRC Director same day via `tpl-grc-cold.md`. Thread to CIO or CFO on Day 3 if the account is post-breach. Thread to General Counsel on Day 3 if the account is post-settlement.

## Measurement

Every touch logs a row in `50_Intel/methodology/measurement-log.md`:
- `touch`: 1 | 2 | 3
- `vertical`: healthcare
- `persona`: ciso
- `hook`: nprm | post-breach | new-ciso
- `reply_y_n`: set on Day 3 after each touch
- `meeting_booked`: set on reply+

## Runs

- YYYY-MM-DD — [[Account]] — outcome

## Cross-references

- [[../../sivan-peer-intro]]
- [[../../cta-ladder]]
- [[../../../50_Intel/verticals/healthcare]]
- [[../../../50_Intel/product/winning-openers]]
- [[../../../50_Intel/product/forbidden-words]]
- [[../../../50_Intel/product/quotes]]
- [[../../../50_Intel/triggers/breach-event]]
- [[../../../50_Intel/triggers/settlement-event]]
- [[../../../50_Intel/triggers/exec-hire]]
- [[../../../50_Intel/methodology/objections]]
