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

- Pull Miles's own Gmail sent folder for his 90-day opener patterns. Miles has 0 direct HubSpot wins logged, so his voice is not represented in the above. This is the biggest remaining gap.
- Log the 8 zero-engagement wins manually so the vault knows what closed them (peer intro, RSAC, partner referral, etc.). Decision for Miles: is it worth the backfill?
- Pull the Chipotle walnut.io demo-request thread to understand the inbound flow that converted.
- Confirm with Maura, Brad, Brian, Yosef whether any cold outbound was sent via a non-HubSpot tool (Apollo, Outreach) and thus missing from this corpus.
