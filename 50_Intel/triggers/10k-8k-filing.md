---
type: intel
subtype: trigger
trigger: sec-filing
source: SEC rulemaking + Item 1C 10-K disclosures + EDGAR patterns
created: 2026-04-22
tags: [intel]
---

# 10-K / 8-K Filing

Public-company filings encode the cyber posture in language we can mine. Use 10-K Item 1C (Cybersecurity) to find risk-factor weakness. Use 8-K Item 1.05 to find material incident disclosures. Also use 8-K Item 5.02 for officer changes (see [[exec-hire]]). See [[sec-cyber-rule]] for the rule basis.

## The filings that matter

- **10-K Item 1C (Cybersecurity).** Required since 2023-12-15 fiscal years ending. Narrative on risk management processes, governance, board oversight, prior material incidents. Source: [SEC.gov 2023-139](https://www.sec.gov/newsroom/press-releases/2023-139) and [KPMG reference library](https://kpmg.com/us/en/frv/reference-library/2024/sec-finalizes-cybersecurity-rules.html).
- **8-K Item 1.05 (Material Cybersecurity Incidents).** Four business days from materiality determination. Since 2023-12-18.
- **8-K Item 5.02 (Officer departures/appointments).** Maps to [[exec-hire]] trigger.
- **10-Q cyber updates.** Look for new disclosure or updated legal proceedings.
- **Proxy statement (DEF 14A) risk oversight section.** Board committee structure for cyber.

## What to mine

- **Weak risk-factor language.** "We may experience incidents; we cannot fully prevent." Generic risk factor = underdeveloped program = opportunity.
- **Named committee.** Some filers name a Risk + Technology Committee with cyber oversight. That committee is where our board reporting lands. See [[../product/features]] pillar 4.
- **Named CISO / CSO in governance section.** Confirms persona + title.
- **Prior material incidents referenced in Item 1C.** Inherent post-incident rebuild context.
- **Third-party + supply chain language.** DBIR 2025 shows third-party involvement doubled YoY to 30% of breaches. If the 10-K is thin on third-party, that's a board-reporting gap.

## Detection pattern

- SEC EDGAR full-text search for "Item 1C" + vertical-specific language.
- EDGAR RSS feeds on Tier 1 ICP tickers.
- Known Trends + Hunton + Blank Rome track Item 1.05 filing trends quarterly. Source: [Known Trends snapshot](https://www.knowntrends.com/2025/02/snapshot-the-first-year-of-cybersecurity-incident-filings-on-form-8-k-since-adoption-of-new-rules/).
- SEC enforcement press releases (October 2024 wave hit 4 companies for misleading 8-K cyber statements).

## Response timing

- **Immediately after 10-K:** 60-day window to engage on new Item 1C language.
- **Immediately after 8-K 1.05:** apply [[breach-event]] timing rules. Wait 7-30 days.
- **Immediately after 8-K 5.02 (officer change):** apply [[exec-hire]] timing rules.
- **Pre-next-fiscal-year-end filing:** buyers want new tooling in place before the next Item 1C goes public.

## Historical win examples

Vault-thin on filings-sourced wins specifically. Most wins trace to offline outbound (85% of wins per [[../playbook/closed-won-patterns]]). Hypothesis worth testing: filings-mining as a top-of-funnel signal for finserv + healthcare + defense primes is under-instrumented today. Propose weekly EDGAR sweep on Tier 1 tickers in the [[../../40_Plays/hunt/trigger-event-hunt]] shift.

## Template reference

Use [[../../90_Templates/tpl-ciso-cold]] with a 10-K / 8-K opener. Anchor on specific language from the filing in sentence one.

## Language that lands

- "Saw your Item 1C disclosure this quarter. [Specific language]. That's the conversation most CISOs are trying to avoid next year with different language." (implies a tighter program)
- "Your 10-K this year names [Risk + Technology Committee]. We produce the board pack that committee is probably reading today."
- "Item 1.05 filings are up YoY. The differentiator on SEC enforcement is documented governance. We make that documentation continuous."

## Cross-references

- [[sec-cyber-rule]]
- [[breach-event]]
- [[exec-hire]]
- [[settlement-event]]
- [[../industry/regulatory-calendar]]
- [[../playbook/closed-won-patterns]]
- [[../personas/ciso]]
- [[../personas/general-counsel]]
- [[../methodology/objections]]
- [[../verticals/financial-services]]
- [[../verticals/manufacturing]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../40_Plays/hunt/trigger-event-hunt]]
