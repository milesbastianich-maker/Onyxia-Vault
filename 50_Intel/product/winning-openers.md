---
type: intel
subtype: product
topic: winning openers
source: HubSpot engagements across 23 closed-won deals, pulled 2026-04-21
status: live
created: 2026-04-22
updated: 2026-04-21
tags: [intel, product]
---

# Winning Openers

Verbatim openers from outbound threads associated with Onyxia's 23 closed-won deals. Extracted 2026-04-21 via HubSpot `search_crm_objects` + `get_crm_objects` on `hs_email_html`.

## The honest finding

**Most closed-won deals did not close off a cold opener.** Of 23 deals pulled:

- 8 deals have ZERO email engagement logged in HubSpot (Summit Utilities, Orange County Transit, Gaia Real Estate, Silverstein, Adama, Alchemy Tech Group, Consortium Networks, World Wide Technology). These deals were either logged separately, won via direct Calendar / call flow, or partner-sourced without CRM email capture.
- 11 deals have email threads that begin with a meeting follow-up subject ("<> Onyxia Follow up", "Meeting follow up", "Thank you & Next Steps", "Quote for X"). The cold-outbound predecessor is not in HubSpot or does not exist.
- 4 deals (Centra, Simpson Thacher, Radiant Logic, Millennium Print) closed off inbound or warm-intro starts.
- 2 deals (CWT, Chipotle) show genuine cold-outbound emails from the Onyxia team in HubSpot. Those are the only true cold openers in the corpus.

**Implication for Miles.** The "23 closed-won openers" corpus is mostly post-meeting follow-up language, not cold-email hook language. Cold-email patterns need to be sourced from Miles's own outbound history (which has ZERO direct wins in HubSpot yet — see closed-won-patterns.md) plus the two verbatim Yosef + Sivan cold openers captured below plus inferred structure from the closed-won-patterns.md win-pattern analysis.

---

## The two verbatim cold openers

### 1. Yosef Adatto — CWT — "SEC Inquiry" (2023-12-21)

Deal closed at $100K (corporate travel, CWT is public). First cold outbound. Subject line is 2 words, regulation-timed (SEC cybersecurity rules enacted 2023-12-18, so this hit 3 days after the rule dropped). Framing: value-first, no ask. Checklist PDF as the value vehicle. Reply line was a second send 7 days later, then deal advanced months later through separate motion.

**Subject:** `SEC Inquiry`

**Body (verbatim):**

> Hi Harshal,
>
> I hope you are using this time for some well deserved R&R.
>
> I wanted to share a resource with you for the upcoming SEC regulations enacted on December 18th. It contains a guide for how to ensure you maintain compliance and a checklist for what to do if your organization encounters a potential incident, and the actions you can take.
>
> Originally the team and I created this resource for our public enterprise customers to be a companion piece for our platform that continuously monitors, measures, and communicates the value of their security program to the business through AI and automation.
>
> I wanted to share it with you with zero upfront ask to see if it can provide value.
>
> You can read the checklist here: [SEC Checklist PDF]
>
> Don't like clicking links? I'd be happy to show it to you when timely and relevant.
>
> Looking forward,
> Yosef

**Structural pattern:**
1. Regulation-timed hook (SEC rule just enacted) → reason to open.
2. Resource offered with zero-ask, one sentence describing it concretely.
3. "Originally created for our public enterprise customers" → implied social proof without naming logos.
4. Single low-friction CTA with a link-out option.
5. Sign off, first name only.

### 2. Sivan Tehila (CEO) — CWT — "Can We Help With Your Q2 Cybersecurity Reporting?" (2024-06-20)

Six months after the Yosef touch. CEO-as-former-CISO outreach. Quarter-end reporting timing. Still value-framed. Deal advanced after this.

**Subject:** `Can We Help With Your Q2 Cybersecurity Reporting?`

**Body (verbatim):**

> Hi Harshal,
>
> For CISOs and security leaders, time is of the essence when it comes to preparing for executive and board presentations and making sure you convey the business impact of your team's cybersecurity efforts.
>
> As a former CISO, this was a key part of my inspiration for creating Onyxia, a new solution designed to help CISOs manage and communicate the value of their cybersecurity initiatives in a more efficient and data-driven way. Our platform automates time-consuming program reporting in a matter of clicks and provides a customizable approach that integrates with your existing security stack.
>
> With Q2 coming to a close, can you join me for a brief 30-minute call to explore the reporting challenges you face and how we can help alleviate them with our platform?
>
> If so, please feel free to let me know what day/time is most convenient for you or pick a time here: [Find Time]
>
> Thank you for considering this opportunity. I look forward to the possibility of collaborating with you!
>
> Best,
> Sivan Tehila
> CEO & Founder, Onyxia Cyber

**Structural pattern:**
1. Seasonal forcing function (Q2 close, board reporting season).
2. "As a former CISO" → peer credibility in sentence 1 of para 2. This is the load-bearing line.
3. Product-named + concrete capability ("automates time-consuming program reporting in a matter of clicks").
4. 30-minute ask, framed as "can you join me," personal not template.
5. CEO signature.

**Adaptation for Miles:** The CEO-peer structure is Miles's highest-fidelity template. Replace the "As a former CISO" with Miles's Sivan-as-peer anchor from `40_Plays/sivan-peer-intro.md`. Keep the seasonal/forcing-function opener. Shorten to under 80 words per `feedback_email_engine.md`.

---

## Post-meeting follow-up subjects that held through to close

These are NOT cold openers, but they are the subject-line conventions of threads that converted. Useful for the sequence stage where a meeting has happened and the follow-up needs to stay scannable and reply-able.

| Deal | Owner | Subject | Vertical |
|---|---|---|---|
| WellStar | Brian Fisher | `Wellstar <> Onyxia Follow up` | Healthcare |
| CCC | Brian Fisher | `CCCIS <> Onyxia Follow Up` | InsurTech |
| Millennium Print | Brian Fisher | `Millennium Print Group <> Onyxia: Follow up` | Manufacturing |
| Port Authority | Maura Clancy | `Onyxia Cyber: Thank you & Next Steps with PANYNJ` | Transit |
| Premera | Brad Baldelli | `Onyxia & Premera - meeting follow up` | Health Insurance |
| Radiant Logic | Brad Baldelli | `Radiant Logic & Onyxia - meeting follow up` | Identity |
| Vista Equity | Brad Baldelli | `Onyxia & Vista Equity - meeting follow up` | PE |
| Elite Technology | Brad Baldelli | `Onyxia Cyber: Scheduling POC` | SaaS |
| Christiana Care | Yosef Adatto | `Board Meeting - Today` → `Close more gaps` | Healthcare |

**Pattern:** `{Account} <> Onyxia {stage}` is Brian Fisher's convention. `Onyxia & {Account} - {stage}` is Brad's. `Onyxia Cyber: {action} with {Account}` is Maura's. Short, scannable, repliable. No hooks, no jargon, no pitch.

---

## Verbatim follow-up opener (Brian Fisher, CCC Intelligent Solutions)

First-message body after intro meeting. Same pattern Brian used at WellStar, Millennium Print, Bausch + Lomb. All four closed.

> Hey Kyle,
>
> It was great meeting you and thank you for taking the time to speak. We appreciate the feedback and look forward to speaking on Thursday.
>
> Below I've attached our current CPI's and integrations so you can see what can be deployed right out of the box. On our next call we are happy to dive into how our Ai will work as well as other roadmap items we have in the pipeline.
>
> In the meantime if you have any additional questions please feel free to reach out and we will be glad to be of help
>
> All the best,
> Brian

**Pattern for Miles's use:** short, warm, one concrete attachment, one forward-commit reference ("looking forward to speaking on Thursday"). Zero jargon. Under 80 words. This is the post-discovery template.

---

## Patterns observed

1. **Cold openers in the winning corpus are rare and regulation-timed.** Both verbatim cold emails (Yosef + Sivan) pegged to a forcing function — SEC rule enactment, board-reporting quarter-end. No "hope this finds you well" openers in anything that closed.
2. **CEO/founder cold outbound converts differently than rep cold outbound.** Sivan's cold email reads as peer-to-peer CISO. A rep saying the same thing reads as a vendor pitch. For any Sivan-fronted send, the CEO-as-former-CISO line is the lead sentence.
3. **Post-meeting follow-up pattern is consistent:** `{Account} <> Onyxia {stage}` subject + under-80-word body + one concrete attachment or next-step reference. No feature dumps.
4. **"Zero upfront ask" language works** when paired with a specific resource. Yosef's SEC checklist was the mechanism, not the copy. The copy just got out of the way.
5. **Follow-up second-touch usually changes subject.** Yosef's CWT thread: `SEC Inquiry` → `Metrics that Matter to your board` → `BI BI Power BI Metrics Templates` → `Can We Help With Your Q2 Cybersecurity Reporting?`. Subject churn is part of the motion, not a signal of failure.
6. **Eight of 23 wins have zero email engagement logged.** The vault cannot claim "email drove the deal" for those. Likely drivers: peer intros, RSAC / BlackHat in-person, partner referrals, Calendar-direct. This is an operational gap to fix in HubSpot logging, not a copy insight.

---

## How to use this file

1. **For cold outbound:** use the Sivan CEO structure as the Sivan-peer-intro template (`40_Plays/sivan-peer-intro.md`). Use the Yosef SEC structure for regulation-timed hooks (8-K, HIPAA NPRM, CMMC, DORA, NYDFS).
2. **For post-meeting follow-up:** use the Brian Fisher structure. `{Account} <> Onyxia Follow up` subject, <80 words, one concrete artifact, one forward commit.
3. **For multi-touch sequences:** rotate subjects on touches 2, 4, 7, 14. See `40_Plays/sequences/` and the subject-rotation pattern above.
4. **Quote verbatim, never paraphrase.** Both opener bodies are linked from every `tpl-*-cold.md` template.
5. **If you want a winning opener for a vertical not represented above, say so.** Do not fabricate. Example: there are NO winning openers in this corpus for retail QSR outbound (Chipotle closed via walnut.io demo-request reply, not cold). Flag vault-silent.

---

## Extraction methodology (for future re-pulls)

1. `mcp__claude_ai_HubSpot__search_crm_objects` with `objectType: emails`, `associatedWith.objectType: deals`, `objectIdValues: [deal_id]`, sort ASC by `hs_timestamp`. Filter `hs_email_direction = EMAIL` for outbound.
2. First outbound in a thread that has a same-thread `INCOMING_EMAIL` reply = candidate winning opener.
3. `mcp__claude_ai_HubSpot__get_crm_objects` with property `hs_email_html` (NOT `hs_email_text` — that property does not exist on this instance).
4. Strip HTML → text → first paragraph.
5. Note: `hs_email_html` is populated only on outbound emails. Inbound customer replies do not expose body text via this MCP. For inbound-originated wins (e.g., Centra), opener is the Onyxia reply, which reads "Thank you for reaching out..." — not a cold hook.

---

## Gaps to fill next session

- ~~Miles Gmail sent folder pull~~ — **done this session**. See "Miles's own cold-email corpus" section below.
- Log the 8 zero-engagement wins manually so the vault knows what closed them (peer intro, RSAC, partner referral, etc.). Decision for Miles: is it worth the backfill?
- Pull the Chipotle walnut.io demo-request thread to understand the inbound flow that converted.
- Confirm with Maura, Brad, Brian, Yosef whether any cold outbound was sent via a non-HubSpot tool (Apollo, Outreach) and thus missing from this corpus.

---

## Miles's own cold-email corpus (pulled 2026-04-22, Gmail sent, 90d)

Miles has sent 50+ personalized cold outbound in the last 24 hours. Distinct voice from the Maura/Brad/Sivan/Brian corpus. Two registers:

- **Register A — high-fidelity personalized.** First-name-first opener, concrete company fact in sentence 1 (exact employee count, recent news, settlement amount, role transition), Miles signature prose, verbatim 160-hour customer quote, peer-call CTA.
- **Register B — template sequences.** "[Name] — [hook] @ [Company]" subject, casual "Hi/Hey" open, templated problem frame, lower fidelity but high volume. Uses em dashes.

**Voice-rule note:** The no-em-dashes rule in `forbidden-words.md` applies to agent-written drafts. Miles himself uses em dashes in his own prose. Leave both in place — the rule targets AI tells, not Miles's natural voice.

### Four verbatim Register-A openers (healthcare + fins)

**1. Andrew Puller — MedStar — Subject: `160 hours a month`**

> Andrew,
>
> Reporting-layer burden is the quiet killer for CISOs at your scale. One of our healthcare customers (13,000+ employees, multi-region) put it this way:
>
> "With Onyxia, we are able to save at least 160 working hours a month that one full-time analyst would traditionally spend on manual reporting and instead, focus more time on our actual risk management strategy."
>
> Sivan Tehila, our CEO, was a CISO before building this.
>
> Worth 15 minutes next Tuesday or Thursday to compare notes?
>
> Miles Bastianich
> Onyxia Cyber

**2. Megan Marshall — Medusind — Subject: `after the settlement`**

> Megan,
>
> Saw the final settlement payout went out on the 10th. $5M is a concrete number for the board to hold against whatever security investment comes next.
>
> Our CEO Sivan Tehila is a former CISO. She built Onyxia so that GCs and CISOs at healthcare orgs can share one real-time picture of risk, and auto-generate the board reporting that gets asked for after an incident like this. Your team at Medusind is already working with our side on the CISO track.
>
> Worth a short call to compare notes on what post-settlement reporting looks like in your board packet?
>
> Miles Bastianich
> Onyxia Cyber
> 203-524-8880

**3. Marlon Clarke — Cross Country Healthcare — Subject: `Chris Tyrell's first 90 days`**

> Marlon,
>
> Saw the announcement on Chris Tyrell joining as CIO yesterday. New-CIO windows reset the board-reporting expectations in a hurry.
>
> A healthcare CISO at a 13,000-employee system told us:
>
> "With Onyxia, we are able to save at least 160 working hours a month that one full-time analyst would traditionally spend on manual reporting and instead, focus more time on our actual risk management strategy."
>
> Our CEO Sivan Tehila is a former CISO. She does a 20-minute peer call with folks navigating moments like this. Not a demo.
>
> Want me to set it up?
>
> Miles Bastianich
> Onyxia Cyber

**4. Leilani Farol — First Horizon Bank — Subject: `the first 90 days at First Horizon`**

> Leilani,
>
> Congrats on the CISO role at First Horizon. Moving from GRC at Fidelity to owning the full security program at an $84B-asset bank is a different animal — especially with SEC cyber disclosure rules tightening the reporting window.
>
> Sivan Tehila, our CEO and former CISO, built Onyxia specifically for this moment: normalizing data across the existing stack and auto-generating board-ready compliance reporting so your team isn't burning cycles on it manually.
>
> Curious if that's on your radar as you're setting strategy?
>
> Miles Bastianich
> Onyxia Cyber
> 203-524-8880

### Miles Register-A structural pattern

1. **Sentence 1:** First-name-only open. No "Hi," no "Hope you're well." Just `<First>,`.
2. **Sentence 2 (the hook):** Concrete fact about their company. Settlement amount + date. Exact employee count. Recent announcement. Role transition with specific prior role. Never generic.
3. **Sentence 3 (pattern statement):** A Miles signature framing that lands the problem: "Reporting-layer burden is the quiet killer for CISOs at your scale." / "New-CIO windows reset the board-reporting expectations in a hurry." / "Moving from X to Y is a different animal."
4. **Verbatim customer quote** (block-quote formatted) — the 160-hours line, every time, for healthcare. First sentence of the quote block identifies the customer's profile ("healthcare CISO at a 13,000-employee system").
5. **Sivan-as-former-CISO line.** Single sentence. "Sivan Tehila, our CEO, was a CISO before building this." or "Our CEO Sivan Tehila is a former CISO."
6. **CTA.** Peer-call framing ("compare notes," "20-minute peer call") OR curiosity-check ("Curious if that's on your radar"). "Want me to set it up?" is a strong single-sentence CTA variant.
7. **Signature:** `Miles Bastianich / Onyxia Cyber` + phone number (203-524-8880) when the CTA is high-commitment.

### Miles Register-B subject-line taxonomy

`<First Name> — <hook> <verb> <Company>`. Seven observed hooks, all used as named sequences:

| Hook | When used | Example |
|---|---|---|
| "a map for the security stack" | tool-sprawl targets, SaaS/mid-market | Brian — a map for the security stack |
| "CPM for <Company>" | financial services | Kevin — CPM for Daybright Financial |
| "stack sprawl @ <Company>?" | fast-growth tech/SaaS | Emilio — stack sprawl @ Datadog? |
| "audit-season prep made boring" | consulting + client-data-heavy | Ramana — audit-season prep made boring |
| "your board deck on autopilot?" | large enterprise CISO | Laura — your board deck on autopilot? |
| "proving the security program at <Company>" | regulated, audit-heavy | Igor — proving the security program at SUNY Downstate |
| "visibility across the <Company> stack" | consumer brands | Darren — visibility across the Parx Casino stack |
| "the <Company> tool stack dilemma" | SaaS/media | Nick — the Olo tool stack dilemma |
| "CPM built for CISOs/CSOs" | regulated-industry-translation angle | Alyssa — CPM built for CISOs |

### What this adds vs the other-owner corpus

- **First-name-no-salutation** opener is a Miles convention. Maura/Brad use "Hi <First>,". Miles in Register A uses just `<First>,`. Drops one line of filler.
- **Pattern-statement signature lines** are Miles's high-fidelity weapon. The other-owner corpus leans on "Sivan built this for…" as the anchor. Miles leads with his own framing, then lands Sivan.
- **Verbatim 160-hour quote usage rate** is higher in Miles's corpus than anyone else's. Right discipline.
- **Trigger-event specificity is sharper.** "Saw the final settlement payout went out on the 10th. $5M is a concrete number" beats "post-breach framing." Vault future drafts should match that specificity floor.
