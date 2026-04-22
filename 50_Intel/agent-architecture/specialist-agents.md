---
type: intel
subtype: agent-architecture
created: 2026-04-22
tags: [intel, agent-architecture]
---

# Specialist Sub-Agent Architecture

`onyxia-operator` is the generalist. For high-leverage work, delegate to four specialists. Each has a narrow scope, a locked toolbelt, and a handoff contract.

## Why four specialists, not one super-agent

Per `external-patterns.md`, 11x's Alice was rebuilt as multi-agent after monolithic design lost context on deep research. Onyxia's current shift architecture (morning-brief, watchdog, midday, eod) already mirrors this pattern at the time-axis. Specialists mirror it at the capability-axis.

The leverage insight: **deep specialization within each scope beats horizontal expansion.** A focused researcher that only reads does not contaminate its context with drafting voice-rules. A drafter that only writes under tight voice gates produces cleaner copy than a generalist. An auditor that only compares state against rules catches drift the generalist would rationalize away.

## The four specialists

### 1. `onyxia-researcher` (read-only)
Scope: research + synthesis, never write.
Tools: all MCP reads, WebSearch, WebFetch, vault Read/Grep/Glob.
Invocation: account deep-dive, regulatory scan, competitive intel, cross-vault sweep.
Output: structured markdown text returned to operator, never vault write.

### 2. `onyxia-drafter` (Gmail draft-only)
Scope: draft outbound copy, voice-gate, create Gmail drafts.
Tools: vault Read/Grep, Gmail create_draft + list_drafts + search_threads.
Invocation: cold email, voicemail script, LinkedIn connect.
Hard gates: forbidden-words grep, winning-openers structure match, peer-tone, specificity.
Output: Gmail draft ID + voice-test pass/fail report.

### 3. `onyxia-hunter` (prospect discovery)
Scope: run ZoomInfo hunts, dedupe HubSpot, score fit, stage accounts.
Tools: ZoomInfo full, HubSpot read + contact-create, vault Read/Write.
Invocation: scheduled hunt shifts, ad-hoc white-space scans, intent-signal follow-ups.
Discipline: HubSpot-dedupe BEFORE contact-enrichment (credit burn), respect territory (Brad-owned = skip), seed only from ICP-qualified closed-won.
Output: staged `10_Accounts/` stubs + hunt log.

### 4. `onyxia-auditor` (vault + process audit)
Scope: scan for drift, contradictions, stale content, promotion opportunities.
Tools: vault Read/Write/Edit/Grep, HubSpot read-only.
Invocation: quarterly full sweep, weekly mini sweep (Friday shift), ad-hoc on drift signal.
Discipline: propose, never edit without operator ACK. Never touch CLAUDE.md without Miles.
Output: per-area finding list with proposed fixes.

## Handoff contracts

Every specialist returns a structured YAML or markdown block. Operator parses, decides, commits.

### Researcher → Operator
```yaml
task: <one-line>
findings: [{claim, source_url, retrieval_date, confidence}]
cross_references: [vault_paths]
open_questions: []
recommended_next: <one sentence>
```

### Drafter → Operator
```yaml
draft_id: <Gmail ID>
voice_tests: {forbidden_grep, structure_match, peer_tone, specificity}
objection_prep: {likely_objection, response_line}
cta_tier: passive | specific | peer-call
```

### Hunter → Operator
```yaml
hunt_pattern: <name>
candidates_raw: n
candidates_final: n
accounts_staged: [list]
territory_conflicts: [list]
log_file: <path>
```

### Auditor → Operator
```markdown
## Audit <date>
### <area>
- <finding> Propose: <fix>. ACK?
```

## When the operator orchestrates

- **New-account end-to-end:** researcher (deep-dive) → hunter (score + stage) → drafter (multi-thread drafts) → operator posts to `#miles-ai-ops` for ✅.
- **Weekly synthesis:** auditor (mini sweep) → researcher (cross-vault pattern scan) → operator writes `60_Lessons/YYYY-WW-review.md`.
- **Quarterly self-audit:** auditor (full sweep) → operator walks findings with Miles in live session.
- **Deal save (silent champion):** researcher (org chart refresh) → hunter (if net-new-contact identified) → drafter (recovery sequence).

## Why not a fifth specialist?

Candidate fifth roles considered and rejected:

- **A "sender" that sends approved drafts.** Blast radius too high. Keep send gated to human-approved Gmail action. Consolidate approval ritual in `#miles-ai-ops` reaction gating.
- **A "closer" for late-stage deals.** Late-stage needs human judgment. The operator + Miles is the closer. A specialist would introduce template drift on legal and pricing.
- **A "negotiator."** Same reason as closer.

## Rollout

- Researcher, Drafter, Hunter, Auditor definitions landed at `~/.claude/agents/onyxia-<role>.md`.
- First invocation: next session, route the winning-openers follow-up pull (Miles's own Gmail sent folder) through `onyxia-researcher` to prove the handoff contract.
- Measurement: every specialist invocation logs a row in `50_Intel/methodology/measurement-log.md` with `agent: onyxia-<role>`, `task`, `duration_ms`, `findings_count`, `operator_accepted: Y/N`.

## Cross-references

- [[./external-patterns]]
- [[../../.claude/agents/onyxia-operator]] (canonical generalist)
- [[../methodology/measurement-log]]
