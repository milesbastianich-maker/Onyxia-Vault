---
type: template
persona: ciso
created: 2026-04-22
tags: [template, p/ciso]
---

# Template — CISO Cold

Peer-to-peer. CISO to CISO. Sivan is the anchor. The ask is 20 minutes, no slides, no demo. 80-word cap. No em dashes. No corporate jargon.

See voice rules in [[../00_Index/CLAUDE]]. Verify every product claim against [[../50_Intel/product/features]] + [[../50_Intel/product/quotes]] before sending. For winning opener patterns once populated by another agent, see `50_Intel/product/winning-openers.md`.

## Structure

**Sentence 1 (personalization trigger).** Specific to prospect. Not generic. One of:
- New-role congrats + context (maps to [[../50_Intel/triggers/exec-hire]])
- Regulatory deadline in their industry (maps to [[../50_Intel/triggers/sec-cyber-rule]])
- Public filing reference (maps to [[../50_Intel/triggers/10k-8k-filing]])
- Post-incident rebuild framing (maps to [[../50_Intel/triggers/breach-event]] + [[../50_Intel/triggers/settlement-event]])
- Vertical-specific compliance moment (see [[../50_Intel/verticals/healthcare]] / [[../50_Intel/verticals/financial-services]] / [[../50_Intel/verticals/manufacturing]] / [[../50_Intel/verticals/critical-infrastructure]])

**Sentence 2 (specific pain, in their language).** Anchor on one observed CISO pain from [[../50_Intel/personas/ciso]] core-pains list.

**Sentence 3 (Sivan-as-peer, one line only).** From [[../40_Plays/sivan-peer-intro]]:
> Sivan Tehila, our CEO and former CISO, built Onyxia specifically for [this moment / this problem].

**Sentence 4 (ask).** 20 minutes. Peer call, not demo. Option to opt out cleanly.

## Mandatory references for claims

- Customer quotes → always verbatim from [[../50_Intel/product/quotes]]. Never paraphrase when a verbatim exists.
- Feature claims → verify against [[../50_Intel/product/features]].
- Deal-size or outcome claims → verify against [[../50_Intel/playbook/closed-won-patterns]].
- Regulatory specifics → verify against [[../50_Intel/industry/regulatory-calendar]].
- Breach stats → verify against [[../50_Intel/industry/breach-report-synthesis]].

## Anti-patterns (auto-reject)

- Em dashes.
- "Unlock," "leverage," "synergy," "seamless," "ecosystem," "empower," "streamline," "robust."
- Header "Hope this finds you well" + any variant.
- "I'd love to" + any variant.
- Rounded customer metrics.
- Invented features.
- Demo request as CTA. (Use peer call.)
- Pricing mentioned. See [[../50_Intel/methodology/objections]] #4.

## Expected objection + prep

Before sending, have the top 2 likely objections + response ready from [[../50_Intel/methodology/objections]]:
- "We already have X" → #1.
- "Not a priority" → #2.
- Silence → #10 (pattern-break at day 14).

## Follow-up cadence

Per [[../50_Intel/playbook/closed-lost-patterns]]: day 3, day 7, day 14, day 30, day 60. Pattern-break day 14 format (LinkedIn, voicemail, Loom). Multi-thread by day 30 per [[../50_Intel/personas/ciso]] objections.

## Runs

Log each send in [[../40_Plays/sivan-peer-intro]] Runs section + in the relevant `10_Accounts/{Company}.md` Timeline. Do not duplicate.

## Cross-references

- [[../40_Plays/sivan-peer-intro]]
- [[../40_Plays/reply-intent-parser]]
- [[../50_Intel/personas/ciso]]
- [[../50_Intel/playbook/closed-won-patterns]]
- [[../50_Intel/playbook/closed-lost-patterns]]
- [[../50_Intel/methodology/objections]]
- [[../50_Intel/product/quotes]]
- [[../50_Intel/product/positioning]]
- [[../50_Intel/triggers/exec-hire]]
- [[../50_Intel/triggers/breach-event]]
- [[../50_Intel/triggers/sec-cyber-rule]]
