---
type: intel
subtype: product
topic: forbidden words
source: feedback_email_engine.md + 00_Index/CLAUDE.md voice rules + 2026-04-21 session synthesis
created: 2026-04-21
tags: [intel, product]
---

# Forbidden Words

Words and phrases Miles never writes in outbound to security buyers. Auto-reject any draft that contains them. Compiled from the closed vocabulary in `00_Index/CLAUDE.md`, the `feedback_email_engine.md` memory, and contemporary CISO tell-tale lists.

## Note on em dashes

Em dashes are banned in AGENT-written drafts (they are a tell). Miles's own prose uses em dashes naturally. When editing Miles's copy, preserve his em dashes. When writing as the drafter sub-agent, do not introduce them.

## Corporate jargon (auto-reject)

- leverage (as a verb) → use
- synergy / synergize → write what the actual value exchange is
- ecosystem → integrations, stack, partners — name the specific thing
- robust → pick the concrete capability
- seamless / seamlessly → delete, it adds nothing
- unlock → enable, allow, or delete
- empower → delete
- streamline → reduce, cut, speed up
- holistic → comprehensive, or delete
- solution → product, platform, tool, or the specific feature name
- best-in-breed / best-in-class → delete, name a specific differentiator
- disrupt / disruptive → delete
- next-generation / next-gen → delete, the CISO has heard it 500 times
- cutting-edge / bleeding-edge → delete
- revolutionary → delete
- transformative / transformation → too big, too abstract
- paradigm shift → never
- end-to-end → delete, be specific about scope
- turnkey → delete
- mission-critical → delete, over-indexed
- enterprise-grade → delete
- game-changing / game-changer → delete
- world-class → delete

## AI writing tells (auto-reject)

- "I hope this email finds you well"
- "I hope you're doing well"
- "I wanted to reach out"
- "I'm reaching out because"
- "I wanted to share" (acceptable in post-meeting context, banned in cold)
- "Just wanted to / just circling back / just checking in / just following up"
- "Circling back"
- "Touching base"
- "I'd love to" (any variant)
- "As discussed" (unless an actual prior discussion is cited by date)
- "In summary" / "To summarize" / "As mentioned above"
- "Dive into" / "deep dive" (overused)
- "Delve" / "delve into"
- "Navigate the complexities of"
- "Tapestry of"
- "Landscape of" / "the cyber landscape"
- "Realm of"
- "Crucial" (overused)
- "Essential" (overused)
- "Cultivate"
- "Foster"
- "Holistic approach"
- "Embark on a journey"
- "Unveil"
- "Unleash"
- "Elevate"

## Cyber-buyer-specific dead phrases (2026)

Security buyers have been pitched these to exhaustion. They signal vendor, not peer.

- "AI-powered" → meaningless to a CISO in 2026. If Onyxia is using AI for something specific, name what it does (e.g., "auto-maps your controls to HIPAA §164.308 in a click"). Otherwise delete.
- "cyber resilience" → Onyxia's own category language, background noise when used in cold. Fine on the website, cut from cold subject lines.
- "proactive security posture"
- "reduce your attack surface" (as cold hook)
- "threat landscape"
- "security journey"
- "unified platform"
- "single pane of glass" → cliché, triggers eye-roll
- "bad actors"
- "threat actors" (acceptable when specific, banned as generic opener)
- "zero trust" as a stand-alone buzzword (acceptable when tied to a specific architecture decision)
- "machine learning-powered" → meaningless
- "continuous monitoring" → what product isn't?
- "accelerate digital transformation"

## Opener anti-patterns

- Opening with "I" or "My name is" or "I'm [name]"
- Opening with "[Company] is a [product category]"
- Opening with "Congratulations on [LinkedIn milestone]" unless tied to a concrete trigger (new-CISO 30-day window is OK)
- "Hope you're having a great week"
- Two-paragraph intro before you say what you want
- Subject lines that start with "Quick question" or "Quick intro" or "15 minutes?"

## CTA anti-patterns

- "Hop on a call"
- "Jump on a call"
- "Pick your brain"
- "Grab 15 minutes"
- "Let's connect" (no specific reason)
- "Would love to chat"
- "Demo request" as CTA in cold → use peer call framing per `40_Plays/cta-ladder.md`

## Subject line anti-patterns

- `Re:` on a cold (fakes a reply thread — dishonest, triggers spam filters)
- `[EXTERNAL]` bracketed
- All caps
- Emojis in subject line
- Question marks stacked ("??" "!?")
- Subjects over 8 words
- Generic "Quick question" / "Following up" as cold opener (OK as a bump, banned as opener)

## Anti-patterns specific to Miles's prior drafts

### Register-B mail-merge templates (banned 2026-04-22 by Miles)

If any of these appear in a draft, reject and rewrite as Register-A with one-to-one specificity:

- "tend to inherit a toolbox that grew faster than the playbook"
- "Twenty-plus tools, three that overlap, two that nobody's quite sure are still live"
- "your security stack looks less like a tidy pyramid and more like a LinkedIn logo garden"
- "Financial-services CISOs have the rough job of explaining cybersecurity effectiveness to people who'd rather talk about returns"
- "Running security in a client-data-heavy environment like [Company] means every audit or client security questionnaire becomes a mini fire drill"
- "a security surface area that would make most CISOs wince"
- "end up doing a lot of translation — from security data to risk language to board language"
- Any subject in the `[First] — [hook] @ [Company]?` or `[First] — CPM for [Company]` or `[First] — a map for the security stack` patterns (see `winning-openers.md` Register-B anti-pattern table)

### What "personalized" actually means (Miles 2026-04-22)

A concrete fact specific to THIS company that could not be said about any other prospect. Examples from Register-A that pass:
- "Saw the final settlement payout went out on the 10th. $5M is a concrete number for the board to hold against whatever security investment comes next." (Medusind, post-settlement)
- "Saw the announcement on Chris Tyrell joining as CIO yesterday." (Cross Country, new-CIO 1 day prior)
- "Moving from GRC at Fidelity to owning the full security program at an $84B-asset bank is a different animal" (Leilani, named prior company + named prior role + named current asset size)

If the opener works with the company name swapped, it fails. Rewrite.

_Future rejections populate here as 👎 reactions land in `60_Lessons/rejections/`. Every 👎 gets a one-line reason captured here + in `40_Plays/rejection-feedback.md`._

## How to test a draft

1. Grep the draft for every word above. Any hit = rewrite.
2. Read it aloud. If it sounds like an SDR, not a peer, rewrite.
3. The "Miles after two coffees and before his first meeting" test: would Miles actually type this to another CISO he respects? If no, rewrite.
4. If a sentence could appear verbatim in any SaaS vendor blog, delete it.

## Cross-references

- [[../../00_Index/CLAUDE]] — voice rules source of truth.
- [[../../40_Plays/rejection-feedback]]
- [[../../40_Plays/cta-ladder]]
- [[./power-phrases]]
- [[./winning-openers]]
- [[../methodology/objections]]
