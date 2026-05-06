---
type: methodology
category: voice
status: canonical
last_updated: 2026-05-04
source: 35 drafts Miles discarded 2026-05-04 + the structural diagnosis that followed
applies_to: onyxia-drafter, onyxia-operator
purpose: Catalog of HOW cold emails fail despite passing structural rule audits. Drafter cross-references this BEFORE saving any draft. Each failure shows the original line, why it fails (pain library / canon citation), and the rewrite anchored on the correct spine pain.
---

# Cold-Email Failure Modes

Every entry below is a real draft from the 2026-05-04 discard batch. All 35 passed the 11-gate structural audit. Miles read them and threw them all out. The structural audit cannot catch these failures because they are failures of FRAMING, not of structure.

The drafter's pre-save process now includes: scan this catalog. If the draft you wrote resembles any failure mode here, rewrite using the rewrite pattern shown.

---

## Failure 1 — Regulation as the spine

The most common and most destructive failure. The drafter treats a regulation as the email's anchor and stacks regulatory shorthand. The reader cannot find the actual pain. The pain library never gets consulted because the regulation feels concrete enough.

### Original (Sarepta / Mary Ballard)

> Mary,
>
> Sarepta's ELEVIDYS gene therapy program is the first FDA-approved treatment for Duchenne. The sequences and protocols behind it are existential IP, and gene therapy delivery systems are in scope of FDA's September 2023 Cybersecurity Guidance for Medical Devices.
>
> Sarepta is also a NASDAQ registrant under SEC Item 1.05, which means a material incident triggers a 4-day disclosure clock.
>
> Onyxia tracks the control gaps across both FDA and SEC requirements and maintains the evidence trail for inspections and materiality determinations.

### Why it fails

- **Regulation salad.** Stacks four regulatory references in 80 words: "FDA-approved," "FDA's September 2023 Cybersecurity Guidance for Medical Devices," "NASDAQ registrant," "SEC Item 1.05." Each one carries jargon overhead. Together they're unreadable.
- **No spine pain selected from `pain-library.md`.** The actual spine here should be Pain #8 (IP / crown-jewel theft existential) — the recipe IS the company. The drafter never picked a pain. It picked regulations.
- **Value sentence uses banned-category abstract nouns.** "Control gaps," "evidence trail," "materiality determinations." Sibling-evasion of the small banned-noun list from the original style guide. The Concrete-Noun Discipline rule (Section J of the new style guide) catches this category-wide.
- **No Pattern Statement.** Canon examples all have a Pattern Statement in sentence 3 ("quiet killer," "different animal," "concrete number"). This email has none. It just lists facts.
- **No customer quote.** Canon examples for any IP-sensitive contact would land the Hashal Mehta "intuitive" quote or build a fresh peer-CISO line. This email substitutes Sivan as a feature description ("Onyxia tracks...") instead of a peer credibility line ("Sivan was a CISO").
- **15yo cannot answer "what hurts" or "what does Onyxia do."**

### Rewrite (anchored on Pain #8 — IP existential)

> Mary,
>
> Sarepta's ELEVIDYS is the first FDA-approved gene therapy for Duchenne. The protocols behind it are not interchangeable with anyone else's IP. Lose the recipe to a hack and there is no rebuild.
>
> Sivan Tehila, our CEO, was a CISO. The Stack Map shows you which of your tools are actually protecting the systems holding the gene therapy data, separate from everything else in your stack. You see what is covered and what is exposed in 30 minutes, not 30 days.
>
> Worth 20 minutes the week of 5/19 to put your IP-sensitive systems on the map?
>
> Cheers,
> Miles Bastianich
> Onyxia Cyber
> 203-524-8880

### Why the rewrite works

- **Spine pain named in plain English in sentence 2.** "Lose the recipe to a hack and there is no rebuild" is Pain #8 in 12 words. A 15yo gets it.
- **Pattern Statement.** "The protocols behind it are not interchangeable with anyone else's IP." Miles voice. Memorable.
- **Cameo regulation = ZERO.** No FDA, no SEC, no Item 1.05 mentioned. They are not the spine; they are not the pain. They are removed.
- **Sivan one sentence.** "Sivan Tehila, our CEO, was a CISO." That's the credibility line.
- **Onyxia-response in plain English.** "Stack Map shows you which of your tools are actually protecting the systems holding the gene therapy data" + "in 30 minutes, not 30 days." Verb + concrete object + concrete time savings.
- **Peer-framed ask.** Specific timeframe (week of 5/19), specific feature ("put your IP-sensitive systems on the map").
- **Sign-off block.**

---

## Failure 2 — Abstract-noun siblings (sibling-evasion of the banned list)

The original style guide had a small banned-noun list: "control coverage," "governance trail," "posture," etc. The drafter learned the LIST and then used SIBLINGS of the same banned category. "Control gaps" instead of "control coverage." "Evidence trail" instead of "governance trail." Same pattern, different surface tokens. The category-based Concrete-Noun Discipline rule catches sibling-evasion.

### Original (Columbia Banking / Christine Eagan, value sentence from earlier draft)

> Onyxia provides continuous governance trail visibility so your ERM function can demonstrate cybersecurity program posture to the board and satisfy SEC Item 1.05 materiality disclosure requirements without manual evidence assembly.

### Why it fails

- 38 words. One sentence.
- Three abstract nouns chained: "governance trail visibility" / "cybersecurity program posture" / "materiality disclosure requirements without manual evidence assembly."
- "Demonstrate" is an abstract verb. "Provide" is the limpest verb in the language. Together they say nothing.
- A 15yo reads it and knows: Onyxia provides something so something can demonstrate something.

### Rewrite (anchored on Pain #3 — board-ready when something happens)

Sentence 3-4 of an ERM-aimed cold:

> Sivan Tehila, our CEO, was a CISO. The Board Reporting feature pulls real numbers from your existing tools and builds the cyber section of your audit committee pack in one click. Your team is not assembling it the night before the meeting.

### Why the rewrite works

- "Pulls real numbers from your existing tools" — concrete verb (pulls) + concrete object (real numbers from your existing tools).
- "Builds the cyber section of your audit committee pack in one click" — concrete action + concrete output + concrete time.
- "Your team is not assembling it the night before the meeting" — concrete waste avoided. A 15yo gets it.
- Zero abstract nouns from the banned category.

### General sibling-evasion rule

If the noun in your value sentence ends in -ility, -age, -ance, -ence, -ity, -ment, or -tion AND describes a state rather than a concrete thing or action, replace it with a verb-object pair. Examples:

| Banned (any sibling) | Replace with |
|---|---|
| visibility / view / picture into X | "Onyxia shows you which X are working and which are not" |
| coverage / coverage gaps / control gaps / posture | "Onyxia checks every day whether your security tools are doing their job" |
| trail / record / lineage / documentation | "Onyxia keeps the paperwork your auditor / board / GC will need in one place" |
| evidence / attestation / assurance | "Onyxia produces the report your auditor is going to ask for, before they ask" |
| readiness / maturity / preparedness | "Onyxia tells you which of [N] controls you are passing today, and which you are not" |
| automation of X | "Onyxia does X automatically" or "Onyxia removes [N] hours of [Y] work per month" |
| determinations / assessments / determinations | "Onyxia tells you whether [specific thing] is true today" |

---

## Failure 3 — Regulation salad

Stacking 3+ regulations in one email so that the recipient can't decode any of them. Caused by drafter trying to look thorough. Often appears alongside Failure 1 (regulation as spine).

### Original (Augusta University / Heather Roszkowski)

> Heather,
>
> Augusta University is one of the few institutions carrying both GLBA Safeguards and HIPAA Security Rule obligations simultaneously. The HIPAA NPRM finalization in May removes the addressable/required distinction and mandates MFA, asset inventory, and 72-hour restoration. The FTC's updated GLBA Safeguards rule is already in force.
>
> Two federal frameworks, one security program, one audit cycle at a time.

### Why it fails

- Six regulatory references in 60 words: GLBA Safeguards, HIPAA Security Rule, HIPAA NPRM finalization, addressable/required distinction, MFA / asset inventory / 72-hour restoration mandates, FTC's updated GLBA Safeguards.
- "Addressable/required distinction" is jargon a 15yo cannot decode.
- The Pattern Statement at the end ("Two federal frameworks, one security program, one audit cycle at a time") is actually OK. It buries underneath the regulatory salad.

### Rewrite (anchored on Pain #5 — multi-framework reconciliation)

> Heather,
>
> Augusta University runs HIPAA on the medical-school side and GLBA Safeguards on the financial-aid side. Same security stack underneath. Two audits, two formats, one team rebuilding the spreadsheet for each.
>
> A healthcare CISO at a 13,000-employee system told us: "With Onyxia, we are able to save at least 160 working hours a month that one full-time analyst would traditionally spend on manual reporting."
>
> Sivan Tehila, our CEO, was a CISO. The Framework Compliance Dashboard maps your existing controls to whichever framework the auditor is asking for. One control set, two framework views, one click.
>
> Want me to walk through it against your next audit?
>
> Cheers,
> Miles Bastianich
> Onyxia Cyber
> 203-524-8880

### Why the rewrite works

- Two regulations cited (HIPAA, GLBA), each in one short clause naming WHERE in her org they apply (medical-school side, financial-aid side). Localizes the abstract.
- Pattern Statement in plain English, sentence 3: "Two audits, two formats, one team rebuilding the spreadsheet for each." 15yo gets it.
- Customer quote verbatim. Profile-match (healthcare CISO, 13,000 employees) lands for an academic medical center.
- Sivan one sentence.
- Onyxia-response with concrete output (one control set, two views, one click).

### Regulation-cameo rule

When you must reference a regulation, follow these rules:
1. **One regulation per sentence.** Two regulations means two sentences, each localized to where in their org the regulation applies.
2. **Maximum two regulations per email** total. If you need three, you have not selected the right spine pain — Pain #5 is your spine, and the email should anchor there in plain English.
3. **First reference unpacked.** "SEC Item 1.05 (the rule that forces a public company to tell investors about a hack within 4 days)." Subsequent references can be naked.
4. **Skip the regulatory mechanics jargon.** "Addressable/required distinction." "72-hour restoration objective." "Annual asset inventory mandate." All of this is INTERNAL FDA / HHS process. The recipient does not need it. Cut.

---

## Failure 4 — Pattern Statement absent

Canon entries 1-7 all have a Pattern Statement in sentence 3 (the line that names the pain in the recipient's own language: "quiet killer," "different animal," "concrete number," "three audits three formats one team"). When this is missing, the email is a string of facts with no central frame. The reader sees data, not pain.

### Original (Gundersen / Kari Adank)

> Kari,
>
> The HIPAA Security Rule NPRM is targeted for May 2026 finalization. When it lands, the addressable/required distinction goes away and asset inventory plus an updated network map become mandatory requirements, not optional ones. For a seven-hospital, 65-clinic system that absorbed Bellin in 2022, that is a large distributed surface to document.
>
> Onyxia tracks whether each HIPAA control is working across all your facilities every day, so your team is not rebuilding the evidence file from scratch when OCR comes knocking.

### Why it fails

- Sentences 1 and 2 are regulatory mechanics ("addressable/required distinction goes away," "asset inventory plus an updated network map become mandatory requirements, not optional ones"). Jargon stack.
- Sentence 3 ("a large distributed surface to document") is the closest thing to a Pattern Statement, but it is buried at the end of paragraph 1 and uses "surface to document" — abstract.
- No customer quote.
- No Sivan line.
- The Onyxia-response line is OK but weakened because the email never named the pain in plain English.

### Rewrite (anchored on Pain #5 — multi-framework / multi-site evidence collection)

> Kari,
>
> Gundersen runs HIPAA across seven hospitals, 65 clinics, and the Bellin sites you absorbed in 2022. Same audit, eight different campuses producing the same evidence in slightly different formats. Your team rebuilds the file every cycle.
>
> A CISO at a 13,000-employee multi-region health system told us: "With Onyxia, we are able to save at least 160 working hours a month that one full-time analyst would traditionally spend on manual reporting."
>
> Sivan Tehila, our CEO, was a CISO. The Framework Compliance Dashboard pulls HIPAA evidence from each campus's tools into one view, and rebuilds it as the rule changes.
>
> Worth 20 minutes the week of 5/19 to walk through it against the OCR audit cycle?
>
> Cheers,
> Miles Bastianich
> Onyxia Cyber
> 203-524-8880

### Why the rewrite works

- **Pattern Statement, sentence 2:** "Same audit, eight different campuses producing the same evidence in slightly different formats. Your team rebuilds the file every cycle." Names her pain. 15yo plain English.
- HIPAA cited once, naked, no addressable/required mechanics.
- Customer quote with profile match.
- Sivan one sentence.
- Onyxia-response: concrete verb (pulls) + concrete object (HIPAA evidence from each campus's tools) + concrete benefit (one view).

### General Pattern Statement rule

Every cold email has a Pattern Statement. It sits in sentence 3 (after the trigger). It names the pain in the recipient's language. It is memorable, often slightly blunt. Examples from canon:

- "Reporting-layer burden is the quiet killer for CISOs at your scale." (Pain #1)
- "New-CIO windows reset the board-reporting expectations in a hurry." (Pain #4)
- "Moving from GRC at Fidelity to owning the full security program at an $84B-asset bank is a different animal." (Pain #4)
- "$5M is a concrete number for the board to hold against whatever security investment comes next." (Pain #3)
- "Two security stacks under one team, with overlap nobody fully mapped yet and gaps nobody owns yet." (Pain #2)
- "Three audits, three formats, one team rebuilding the spreadsheet from scratch each cycle." (Pain #5)

If your draft does not have a sentence that reads like one of these, write one. If you cannot, you have not picked the right spine pain.

---

## Failure 5 — Tenure cited without pain anchor

The drafter learned to mention tenure ("six months in," "ten months into the role"). It treats tenure as a personalization token. But tenure only matters if it's anchored to Pain #4 (new-leader inheritance) or used as a tone modulator. When tenure is cited alongside a different spine pain, it reads as random.

### Original (Lantheus / Robert Sherman, Email 1)

> Robert,
>
> Lantheus's radiopharmaceutical delivery systems put your program in scope of FDA's September 2023 Cybersecurity Guidance for Medical Devices. That guidance requires a documented cybersecurity plan, SBOM, and vulnerability management evidence for premarket submissions.
>
> Lantheus is also a NASDAQ registrant under SEC Item 1.05, which means a material incident triggers a 4-day disclosure clock.
>
> Sixteen months in, both obligations landed on your desk within six months of your start.
>
> Onyxia maps the control gaps across both FDA and SEC requirements, so you know where you stand before an inspection or an incident.

### Why it fails

- Same regulatory salad as Failure 1 (FDA + SEC + Item 1.05 + SBOM + premarket submissions).
- "Sixteen months in" — tenure cited, but the email's spine is regulation, not new-leader. Tenure here is decorative.
- No customer quote, no Sivan line.
- Value sentence has the banned-noun sibling "control gaps."

### Rewrite (anchored on Pain #4 — new-leader inheritance, with regulation cameo)

> Robert,
>
> Sixteen months into the CISO seat at Lantheus is the moment the board starts asking what shape the program is in. Inheriting a public-company security stack under FDA scrutiny is not a 9-month research project; the answer needs to be ready now.
>
> Sivan Tehila, our CEO, was a CISO. The CPI Library gives you a clean baseline of your program in 30 days against the controls FDA inspectors and your audit committee actually look at. You walk into the next board prep with a real number, not a hand-built slide.
>
> Worth 20 minutes the week of 5/19 to compare notes with someone who navigated this moment?
>
> Cheers,
> Miles Bastianich
> Onyxia Cyber
> 203-524-8880

### Why the rewrite works

- **Spine = Pain #4.** Tenure ("sixteen months in") is the trigger AND the spine, not decoration.
- **Pattern Statement, sentence 2:** "Inheriting a public-company security stack under FDA scrutiny is not a 9-month research project; the answer needs to be ready now." 15yo gets it.
- **Regulation cameo:** "FDA scrutiny" mentioned in one clause. No SEC, no Item 1.05, no SBOM. The email is about the new-leader moment; the regulation is the supporting pressure.
- **Sivan + concrete capability:** "CPI Library gives you a clean baseline of your program in 30 days." Verb + object + time.
- **Peer-framed ask:** "compare notes with someone who navigated this moment" — the Sivan peer-call frame.

### Tenure rule

- **Tenure is the spine** when contact is under 12 months in role → Pain #4 → tenure is the trigger and the framing.
- **Tenure is a tone modulator** otherwise (mature-program → peer register; scaling → integration register).
- **Never cite tenure as a decoration.** "Six months in, both obligations landed on your desk" is decoration if the email is about FDA and SEC, not the new-leader moment.

---

## Failure 6 — Soft close used as the entire close

The new style guide added Email 1 (informative, soft close) as a default. The drafter started writing soft closes for emails that ALSO had no Sivan line, no customer quote, and no pain anchor. The soft close became the default exit ramp for a weak email.

### Original (Augusta University / Heather Roszkowski, Email 1)

> Onyxia tracks whether your controls are meeting both framework baselines simultaneously, so you are not running two separate evidence tracks manually.
>
> Worth having on your radar.

### Why it fails

- The Onyxia-response sentence does the entire job (states what Onyxia does and what waste it avoids).
- The soft close ("Worth having on your radar") is fine as a soft close.
- BUT the email skipped the Sivan line, the customer quote, and the pattern statement. So the soft close ends an email that never built credibility. The recipient has no reason to remember Miles by Friday.

### Rewrite

The fix is not to add a hard ask to a weak email. It's to put the credibility-building elements back in. The earlier rewrite for Failure 3 (Augusta University) shows the full-credibility version with quote + Sivan + Pattern Statement. Soft close is fine when the body is loaded; the body has to actually be loaded.

### Soft-close rule

A soft close ("Sharing in case it helps." / "Worth having on your radar." / "Putting it on your screen, not your calendar.") is appropriate ONLY when the email body has done its job: a concrete trigger + a Pattern Statement + a customer quote OR Sivan line + a plain-English Onyxia-response. The soft close trades the meeting ask for trust-building. It only works when the trust-building is actually present.

If the body is thin, do not paste a soft close. Either load the body or write Email 2 with a real ask.

---

## Failure 7 — Stacked Onyxia capabilities

The drafter learned to mention multiple Onyxia features in one email, on the theory that "more features = more value." The opposite is true. Stacking features dilutes the central pain. The reader cannot remember what Onyxia DOES, only that Onyxia does several things.

### Original (Kaman Corporation / Eunice Clark, Email 1)

> Onyxia scores Kaman's CMMC Level 2 controls today so your team knows exactly which gaps to close before the C3PAO assessor arrives, rather than finding out during the audit.

### Why this is OK on its own (it is)

This sentence is actually fine. It uses one capability (CPI scoring against CMMC Level 2), one concrete waste avoided (finding out during the audit), and the verb is concrete. It would pass the 15yo gate.

### Where it fails (the EARLIER drafts)

In an earlier round, the drafter wrote: "Onyxia delivers continuous CMMC control coverage visibility so your IT team can track Level 2 readiness posture without building the compliance infrastructure from scratch." Three capabilities ("continuous coverage visibility" + "track readiness posture" + "compliance infrastructure"), zero concrete actions, three abstract nouns.

### Capability rule

ONE Onyxia capability per cold email. Pick the capability that maps to the spine pain. From `features.md`:

| Spine pain | Default capability to lead with |
|---|---|
| #1 Manual reporting | Automated Board & Executive Reporting (one-click report) |
| #2 Tool sprawl | Stack Map (auto-renders in 30 minutes) |
| #3 Board-ready when something happens | Board Reporting + Framework Compliance Dashboard |
| #4 New-leader inheritance | CPI Library (clean baseline in 30 days) |
| #5 Multi-framework reconciliation | Framework Compliance Dashboard (one-click overlay) |
| #6 Continuous truth | CPI Library (continuous monitoring with SLAs) |
| #7 Lean team | Automated Board Reporting + 160-hour quote ROI math |
| #8 IP existential | Stack Map (asset-type axis) + CPI Library customizable |

Don't stack. Pick one.

---

## Failure 8 — "Recently" without a date

When you write "Recently your company announced X," the recipient cannot tell whether you read the news yesterday or six months ago. Concrete dates land. "Recently" is filler.

### Original (a CSAA-style draft)

> CSAA Insurance recently expanded its digital quote experience.

### Why it fails

- "Recently" is undated. The recipient cannot verify Miles read this news.
- "Expanded its digital quote experience" is corporate-comms language, not Miles voice.

### Rewrite

> CSAA's API-driven quote channel went live in [Q1 2026]. Underwriters competing on speed mean the security surface grew that month.

### Date rule

Every concrete trigger sentence has a date or a quarter. "Yesterday." "Last Tuesday." "April 24." "Q1 2026." "September 2023." If you do not know the date, you do not have a verifiable trigger; pick a different one.

---

## How drafter cross-references this catalog

Pre-save step (now in `email-style-guide.md` Section G):

For each draft, scan against the eight failure modes above. For each one, ask:

1. **Failure 1 (regulation as spine):** Did I select a spine pain from `pain-library.md`? Or did I anchor on a regulation? If I anchored on a regulation, rewrite with the spine pain.
2. **Failure 2 (abstract-noun siblings):** Does the value sentence use any noun ending in -ility, -age, -ance, -ence, -ity, -ment, -tion that names a state instead of a concrete action or thing? If yes, rewrite with verb-object.
3. **Failure 3 (regulation salad):** Are there 3+ regulatory references in the email? If yes, the spine is wrong; rewrite from a non-regulatory pain anchor.
4. **Failure 4 (no Pattern Statement):** Is there a sentence 3 that names the pain in plain English in the recipient's language? If no, write one.
5. **Failure 5 (tenure decoration):** Is tenure cited? If yes, is the spine Pain #4 (new-leader)? If no, rewrite — either change the spine to #4 or remove the tenure mention.
6. **Failure 6 (soft close on a thin body):** If the close is soft, does the body have all four elements: trigger + Pattern Statement + (Sivan or customer quote) + plain-English Onyxia-response? If any are missing, load the body before keeping the soft close.
7. **Failure 7 (stacked capabilities):** Is exactly ONE Onyxia capability mentioned, and does it match the spine pain per the table above?
8. **Failure 8 (undated trigger):** Does the trigger sentence have a date or quarter? If no, find one or pick a different trigger.

If any of the eight catches a hit, rewrite once. If a second rewrite still hits, return research request to the operator.
