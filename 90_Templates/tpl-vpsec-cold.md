---
type: template
persona: vpsec
created: 2026-04-22
tags: [template, p/vpsec]
---

# Template — VP Security Cold

VP Sec is often an ex-engineer running ops. Sometimes the de facto CISO. Treat as primary buyer if no CISO on record, champion if CISO exists above them. Peer tone. Technical specificity. 80-word cap. No em dashes. No corporate jargon.

See [[../50_Intel/personas/vp-security]]. Verify claims against [[../50_Intel/product/features]] before sending. For winning opener patterns once populated by another agent, see `50_Intel/product/winning-openers.md`.

## Structure

**Sentence 1 (operational pain anchor).** Specific + technical. Examples:
- Stack breadth reference ("you're running Splunk + CrowdStrike + Okta — reporting posture across those is a spreadsheet today").
- Board-deck assembly burden.
- Asset-coverage visibility gap.
- Benchmarking gap vs industry peers.

**Sentence 2 (specific Onyxia answer).** Anchor on one [[../50_Intel/product/features]] pillar:
- Stack Map auto-render on integration (pillar 2).
- Asset Coverage Analyzer (pillar 3).
- Automated Board & Executive Reporting (pillar 4).
- Benchmarking against industry SLA (pillar 5).
- Nexa query capability (pillar 9).

**Sentence 3 (peer credential).** Sivan-as-former-CISO anchor OR customer quote from [[../50_Intel/product/quotes]] (40-hour or 160-hour).

**Sentence 4 (ask).** Live Stack Map render against their known stack. Or Nexa demo against sample data. 15-20 minutes. Peer tone.

## Mandatory references for claims

- Feature claims → [[../50_Intel/product/features]]. Never invent.
- Integration catalog references → pull from [[../50_Intel/product/features]] Integration Catalog section.
- Customer quotes → verbatim from [[../50_Intel/product/quotes]].

## Anti-patterns (auto-reject)

- Skipping the VP Sec for the CISO ("can you connect me with [CISO]?" is a blocker move).
- Em dashes.
- Banned jargon list.
- Marketing-speak ("cutting-edge," "revolutionary," "game-changer").
- Rounded customer metrics.
- Invented features.
- Pricing.

## Expected objection + prep

From [[../50_Intel/methodology/objections]]:
- "We already have SIEM / EDR / Identity tools" → #1 (layer above, not replacement).
- "We need CISO sign-off" → good signal, offer co-brief.
- "Dashboard fatigue" → #8.
- "Integration lift concern" → Premera POC reference (2-4 weeks).

## Multi-thread note

If VP Sec reports to a CISO, multi-thread within 30 days. If VP Sec is the de facto CISO (no named CISO on record), treat as primary buyer + thread to CIO / CFO / GC per [[../50_Intel/playbook/closed-lost-patterns]].

## Runs

Log each send in the relevant `10_Accounts/{Company}.md` Timeline.

## Cross-references

- [[../40_Plays/sivan-peer-intro]]
- [[../40_Plays/reply-intent-parser]]
- [[../50_Intel/personas/vp-security]]
- [[../50_Intel/personas/ciso]]
- [[../50_Intel/playbook/closed-won-patterns]]
- [[../50_Intel/playbook/closed-lost-patterns]]
- [[../50_Intel/methodology/objections]]
- [[../50_Intel/product/features]]
- [[../50_Intel/product/quotes]]
- [[../50_Intel/triggers/exec-hire]]
- [[../50_Intel/triggers/ma-activity]]
