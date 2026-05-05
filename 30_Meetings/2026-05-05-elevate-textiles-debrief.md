---
type: meeting
subtype: debrief
account: "[[Elevate Textiles]]"
attendees: Rick Scott, Sivan Tehila, Brad Baldelli, Miles Bastianich, Karen Mesoznik, Thiago Kaviski (CRA host)
date: 2026-05-05
tags: [meeting]
---

# Debrief — 2026-05-05 Elevate Textiles Demo (Rick Scott)

CRA-hosted 45-minute demo. Rick Scott is global CIO + global CISO at Elevate Textiles (manufacturing). Strong technical fit. Rick is an Israeli-startup advisor with deep affinity for Israeli founders, which Sivan walked into early. Closed with concrete next-step asks: send follow-up today, expand to his team in mid-June, plan a Charlotte dinner in September.

## What happened

- Sivan opened with personal story (10 yrs IDF cyber, ex-Perimeter 81, ex-CISO). Rick disclosed he advises Israeli startups, said "if you're not an Israeli company, I don't know if I want to talk to you, so you're good." Sivan dropped at minute 13.
- Brad walked the platform: home dashboard 85% effectiveness score → 50 integrations page → security stack map (NIST-aligned) → identities KPI page → Asset Coverage Analyzer → framework toggle (NIST/Onyxia) → reporting (PDF + 62-page exec PowerPoint) → Nexa AI agent.
- Miles plugged the Nexa cross-domain query in chat. Rick reacted positively: "that's relevant to me, I like that, Miles."
- Three product features clearly resonated: Asset Coverage Analyzer Venn diagram ("really cool", "very cool"), cross-domain Nexa query, sector benchmarking (manufacturing now in scope).
- Rick raised one missing pillar (NIST 5th — Govern). Brad acknowledged it's on the roadmap.
- Karen and Rick connected on Charlotte (her hometown). Dinner planning tee'd up.

## Rick's verbatim signals (use these)

> "If you're not an Israeli company, I don't know if I want to talk to you, so you're good." — at minute 4. Strong affinity.

> "I have a front-row seat to all of the innovation coming out of Tel Aviv, and it's incredible. And this is right up there. I mean, this is something that doesn't exist today." — minute 30, after the Asset Coverage Analyzer.

> "I like the tools that do more than just one thing, because I don't have a lot of budget or tools." — minute 31. Buying criteria. Onyxia wins because it bundles risk + SLA + asset inventory.

> "VPN is not the solution. That was the solution 10 years ago. I'm trying to bring people into today." — minute 11. Active divestiture pain. Third-party access for the buyer of the divested business unit.

> "I need to spend money to protect the company more than I do to identify the risk. I know what the higher risks are at this point. But you're bringing more to the table than that." — minute 45. Differentiates Onyxia from Safe Security in his head.

> "FAIR — in theory it's wonderful, but it is impossible to execute once, and then to use it moving forward, you just can't do it." — minute 23. He knows Jack Jones personally. He has rejected the FAIR-model risk tools.

> "This is one of my favorite demos." — Karen, minute 46. Closing emotional read. Save for the follow-up.

## What Rick told us about himself (use in outreach)

- 14 months at Elevate. Hired as global CISO. Became global CIO in November 2025 when CIO left. Now wears both hats.
- Career: 21 years at Bank of America, 18 months at Bank of New York. 23 years total in financial services before manufacturing.
- Led NIST 1 → NIST 2 mapping at Bank of New York. Self-described "NIST guy."
- Native of Los Angeles. Lives in Huntersville (north of Charlotte).
- Husband. (His phrasing: "my husband is" a gamer.)
- Formal advisor to **Tenet** (AI agentic security, ex-8200 founders). Working with **Mars** (Israeli startup, named for founders' first initials). Did POV with **Axonius**. Engaged with **Safe Security** and personally knows **Jack Jones** (FAIR model author).
- Invited to the Israeli Embassy Independence Day celebration in May 2026 via iSense.
- Charlotte cyber community: 400+ professionals on the distribution list. Rick is a connector. Free dinners attract crowds.
- Recommended Sea Grill (was Blackfin in the Epicenter) for the Charlotte dinner. September is the right time. Avoid June (4th of July, 250th US birthday slows things).

## What Rick told us about Elevate (the company-level pain)

- Currently divesting one of their business units. The buyer needs access to Elevate systems. His team's default answer is "give them VPN." Rick is pushing for ZTNA-style access. This is an active, 2026 problem.
- Global ops: Bangladesh, Sri Lanka, Mexico, India, Mount Holly NC. SMS-based MFA in regions where smartphones are expensive. Manual workarounds (YubiKey for one older worker without a smartphone).
- Tech stack mentioned in call:
  - **Microsoft Suite** + Microsoft Authenticator (corporate MFA)
  - **Cisco Duo** (network access MFA, separate from Microsoft)
  - **Darktrace** (just implemented — email security + security awareness training)
  - **SentinelOne Singularity** (kicking off endpoint protection rollout Monday 2026-05-12)
  - **SentinelOne SIEM** (currently using; Brad noted SIEM is not their preferred integration source)
  - **Tanium** (asset coverage)
  - **Microsoft Defender for Cloud** ("barely using it") — no other CSPM/CNAPP today
  - **Axonius** — POV done, not bought (couldn't justify single-purpose tool)
  - **SAFE Security** — engaged, his Risk Compliance Manager participated
- Stated 2026 priorities (from his survey filled out pre-call): no KPI process today, automation focus for 2026, resiliency + risk, reporting need.
- Specific gap mentioned in call: 145 privileged users without MFA across both Microsoft and Duo systems. Manual reconciliation today.

## What did NOT resonate / open issues

- 5 NIST pillars vs Onyxia's 4-pillar view. Rick called out Govern is missing. Brad said roadmap. Worth flagging in follow-up that we know it matters.
- Brad's Nexa demo with "Joe Smith" failed (no test data). Recovered via Miles's chat-plug of the cross-domain query. Future demos: pre-load real-looking demo employee data.
- Time pressure at end. CRA enforced 45 minutes. Should not have spent 13 minutes on intros.

## MEDDPICC deltas

Filled or updated on [[Elevate Textiles]]:

- **Metrics** — 145 privileged users without MFA (Rick stated). 40 hours/week manual reporting (Onyxia's 40-hours-per-week customer quote applies here). No KPI process today.
- **Economic buyer** — Rick has buying authority for budgeted items. Likely sole approver under threshold.
- **Decision criteria** — tools that do more than one thing. Real-data risk over subjective FAIR. NIST alignment. Sector benchmarking (manufacturing).
- **Decision process** — Rick wants expanded demo with Director of Infrastructure (asset management lens) + Security Risk Compliance Manager (vulnerability lens) in mid-June after his holiday.
- **Identified pain** — divestiture third-party access (urgent, 2026). MFA gap reconciliation. Manual reporting + KPI tracking. No CSPM beyond Microsoft. Asset coverage gaps across Tanium / SentinelOne footprints.
- **Champion** — Rick himself. Strength 4/5 (early). Champion test not yet passed (has not introduced us to peer or shared internally).
- **Competition** — Axonius (POV done, didn't proceed), Safe Security (engaged), Tenet (he advises). Status quo: manual reconciliation + Microsoft Defender for Cloud underused.

## Commitments

- **They said they would:**
  - Reply with times and dates for an expanded demo with two team members in mid-June.
  - Connect with Karen on the Charlotte September dinner.
  - Rick put his email in the chat (capture from Zoom chat / CRA recording handoff — confirm we got it).
- **I said I would:**
  - Send follow-up email by EOD 2026-05-05 with: company info, integration list, Nexa FAQ. CC Brad, Karen, Sivan. Rick wants one thread for everyone.
  - Coordinate with Karen on Charlotte dinner planning (Sea Grill, September).

## Next step

- **2026-05-05 EOD** — Miles sends follow-up email (single thread, all attendees). Includes integration list, Nexa FAQ, company one-pager. Open with Rick's "doesn't exist today" reaction or his Israeli-startup affinity. Asks for mid-June availability.
- **2026-05-06** — Karen reaches out to Rick re Charlotte dinner. September window. Sea Grill is Rick's recommended venue.
- **2026-06-15 ish** — expanded demo with Rick + Director of Infrastructure + Security Risk Compliance Manager. Asset management + vulnerability angles.
- **2026-09-XX** — Charlotte dinner. Sivan attends (her first time in Charlotte). 400-person Charlotte cyber community is the upside.

## Intel to promote (for [[../50_Intel/]])

- **Manufacturing vertical brief** — Elevate is a strong reference for the manufacturing brief once we earn the case study. Multi-region (Bangladesh, Sri Lanka, Mexico, India, US). SMS-MFA reality in low-smartphone-density regions is a manufacturing pain we have not documented.
- **Competitor file** — Tenet (Rick advises). 8200-founded AI agentic security. Worth mapping in `50_Intel/competitors/tenet.md` if not present.
- **Competitor file** — confirm `50_Intel/competitors/safe-security.md` and `50_Intel/competitors/axonius.md` exist and reflect Rick's "FAIR is impossible to execute" + "couldn't justify single-purpose tool" positioning.
- **Quote candidate** — Rick's "this is something that doesn't exist today" + "I like tools that do more than one thing" both belong in `50_Intel/product/quotes.md` as live-call peer quotes (not customer quotes — prospect-call quotes).
- **Asset Coverage Analyzer** — confirmed top-of-demo win. Add to `features.md` as the "show this first" anchor for any prospect with multi-tool environment + asset inventory pain.
- **Buying-trigger pattern** — divestiture creating third-party access pressure. Add to `50_Intel/icp.md` trigger events list if not there. Manufacturing + PE-track + carve-out signals are likely.

## Lesson

When the CEO drops 13 minutes into a 45-minute call, intros must be tighter. Sivan's story is the highest-conversion warm-up but should run 3-4 minutes, not 7. For Israeli-affinity prospects, Sivan can sometimes appear in the demo opener and exit fast, leaving 35+ minutes for product. Pulled into the Friday review.
