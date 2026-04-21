---
type: intel
subtype: methodology
topic: objection library
source: closed-lost corpus (113) + closed-won notes + product quotes
created: 2026-04-22
tags: [intel]
---

# Objection Library

Referenced by [[../../40_Plays/reply-intent-parser]] on the Objection branch. Referenced by [[sivan-peer-intro]] expected-objection section. Every new objection heard in a meeting or reply lands here.

## Rules

- **Verbatim customer phrasing first.** That is how the prospect will say it. We match their words before we match their intent.
- **Winning response pattern comes from closed-won notes where the same objection was overcome.** If the objection was never overcome in won deals, mark it open and flag to Miles.
- **Never quote pricing in any objection response.** Redirect to scoping call per [[../../40_Plays/reply-intent-parser]].
- **Never invent a feature.** Verify every product claim against `50_Intel/product/*` before using.

## The objections

### 1. "We already have [SIEM / EDR / DLP / GRC tool]."

**How they say it.** "We already have Splunk and CrowdStrike." / "We bought Archer." / "We just rolled out ServiceNow IRM."

**What it means.** They think we are another point tool. We are the layer above. This is the most common misunderstanding and the easiest to reframe.

**Winning response pattern.** Onyxia does not replace SIEM / EDR / GRC. It sits above the stack, pulls from those tools via API, normalizes the data, and produces board-ready reporting + predictive risk scoring.

Verbatim anchor from [[../product/positioning]]:
> "We sit above your existing security stack, normalize the data, and auto-generate board-ready reporting."

Reference proof: Hashal Mehta CISO quote from [[../product/quotes]]:
> "With Onyxia, everything is intuitive; the team now spends time analyzing results rather than populating them. Onyxia helps us understand where we're excelling and where we need more focus."

**Next step ask.** 15 min to show what we pull from their existing tools, not replace them.

---

### 2. "Not a priority right now." / "Time frame isn't right."

**How they say it.** "We are heads-down on a different initiative." / "Circle back Q3." / "Maybe next budget cycle."

**What it means.** From [[../playbook/closed-lost-patterns]] — "Time frame" accounts for roughly 15 percent of losses. Decode: "no economic buyer found + no forcing function." Pain is not acute enough relative to other fires.

**Winning response pattern.** Don't push past the no. Ask what IS the priority. That answer becomes the next trigger hook. Add to nurture with a specific trigger to re-approach on (new CISO, new breach, new compliance deadline, fiscal year start, new funding round).

Verbatim from [[sivan-peer-intro]]:
> "Not a priority right now." → Ask what is. The answer becomes next quarter's hook.

**Next step ask.** "Totally get it. What IS on the top of the list this quarter? I'll circle back when the timing matches."

**Mitigation going forward.** Feed the account into `50_Intel/nurture/` with the trigger-event watch.

---

### 3. "We don't have budget."

**How they say it.** "Budget is frozen." / "We spent it on [other tool] this cycle."

**What it means.** From [[../playbook/closed-lost-patterns]] — budget losses include Montefiore, Main Line Health, CSC, Insulet, Lowenstein Sandler, Fitch Group. Decode: "budget" is often code for "no economic buyer found." We never got to the person who signs off.

**Winning response pattern.** Identify the EB. MEDDPICC Economic Buyer slot must be named before any proposal. If the champion says no budget, ask who controls the line item. That person is the EB.

**Next step ask.** "Who owns the security program budget line? Happy to brief them directly so the case lives above the project level."

**Mitigation going forward.** No proposal ships without a named EB. Hard rule per [[../playbook/closed-lost-patterns]] closing action list.

---

### 4. "Send me pricing first."

**How they say it.** "What's it cost?" / "Ballpark the investment so I can see if it fits."

**What it means.** Shortcut past discovery. Without scope, pricing is either too high (scares off) or too low (commoditizes). Every closed-won deal in the corpus went through scoping before a number.

**Winning response pattern.** Do NOT quote. Per [[../../40_Plays/reply-intent-parser]] pricing is a hard stop. Redirect to a 15-minute scoping call. Reason: pricing depends on stack size + framework surface + number of users.

**Next step ask.** "Pricing depends on how much of your stack we pull from and which frameworks you run against. 15 minutes and I can give you a real number, not a marketing number."

**Hard rule.** No pricing over email, ever.

---

### 5. "I don't have time for another demo."

**How they say it.** "I've seen enough security tools this quarter." / "Not doing another vendor pitch."

**What it means.** Demo fatigue. They have seen ten dashboards this year. The peer-intro play beats the demo-request play here.

**Winning response pattern.** Reframe as a peer call, not a demo. Sivan Tehila is a former CISO. Her time with a CISO peer is about comparing notes on the problem, not walking through a product.

Anchor from [[sivan-peer-intro]]:
> "Sivan Tehila, our CEO and former CISO, built Onyxia specifically for [this moment / this problem]. Curious if that's on your radar as you're setting strategy?"

**Next step ask.** "Not a demo. 20 minutes with Sivan. She built this because she had the problem. No slides."

---

### 6. "We are building this in-house."

**How they say it.** "We've got our own dashboard." / "My team is Power BI-ing it." / "In-house data team is on it."

**What it means.** From [[../playbook/closed-lost-patterns]] — Amdocs was lost to "In-house method." 1 percent of losses. Usually a stall, not a real decision.

**Winning response pattern.** Reference the 160-hour-per-month quote from [[../product/quotes]]:
> "With Onyxia, we are able to save at least 160 working hours a month that one full-time analyst would traditionally spend on manual reporting and instead, focus more time on our actual risk management strategy."
> — CISO of a leading not-for-profit healthcare client

Then the 40-hour-per-week quote from [[../product/quotes]]:
> "Before Onyxia, our team spent at least 40 hours per week on manual reporting and data aggregation... Onyxia took us from the 'spreadsheet from hell' to automation to now, we can actually track and predict where things are going to go."
> — CISO of Leading Insurtech Company (likely CCC Intelligent Solutions, closed-won $120K)

**Next step ask.** "How many analyst hours a week does the in-house setup cost you today? If it's north of 20, worth 15 minutes to compare."

---

### 7. "We already bought a competitor." / "We are on [GRC/dashboard tool] with 12+ months left."

**How they say it.** "We're using [Archer / OneTrust / ServiceNow IRM]."

**What it means.** From [[../playbook/closed-lost-patterns]] — Onyxia lost ONE deal out of 113 to a competing service (Allied World). Competition is almost never the real loss. Usually "competitor" is a polite brush-off masking lack of urgency or missing EB.

**Winning response pattern.** Ask a calibration question per [[../../40_Plays/reply-intent-parser]] competitor branch. Probe for dissatisfaction signal. The goal is NOT to displace on contract date but to understand what their tool isn't doing.

Good calibration questions:
- "How is [tool] doing on automated board reporting? That's where we usually come in alongside, not replace."
- "Does [tool] pull from your entire security stack or mostly GRC workflows?"

**Next step ask.** "Not asking you to rip and replace. 15 minutes to see what [competitor] isn't covering. Most of our customers run both."

---

### 8. "Security teams don't need another dashboard."

**How they say it.** "We have dashboard fatigue." / "Another pane of glass isn't the answer."

**What it means.** They are pattern-matching to noise. This objection is about positioning, not product.

**Winning response pattern.** Use Hashal Mehta quote from [[../product/quotes]]:
> "With Onyxia, everything is intuitive; the team now spends time analyzing results rather than populating them."

Frame Onyxia as the dashboard that eliminates dashboards by normalizing all security data into one source of truth for board and program reporting.

Anchor from [[../product/positioning]]:
> "Many other tools create more noise. We allow security leaders to focus on strategic insights and then drill down to operational improvements."

**Next step ask.** "Fair. Most of our customers came in with that same reaction. 20 minutes with Sivan and you can decide if we fit the 'actually reduces noise' column."

---

### 9. "Need to run this by [board / CFO / legal]."

**How they say it.** "Need buy-in from [CFO / GC / Board]." / "Let me socialize this."

**What it means.** Could be a real process marker (good) or a soft deflection (bad). Depends on whether they've identified the approver by name.

**Winning response pattern.** Use it to multi-thread. Offer to brief the named approver directly or provide a written business justification doc.

**Next step ask.** "Happy to put together a 2-page business justification for [named approver] so you don't have to translate. Who's the right person to share it with directly?"

**MEDDPICC tie-in.** This is the moment to name the Economic Buyer. If the champion can't name them, the EB slot is empty. Flag on account note per `10_Accounts/{Company}.md` MEDDPICC section.

---

### 10. Silence. No response.

**How they say it.** They don't. 60 percent of closed-lost had one contact and went quiet.

**What it means.** From [[../playbook/closed-lost-patterns]] — Onyxia does not lose to competitors. It loses to silence. Single-threaded accounts drift.

**Winning response pattern.** Pattern-break at day 14 with a different format. Voicemail, Loom, LinkedIn message. Multi-thread to a second contact. Bring a fresh trigger event.

From [[../playbook/closed-lost-patterns]]:
> Every active deal must have ≥2 engaged contacts within 30 days of first meeting.
> Follow-up cadence: day 3, day 7, day 14, day 30, day 60. Pattern-break at day 14 with a different format.

**Next step ask.** Skip to a second contact. Draft for the GC, the CIO, or the peer. Don't keep poking the original thread.

---

## Objections we have NOT heard yet (watchlist)

Empty slots. Fill as they come up in meetings.

- **Sovereignty / data residency** — not yet encountered. Likely relevant for EU / Israeli / APAC buyers.
- **FedRAMP / government certification** — Onyxia does not currently serve FedRAMP-High. See [[../icp]] exclusion. Objection lives in exclusion territory.
- **Integration gaps** — 8 percent of losses per [[../playbook/closed-lost-patterns]]. Specifics unknown. When heard, log the exact tool that wasn't integrated.
- **Service not of value** — Veterans United, Keurig Dr Pepper per loss corpus. Decode unknown. Ask Maura Clancy when possible.

## Vault-silent slots

- **Deployment complexity objection.** We have the immediate-value quote from [[../product/quotes]] but no verbatim customer phrasing of the objection.
- **Data exposure / security concerns on sending our data to Onyxia.** Likely comes up at BigLaw / financial services. No verbatim capture yet.

## How this file gets updated

- Every new meeting debrief under `30_Meetings/` with a flagged objection appends here.
- Every reply-parser "Objection" classification references this file.
- Friday synthesis promotes any objection heard 2+ times in the week.

## Cross-references
- [[../playbook/closed-lost-patterns]] — where the data comes from
- [[../playbook/closed-won-patterns]] — where the responses come from
- [[../product/quotes]] — verbatim customer language
- [[../../40_Plays/reply-intent-parser]] — reply intent branches
- [[../../40_Plays/sivan-peer-intro]] — peer-call pivot
- [[measurement-log]] — per-draft log, tracks which objections block conversion
