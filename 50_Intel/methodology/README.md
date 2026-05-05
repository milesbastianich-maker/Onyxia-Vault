---
title: Cold Email Methodology — Brain Map
tags: [methodology, cold-email, index]
updated: 2026-05-05
---

# Cold Email Methodology — Brain Map

This folder is the cold-email brain. Five files. Each one answers a different question. Open them in order; the answer to each unlocks the next.

If you only have time to read one thing before drafting, read [[advanced-copywriting-personalized-emails]] and stop pretending the rest matter for this draft.

## The five layers

| # | File | Question it answers | Stability |
|---|---|---|---|
| 0 | [[advanced-copywriting-personalized-emails]] | Why does a personalized cold email work? | Stable. Update rarely. |
| 1 | [[pain-library]] | Which of the 8 Onyxia spine pains do I lead with? | Slow change. Update when product capability shifts. |
| 2 | [[email-style-guide]] | What gates does this draft have to pass? | Medium change. Update when Miles names a new gate. |
| 3 | [[cold-email-canon]] | What pattern, in Miles's voice, has actually replied? | Append-only. Add canon entries as new winners ship. |
| 4 | [[cold-email-failure-modes]] | What pattern, when I drafted it, got discarded? | Append-only. Add modes after every discard. |

The numbering is the read order. Layer 0 is the WHY (general). Layers 1 to 4 are the HOW (Onyxia-specific).

## The flow for every cold email

```
[0] advanced-copywriting-personalized-emails
        principles + 4T + banned phrases (skim if recent)
                |
                v
[1] pain-library
        pick ONE spine pain. apply tenure / post-breach overrides.
        write the Pain Selection triplet.
                |
                v
[2] email-style-guide  (Section A + Section B + Section C)
        15-year-old gate. mandatory triplet format. sequence shape.
                |
                v
[3] cold-email-canon
        find the entry tagged to your spine pain.
        pattern-match the skeleton, swap in the recipient's facts.
                |
                v
        DRAFT
                |
                v
[2] email-style-guide  (Section J)
        Comprehension Test. write four plain-English answers.
                |
                v
[4] cold-email-failure-modes
        scan against the 8 modes. one hit means rewrite the line.
                |
                v
[2] email-style-guide  (Section K)
        sign-off block. locked. no variants.
                |
                v
        SAVE as Gmail draft. NEVER send without explicit approval.
```

## What lives where (don't double-store)

- **Principles, frameworks, banned-phrase library, paste-ready prompt** → layer 0 only.
- **Onyxia spine pains, pain triplet rule, persona × pain matrix, tenure / post-breach overrides** → layer 1 only.
- **Style gates, sequence architecture, comprehension test, sign-off block** → layer 2 only.
- **Verified examples that replied** → layer 3 only.
- **Verified examples that got discarded** → layer 4 only.

If you find a rule duplicated across layers, the lower-numbered layer wins. Delete the duplicate from the higher-numbered file and link to the source.

## Update triggers

| Trigger | File to update |
|---|---|
| Miles names a new principle, banned phrase, or rewrites the prompt | layer 0 |
| Onyxia ships a product change, or a spine pain stops fitting | layer 1 |
| Miles names a new gate, removes one, or changes the sign-off | layer 2 |
| A cold email gets a real reply | layer 3 (append; tag to spine pain) |
| Miles discards a draft with a reason | layer 4 (append the line + reason + rewrite) |

Append-only on layers 3 and 4. Never rewrite history on the corpus.

## Adjacent files (not part of the cold-email read order)

- [[buying-center-2026]] — who has authority by deal size and stage. Use during account planning.
- [[discovery-framework]] — for live calls, not cold email.
- [[draft-scoring]] — 8-criteria rubric. Drafter audits against this AFTER writing.
- [[linkedin-outreach]] — separate channel. Different read order. See its own file.
- [[measurement-log]] — outcome tracking. Drafter logs every shipped email here.
- [[objections]] — anticipate, not draft.
- [[touch-tracker]] — operator metadata. NEVER lives in the email body.

## How the agent reads this

The `onyxia-drafter` sub-agent is wired to read layers 0 through 4 in order before any draft, plus the Mandatory Context Gathering list (account file, contact file, Gmail thread, product files, persona, exclusions). See `~/.claude/agents/onyxia-drafter.md` for the full pre-draft consultation block. The drafter wins on conflicts only against itself; the layers in this folder win on conflicts against the drafter.

## Where to start when something feels off

- Draft sounds generic → re-read layer 0 (principles, especially Hyper-Personalization and 1-Year-Old Test).
- Draft sounds like a feature pitch → re-read layer 0 (Pain-Centricity) then layer 1 (pick a more specific pain).
- Draft sounds correct but flat → re-read layer 3 (canon) and pattern-match the rhythm of a real winner.
- Draft sounds dangerous, not sure why → re-read layer 4 (failure modes) and grep the draft against each mode's example line.
