---
type: template
persona: grc
created: 2026-04-22
tags: [template, p/grc]
---

# Template — GRC Director Cold

GRC directors live in framework mappings + audit prep + vendor risk. They are a coach, not the EB. Open with a specific framework or deadline. Close with an offer to co-brief the CISO. 80-word cap. No em dashes. No corporate jargon.

See [[../50_Intel/personas/grc-director]]. Verify claims against [[../50_Intel/product/features]] + [[../50_Intel/industry/regulatory-calendar]] before sending. For winning opener patterns once populated by another agent, see `50_Intel/product/winning-openers.md`.

## Structure

**Sentence 1 (framework or deadline anchor).** Specific to prospect + their regulatory surface. Examples:
- "NYDFS Part 500 annual cert is April 15." (maps to [[../50_Intel/industry/regulatory-calendar]] finserv section)
- "OCR Phase 3 audits focus on risk analysis." (healthcare)
- "HIPAA Security Rule asset-inventory mandate is targeting May 2026 finalization." (healthcare NPRM)
- "CMMC Phase 2 locks in November 2026." (manufacturing/defense)

**Sentence 2 (GRC-specific pain, in their language).** Anchor on one observed pain from [[../50_Intel/personas/grc-director]]:
- Four-framework recertification burden.
- Two-week evidence collection per quarter.
- Auditor-trust gap on coverage claims.
- PDF-wall vendor risk.

**Sentence 3 (positioning — not replacement).** Onyxia pulls from the existing stack + feeds GRC tooling. Does NOT replace Archer / OneTrust / ServiceNow IRM. This is the pre-empt for [[../50_Intel/methodology/objections]] #7.

**Sentence 4 (ask).** 15-minute walk-through of Stack Map render against their stack, OR joint call with CISO + GRC. Peer tone.

## Mandatory references for claims

- Framework specifics → [[../50_Intel/industry/regulatory-calendar]].
- Product pillar claims → [[../50_Intel/product/features]] (especially pillar 7, Framework Compliance Dashboard).
- Customer quotes → verbatim from [[../50_Intel/product/quotes]].

## Anti-patterns (auto-reject)

- Any suggestion of replacing their existing GRC tool.
- Em dashes.
- Banned jargon list (see [[../00_Index/CLAUDE]]).
- Rounded customer metrics.
- Invented features.
- Pricing.

## Expected objection + prep

From [[../50_Intel/methodology/objections]]:
- "We use [Archer / OneTrust / ServiceNow IRM]" → #7.
- "This is the CISO's decision" → redirect to multi-thread.
- "We're building in-house" → #6 (reference 160-hour + 40-hour quotes).

## Multi-thread note

GRC is a coach, rarely the EB. Within 14 days of first-reply, engineer the CISO thread. Single-threaded GRC deals drift and die (60% of closed-lost had 1 contact per [[../50_Intel/playbook/closed-lost-patterns]]).

## Runs

Log each send in the relevant `10_Accounts/{Company}.md` Timeline + [[../40_Plays/sivan-peer-intro]] Runs section where applicable.

## Cross-references

- [[../40_Plays/sivan-peer-intro]]
- [[../40_Plays/reply-intent-parser]]
- [[../50_Intel/personas/grc-director]]
- [[../50_Intel/personas/ciso]]
- [[../50_Intel/playbook/closed-won-patterns]]
- [[../50_Intel/playbook/closed-lost-patterns]]
- [[../50_Intel/methodology/objections]]
- [[../50_Intel/industry/regulatory-calendar]]
- [[../50_Intel/product/features]]
- [[../50_Intel/triggers/sec-cyber-rule]]
