---
type: intel
subtype: methodology
topic: draft scoring rubric
created: 2026-04-22
tags: [intel, methodology]
---

# Draft Scoring Rubric

Every cold-outbound draft routed through `onyxia-drafter` is scored 1-5 against this rubric BEFORE it lands in Gmail drafts. The drafter sub-agent runs this check automatically and logs the score to `measurement-log.md`.

Goal: catch AI-ism patterns before they ship. Shipped-but-flagged drafts get post-hoc scoring so we learn what the prospect reply rate correlates with.

## The 8 criteria

Each scored 0-1 (fail/pass). Sum → 1-5 band.

1. **Specificity.** Sentence 1 references a concrete fact that cannot be said about any other prospect (exec hire date, specific filing, settlement amount, exact employee count, specific role transition). Generic-industry-hook = fail.
2. **Sivan-sentence uniqueness.** The Sivan-as-former-CISO line is NOT structurally identical to any other draft in the current send batch. Each Sivan line names a specific capability tied to THIS prospect's context. Pattern `"Sivan Tehila, our CEO and former CISO, built Onyxia for exactly that [X] moment/seat/workflow"` repeated across drafts = fail.
3. **No em dashes.** Agent-written prose has zero em dashes. Miles's own prose may use them; agent drafts do not. One em dash = fail.
4. **Hedge-count zero.** No "specifically," "exactly," "at this scale," "in order to," "going to ask for," or other filler modifiers. Max one per draft = pass. Two+ = fail.
5. **CTA variation across batch.** In any send batch of 3+, at least 3 distinct CTA forms. Three identical "Worth a short call? No slides." endings = fail.
6. **Register-B phrase grep.** Draft contains zero of the banned phrases from `forbidden-words.md` (the "tend to inherit a toolbox," "logo garden," "rough job of explaining," etc. list). One hit = fail.
7. **Length.** Body is 60-100 words. Under 60 = underpowered. Over 120 = cut. Pass = inside range.
8. **Rhythm.** At least one paragraph under 2 sentences AND at least one paragraph over 2 sentences. Uniform paragraphs = fail.

## Scoring bands

- **5/5** — all 8 pass. Ship.
- **4/5** — 7 pass. Ship if the failed criterion isn't em-dash or Register-B phrase. Otherwise fix.
- **3/5** — 5-6 pass. Revise before ship.
- **1-2/5** — under 5 pass. Rewrite from scratch.

## Workflow

1. `onyxia-drafter` generates draft.
2. Before Gmail `create_draft` call: drafter invokes `avoid-ai-writing` skill in detect mode on the draft text + checks the 8 criteria.
3. Draft score posted to `#miles-ai-ops` with the draft preview.
4. If score <4, drafter does NOT create Gmail draft. Posts revise-request to ops channel instead.
5. If score ≥4, drafter creates Gmail draft, posts with score.
6. Miles reacts ✅ to send, 👎 to kill, ✏️ to request edit.
7. Every send logs to `measurement-log.md` with score + reply outcome.

## Cross-references

- [[../product/forbidden-words]]
- [[../product/winning-openers]]
- [[../product/power-phrases]]
- [[../../.claude/agents/onyxia-drafter]]
- [[./measurement-log]]
