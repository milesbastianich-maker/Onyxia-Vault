---
type: methodology
category: voice
status: canonical
last_updated: 2026-05-04
source: Miles direct 2026-05-04 — "a 15-year-old could read it and see the value Onyxia has for its company" + 35-draft discard postmortem
applies_to: onyxia-drafter, onyxia-operator
relationship_to_v2: ADDITIVE override. The 15-year-old gate (Section A) and Pain Selection (Section B) sit ABOVE all v2 rules. The two-step sequence is the new DEFAULT for cold cycles.
companion_files:
  - 50_Intel/methodology/README.md (the brain map — start here if the system feels confusing)
  - 50_Intel/methodology/advanced-copywriting-personalized-emails.md (the WHY layer — principles, 4T framework, banned phrases)
  - 50_Intel/methodology/pain-library.md (the spine pains — read FIRST on every draft)
  - 50_Intel/methodology/cold-email-canon.md (7 annotated examples — pattern-match against)
  - 50_Intel/methodology/cold-email-failure-modes.md (8 failure modes from the 35-draft discard)
---

# Onyxia Email Style Guide

Read in this order on every cold-email task:

1. `advanced-copywriting-personalized-emails.md` — refresh principles + 4T framework (skim if recent)
2. `pain-library.md` — pick the spine pain
3. THIS FILE — apply Section A (15-year-old gate) and Section B (Pain Selection mandatory triplet)
4. `cold-email-canon.md` — find the canon entry tagged to your spine pain, pattern-match
5. Draft
6. THIS FILE Section J — run the Comprehension Test (written answers)
7. `cold-email-failure-modes.md` — scan against the 8 failure modes
8. v2 hard gates and audit (existing rules in `~/.claude/agents/onyxia-drafter.md`)
9. Save with the Section K sign-off block

If anything in this guide conflicts with v2 or memory files, this guide wins. Section A wins over everything; Section B wins over everything else.

---

## Section A — The 15-Year-Old Gate (top-level override)

Before any other voice check, before any v2 audit, every cold email must pass this:

> A 15-year-old reads the email once. They can answer in one sentence: "What does Onyxia do for this company?"

If they can't, rewrite. No exceptions.

The Onyxia value sentence in the email must be writable as:

> Onyxia [does this specific thing] so you don't [waste this specific time or effort].

**The cab-driver test:** read the draft. If a NYC cab driver could not explain what Onyxia does after reading it, rewrite.

### The 8-second test

Read the draft as the recipient on a phone. In 8 seconds (the time it takes to scan), can they answer:

1. What is this email about? (The trigger / hook.)
2. What hurts in my world? (The Pattern Statement / spine pain in plain English.)
3. What does Onyxia do for me? (The value sentence.)
4. What am I being asked? (The ask, if any.)

If any answer is "I don't know," rewrite.

### Sentence-level rules layered on v2

- Sentences average 14 words or fewer.
- One idea per sentence. Two ideas = split.
- No subordinate clauses in the value sentence. The value sentence is one short main clause.
- Verbs over nouns. "Onyxia tracks X" beats "Onyxia provides tracking of X."

---

## Section B — Pain Selection (mandatory pre-draft triplet)

Before drafting any cold email, the drafter must:

1. Read `~/ObsidianVault/50_Intel/methodology/pain-library.md` in full.
2. Read the contact file for THIS recipient.
3. Use the matrix in `pain-library.md` to select ONE spine pain. Apply tenure override (under 12 months → Pain #4) and post-breach override (8-K filed in last 90 days → Pain #3).
4. Write three lines IN THE RETURN PAYLOAD before any draft body:

```
spine_pain: <Pain #N — short name from pain-library.md>
why_this_pain_for_this_person: <one sentence, contact-specific. Names something verifiable about THEIR situation.>
onyxia_response_plain_english: <one sentence. Verb + concrete object + "so you don't [concrete waste]". No abstract nouns.>
```

If any of the three is vague, hedged, or could be pasted onto a different contact by changing names, the drafter REFUSES to draft and returns a research request to the operator.

### Worked example

**Contact:** Robert Sherman, CISO, Lantheus, 16 months in role, public NASDAQ company in radiopharmaceuticals.

**Pain Selection:**

```
spine_pain: Pain #4 — new-leader inheritance
why_this_pain_for_this_person: Sherman is 16 months into the CISO seat at a public NASDAQ life-sciences company; the moment when the board starts asking what shape the program is in lands during the next two quarters.
onyxia_response_plain_english: Onyxia gives you a clean baseline of your program in 30 days, so you walk into the next board prep with a real number instead of a hand-built slide.
```

This triplet is the spine of the email. Everything else (trigger, Pattern Statement, customer quote, Sivan line, ask) builds from it.

### What the triplet rules out

- Selecting "Pain #3 — board-ready" because the company is public, when the contact is actually a new-leader (Pain #4 wins).
- Selecting "Pain #5 — multi-framework" because the company has FDA + SEC, when the contact is actually a new-leader (Pain #4 wins).
- Selecting any pain that requires you to invent the contact's situation rather than verify it.

### Failure mode the triplet prevents

The 35-draft discard had drafts where the drafter never selected a spine pain. It anchored on regulations because regulations are concrete and easy to research. Pain Selection forces the drafter to do the harder research: who is this person, what hurts in their actual day-to-day.

---

## Section C — Sequence Architecture (the new default)

Default cold cycle is now TWO emails, not one. Single-touch is reserved for event invites, multi-thread referrals, post-meeting follow-ups, replies, and Day-5 bumps.

### Email 1 — Informative (no ask, no meeting push)

- Body: 60-90 words. Shorter than v2's 60-110 default.
- **Hook (sentence 2):** verifiable trigger about THEIR company with date or quarter required. NOT a regulation; an event (settlement, hire, M&A, board change, IPO filing).
- **Pattern Statement (sentence 3):** names the spine pain in plain English in the recipient's language. See canon for examples.
- **Customer quote OR Sivan line (sentence 4-5):** verbatim from `quotes.md` with profile-match setup. Or single-sentence Sivan-as-former-CISO.
- **Onyxia-response (sentence 5-6):** one short main clause. Verb + concrete object + concrete waste avoided. Passes the 15-year-old gate. Banned abstract nouns from Section G ruled out.
- **Soft close:** NOT a question, NOT a meeting ask. Examples:
  - "Sharing in case it helps."
  - "Worth having on your radar."
  - "Figured this fits the work you are already doing."
  - "Putting it on your screen, not your calendar."
- Sign-off block: Section K. Mandatory.

**What Email 1 is NOT:**
- Not a question of any kind
- Not "let me know if helpful"
- Not "happy to send more"
- Not a calendar link
- Not a deck attachment

### Email 2 — Ask (sent 3-5 business days after Email 1, only if no reply)

- Body: 50-75 words.
- **Open:** reference Email 1 explicitly with the date. "Sent you a note on [Mon DD] about [topic from Email 1 hook]."
- **Bridge:** one new angle or sharper restatement of why this matters NOW. Not a copy-paste of Email 1. Often the customer quote OR Sivan line that didn't fit in Email 1.
- **Ask:** one sentence. Time-bound. Binary.
  - Tier 1/2: "Worth 20 minutes the week of [Mon DD]?"
  - Tier 3/4: "Want me to send the one-pager?" / "Open to a 15-minute call [day] or [day]?"
- Sign-off block: Section K. Mandatory.

### Why two emails

Email 1 establishes credibility without triggering the meeting-decline reflex. Most cold emails fail because the first line says "I want your time." Email 1 says "I want to give you a piece of information about your world." That gets read.

Email 2 cashes in. Reply rates compound — the recipient already saw Email 1, so Email 2 lands as a continuation, not a cold. The ask in Email 2 is easier to say yes to because the sender has already proven they know what they are talking about.

### When NOT to use the two-step (single-touch motions)

- Event invite (use v2 `event_invite` playbook)
- Multi-thread referral ask (use v2 multi-thread subject pattern)
- Post-meeting follow-up (use v2 `post_meeting_follow_up`)
- Reply to inbound (use v2 `reply_to_reply`)
- Day-5 bump on existing thread (use v2 `day_5_bump`)
- Warm-revive on a contact with a known prior dark thread (use single re-engagement with new genuine signal)

### Default decision

Unless the operator specifies single-touch, draft a TWO-email sequence: Email 1 informative + Email 2 ask. Save BOTH as separate Gmail Drafts, with Email 2 marked in metadata for send-after-3-business-days.

---

## Section D — Style by Title Tier

Match the recipient's tier. The Pain Selection happens first; the tier modulates HOW the email is voiced.

### Tier 1 — Economic Buyer (CISO, CSO, CRO, VP/SVP Security, Head of Security)

**Voice:** peer, not vendor. Plain English. Strategic priority tied to public signal. NEVER pitch tools. Tools talk down to a CISO.

**Onyxia framing for Tier 1:** Onyxia is about TIME and BOARD VISIBILITY, not features. "Onyxia auto-generates the board report your team is building by hand." "Onyxia gives you one number for the audit committee."

**Banned framings for Tier 1:**
- "Compliance automation tool"
- "Visibility across your stack"
- "Continuous control monitoring"
- "Single pane of glass"

### Tier 2 — Senior Influencer (Deputy CISO, BISO, VP GRC, VP Cyber Risk, VP IT Risk, VP Tech Risk)

**Voice:** co-sign register. Reference the CISO/EB by name when known. They are usually the operational owner who runs the eval.

**Onyxia framing for Tier 2:** "Onyxia produces the report you are already building for [CISO name] every quarter, but on demand." "Onyxia is what your CISO will ask you to evaluate when [trigger] hits."

### Tier 3 — Champion (Director Information Security, Director GRC, Director SecOps, Head of GRC, Head of Cyber Risk)

**Voice:** champion register. Slightly more technical OK. Map their pain to what their CISO will care about — that is how they sell internally.

**Onyxia framing for Tier 3:** "Onyxia gives you the data your CISO is going to ask for, before they ask." "Onyxia replaces the eight tools your team is stitching together for the audit."

### Tier 4 — Senior Champion (Senior Director Information Security, Senior Director Cybersecurity)

**Voice:** treat as Tier 3 with seniority weight. They are usually one year from a CISO seat.

### Tier mismatch handling

If the contact's actual title doesn't fit cleanly:

- **VP Compliance / Compliance leader:** treat as Tier 2 with audit/evidence framing, NEVER tool framing.
- **CIO:** treat as Tier 1 but anchor on IT-program load and budget pressure. "Onyxia lowers the lift on what your security team is already doing."
- **Senior Director IT:** treat as Tier 4 with IT-program lean. Anchor on cross-functional load.
- **ERM / Enterprise Risk Director:** treat as Tier 2 with governance lean. "Onyxia is the paper trail your board will ask for, in one place."
- **Privacy Officer:** out of scope per `target-titles.md`. Drafter must refuse.

---

## Section E — Tenure Inflection Layer

Layer this on top of the title-tier voice. Tenure changes WHAT the email anchors on.

### New-leader (under 12 months in role)

**This is automatic Pain #4.** No matter what the vertical default says, sub-12-month tenure overrides. The hook anchors on the inflection itself.

- Hook lead: "[Specific public signal] put you in the [role] seat at [Company] in [month/year]."
- Onyxia framing: "Onyxia gives you a clean baseline of your program in 30 days, not 9 months."
- Tone: peer who has navigated this. Sivan peer-call frame works well.
- Avoid: "you have a long tenure ahead" (patronizing). "Use this to make your mark" (vendor-y).

### Scaling-program (12-24 months in role)

Hook on what is growing.

- Hook lead: "[Specific signal — team hire, tool purchase, board statement] suggests you are scaling the [program area] right now."
- Onyxia framing: stress integration, not replacement.
- Avoid: "starting from scratch" / "mature program optimization."

### Mature-program (24+ months in role)

Peer-only register, NEVER pitch tools.

- Hook lead: "[Specific event — settlement, hire above them, breach in adjacent sub-vertical, M&A]."
- Onyxia framing: "Sivan was a CISO." Or share what other [vertical] CISOs are doing.
- Avoid: "modernize your program" (insulting). "Optimize your stack" (vendor-y).

### Tenure unknown / accuracy below 85

Default to mature-program tone. Anchor on event or scoop, never on tenure.

---

## Section F — Auto-Reply and Touch-Point Handling

| Inbound state | Drafter action |
|---|---|
| OOO bounce | Operator sets calendar reminder for return-date + 2 business days. Drafter does not draft yet. |
| Wrong-person redirect | Two drafts: thank-you to original + fresh Email 1 to redirect, naming the original referrer in sentence 1. |
| "Not interested" | One draft: "Understood. If [trigger] becomes a priority later, my door is open." Tag `cold/declined`, 6-month reactivation window. |
| "Send more info" | One draft: 80 words max, ONE concrete artifact (one customer quote OR one regulation summary OR one one-pager link). End with the meeting ask. |
| "Not now, ping me in [timeframe]" | Acknowledge in one line. Calendar reminder for the date THEY named. No further touches until that date. |
| Genuine engagement | Match their format and length. Answer their question first. End with meeting ask if it fits. |
| Silent past Email 2 + 7 business days | Day-12 breakup. Single sentence: "Closing the loop. If [trigger] becomes a priority, my door is open." 40-60 words. |
| Silent past breakup | NO further touches. Tag `silent_30d`. Re-engage only on genuine new trigger event. |

### Auto-reply during Miles vacation / OOO

When Miles is out, drafter generates HOLDING replies (not full responses) for any inbound that arrives:

- 30-50 words max
- Acknowledge receipt
- State the return date
- ONE specific commitment (when Miles will respond, what he will respond with)
- No new asks, no calendar links, no new value pitches
- Sign-off block: Section K. Mandatory even on holding replies.

Sample holding reply:
> "Got this. Out of inbox until [return date]. Will pick up [topic from their email] first thing back and reply by [return date + 2 business days].
>
> Cheers,
> Miles Bastianich
> Onyxia Cyber
> 203-524-8880"

---

## Section G — Concrete-Noun Discipline

Replaces the old phrase-list ban with a category rule. Sibling-evasion is the dominant failure mode in the 35-draft discard.

### The category rule

Any noun ending in **-ility, -age, -ance, -ence, -ity, -ment, -tion** that names a STATE rather than a CONCRETE thing or action gets flagged.

Examples that fail (state nouns):
- visibility, view, picture, lens, transparency
- coverage, posture, readiness, maturity
- governance, compliance, alignment
- determination, assessment, attestation, assurance
- automation, optimization, transformation
- documentation, evidence trail, audit lineage

Examples that pass (concrete nouns):
- spreadsheet, slide, report, file, checklist (named artifacts)
- hours, days, weeks (named time units)
- analyst, examiner, board, auditor, committee (named actors)
- HIPAA, NYDFS, SEC Item 1.05 (named regulations — ALWAYS unpacked on first use per Section H)
- audit, inspection, board meeting, renewal (named events)

### The replacement pattern

Whenever a banned-category noun shows up as the verb's object in the value sentence, replace with VERB + CONCRETE OBJECT:

| Banned-category | Replace with |
|---|---|
| "visibility into X" | "shows you which X are working and which are not" |
| "coverage of X" | "checks every day whether X is doing its job" |
| "evidence trail" / "audit lineage" | "keeps the paperwork your auditor will ask for in one place" |
| "readiness" / "maturity" | "tells you which of [N] controls you are passing today" |
| "compliance posture" | "lets you tell the auditor whether you are passing the rule today" |
| "automation of reporting" | "auto-generates the report your team is building by hand" |
| "governance trail" | "keeps the paper trail your board needs in one place" |

### Cross-reference to the failure-mode catalog

`cold-email-failure-modes.md` Failure 2 has more rewrite examples. Drafter scans against that list before saving.

---

## Section H — Plain-English Translation Rule

Every regulation, framework, or technical term cited in a cold email gets ONE plain-English unpacking on first use.

### The format

> [Regulation name] (the rule that [plain-English consequence in 5-12 words])

### Examples

- "SEC Item 1.05 (the rule that forces a public company to tell investors about a hack within 4 days)"
- "NYDFS Part 500 (New York's cybersecurity regulation for financial services companies, with a CISO-to-board annual report)"
- "HIPAA Security Rule NPRM (the proposed update to HIPAA that makes asset inventory and a 72-hour restoration plan mandatory)"
- "CMMC Phase 2 (the Pentagon's mandatory cybersecurity certification for defense contractors handling controlled data)"
- "GLBA Safeguards Rule (the FTC rule that requires a documented security program at any institution that handles consumer financial data)"

### Subsequent references

Once unpacked, you can use the bare regulation name in the rest of the email.

### When a regulation does NOT need unpacking

- The regulation IS the recipient's daily work and they would find unpacking patronizing. Apply judgment: a CISO at a public bank knows what Item 1.05 is. A new GRC director at a higher-ed shop may not be intimately familiar.
- Default: unpack on first use. Risk of patronizing < risk of losing the recipient.

### Maximum two regulations per email

Per the failure-mode catalog (Failure 3, regulation salad). If you need three, you have not selected the right spine pain — the spine is wrong.

---

## Section I — Voice Rule Pointers

Do not duplicate these rules here. Read the source files:

- **v2 cold email rules** (subject patterns, length, you/I ratio, banned phrases): `~/.claude/agents/onyxia-drafter.md` § "v2 Cold Email Rules"
- **Em-dash / "+" / abbreviations / 8th-grade level**: memory `feedback_drafter_v2_rules.md`
- **Banned mail-merge phrases (Register-B)**: memory `feedback_register_b_banned.md`
- **Zero HTML comments in body**: memory `feedback_no_html_comments_in_body.md`
- **Read every draft as the recipient**: memory `feedback_taste_over_rubric.md`
- **Mandatory sign-off block**: memory `feedback_email_signature.md` + Section K below
- **Forbidden words source of truth**: `~/ObsidianVault/50_Intel/product/forbidden-words.md`
- **Winning openers / Register-A anchors**: `~/ObsidianVault/50_Intel/product/winning-openers.md`
- **Power phrases / approved CTA variants**: `~/ObsidianVault/50_Intel/product/power-phrases.md`
- **Customer quotes (verbatim, never paraphrase)**: `~/ObsidianVault/50_Intel/product/quotes.md`
- **8-criteria rubric**: `~/ObsidianVault/50_Intel/methodology/draft-scoring.md`
- **Personas**: `~/ObsidianVault/50_Intel/personas/*.md`
- **Objections**: `~/ObsidianVault/50_Intel/methodology/objections.md`
- **Target titles canon**: `~/ObsidianVault/50_Intel/target-titles.md`
- **Pain Library**: `~/ObsidianVault/50_Intel/methodology/pain-library.md` (NEW, READ FIRST)
- **Cold-Email Canon**: `~/ObsidianVault/50_Intel/methodology/cold-email-canon.md` (NEW)
- **Cold-Email Failure Modes**: `~/ObsidianVault/50_Intel/methodology/cold-email-failure-modes.md` (NEW)

---

## Section J — Comprehension Test (REPLACES the old taste-read checkbox)

The drafter must WRITE FOUR ANSWERS in its return payload before saving any draft. Not check boxes. Write actual sentences. If the answers are vague or hedged, the email failed.

### The four required answers

```
comprehension_check:
  pain_in_one_sentence_15yo_gets: "<one sentence in plain English a 15-year-old understands>"
  onyxia_fix_in_one_sentence_15yo_gets: "<one sentence in plain English a 15-year-old understands>"
  what_recipient_does_after_reading: "<one sentence — reply to ask a question / forward to colleague / save for later / ignore>"
  plain_english_summary_of_email: "<2-3 sentences. If shorter or clearer than the email itself, the email failed.>"
```

### What "passes"

Each of the four answers must be:
- Concrete (uses concrete nouns and verbs, no abstract -ility / -ance / -ition nouns).
- Specific to THIS contact at THIS company (not pasteable to another contact by changing names).
- Plain English a 15-year-old gets on first read.

### What "fails" — auto-reject

Any of these = rewrite:
- Answer uses an abstract-category noun ("Onyxia provides visibility into X").
- Answer is generic ("Onyxia helps companies with cybersecurity").
- Answer is the email itself with the same words rearranged (not a clearer summary).
- Answer cannot be written without re-reading the email three times.
- "What the recipient does" answer is "ignore" or "delete" — that means the email failed.

### Why this works

The original "taste read" was a checkbox. The drafter ticked it without doing the actual taste read. Forcing the drafter to WRITE the four answers means the gate cannot be faked — either the drafter can write the answers in plain English, or it can't, and if it can't, the email is not clear enough.

### Worked example — what passes

**Email:** Marlon Clarke / Cross Country Healthcare (canon entry 2).

```
comprehension_check:
  pain_in_one_sentence_15yo_gets: "Marlon got a new boss yesterday and new bosses ask new questions about how the security team is doing."
  onyxia_fix_in_one_sentence_15yo_gets: "Onyxia helps Marlon's team save 160 hours a month so they have time to answer the new boss's questions instead of building reports by hand."
  what_recipient_does_after_reading: "Reply with 'sure, set it up' if interested, or with a date — the ask is one binary question."
  plain_english_summary_of_email: "Marlon, your new CIO Chris Tyrell will reset the board-reporting expectations fast. Another hospital saved 160 analyst hours a month with Onyxia. Our CEO Sivan was a CISO. Want me to set up a 20-minute call?"
```

All four pass: concrete, specific, plain English, and the summary is genuinely shorter than the email body.

### Worked example — what fails (and triggers rewrite)

**Email:** Sarepta / Mary Ballard original (failure 1 in failure-modes catalog).

```
comprehension_check:
  pain_in_one_sentence_15yo_gets: "Sarepta has FDA cybersecurity obligations and SEC Item 1.05 obligations." [FAIL — uses "obligations" twice, abstract noun, restates regulations not pain]
  onyxia_fix_in_one_sentence_15yo_gets: "Onyxia tracks control gaps and maintains evidence trails." [FAIL — banned-category abstract nouns "gaps" and "trails"]
  what_recipient_does_after_reading: "Probably skim and move on; nothing in the email is sharp enough to stop on." [FAIL — "ignore" outcome]
  plain_english_summary_of_email: "Sarepta makes a gene therapy drug. The FDA and SEC both regulate it. Onyxia tracks regulatory stuff." [FAIL — vaguer than the email itself, "regulatory stuff" is filler]
```

Three of four fail. Auto-reject. Rewrite using Pain #8 spine and the canon pattern.

---

## Section K — Mandatory Sign-Off Block (locked 2026-05-04)

Every email Miles sends ends with this exact four-line block. No exceptions, no shortened variants.

```
Cheers,
Miles Bastianich
Onyxia Cyber
203-524-8880
```

### Rules

- Four lines, in this order, on consecutive lines.
- Comma after `Cheers`.
- Full name on line 2 (`Miles Bastianich`, never `Miles` alone, never `Basti`).
- Company on line 3 (`Onyxia Cyber`, no abbreviation, no LLC, no Inc).
- Phone on line 4 (`203-524-8880`, hyphenated, no parentheses, no country code).
- ONE blank line above the block, separating it from the body.
- No additional text after the phone number. No tagline, no website, no LinkedIn, no calendar link, no PGP, no logo, no quote, no email-disclaimer.
- No P.S. between the body and the sign-off block. (P.S. allowed BEFORE the body close, never after.)

### Where this applies

Every email draft the drafter creates: cold first-touch (Email 1), cold follow-up (Email 2), Day-5 bumps, Day-12 breakups, post-meeting follow-ups, replies to inbound, event invites, warm intro follow-ups, holding replies during OOO, multi-thread referral asks, warm-revive singles.

### Where this does NOT apply

- LinkedIn connect notes (rules in `~/ObsidianVault/50_Intel/methodology/linkedin-outreach.md`)
- LinkedIn DMs
- Voicemail scripts
- SMS

### Drafter audit gate

Auto-reject any draft missing the block, with a wrong line, or with extra text after the phone number.

---

## Section L — Drafter Self-Check Before Saving

Run in this order. Any FAIL = rewrite. Same gate failing twice in a row = return research request to operator, do NOT third-attempt.

1. **Pain Selection triplet** (Section B): three lines written in payload, all three pass the contact-specific test.
2. **15-year-old gate** (Section A): value sentence passes the cab-driver test.
3. **Sequence default** (Section C): correct playbook (two-step sequence vs single-touch).
4. **Title-tier voice** (Section D): framing matches contact's tier.
5. **Tenure inflection** (Section E): anchor matches tenure class. Sub-12mo always Pain #4.
6. **Concrete-Noun Discipline** (Section G): zero state-nouns in -ility, -age, -ance, -ence, -ity, -ment, -tion as verb objects.
7. **Plain-English Translation** (Section H): every regulation cited is unpacked on first use. Maximum two regulations per email.
8. **Failure-mode catalog scan** (`cold-email-failure-modes.md`): zero hits against the 8 failure modes.
9. **All v2 hard gates** (em-dash, "+", abbreviations, banned phrases, 8th-grade level, you/I ratio, word count).
10. **HTML comments grep:** zero.
11. **Comprehension Test** (Section J): four written answers, all pass concrete + specific + plain-English checks.
12. **Sign-off block** (Section K): exact four lines, one blank line above, nothing after.

If all pass, save to Gmail Drafts.
