---
type: intel
account: "[[iVisa]]"
signal_date: 2026-05-05
trigger_verdict: not_fired
tags: [intel, account/iVisa]
---

# iVisa — ZoomInfo Signals Scan — 2026-05-05

## Trigger verdict: NOT FIRED

No certification pursuit signal detected. No security leadership hire. No GRC or compliance role opened. No funding event. The 2026-08-01 dark window stands as-is, with one partial watch item noted below.

---

## Intent signals

ZoomInfo intent topics API returned a validation error on the compliance/GRC topic cluster (SOC 2, ISO 27001, GRC, SIEM, Vulnerability Management topics). The topics as submitted did not match ZoomInfo's canonical intent-topic taxonomy. Re-run recommended once valid topic IDs are obtained via the ZoomInfo lookup endpoint.

Result: ZoomInfo intent signals vault-silent on iVisa as of 2026-05-05. No data returned. (source: ZoomInfo Enrich Intent API, retrieved 2026-05-05)

---

## Scoops (ZoomInfo, retrieved 2026-05-05)

Source: ZoomInfo Scoops enrichment on company ID 415242776.

### Signal 1 — CTO promotion (Jan 2026, moderate relevance)

Andee Woodward was promoted from VP Engineering to Chief Technology Officer at iVisa. (source: ZoomInfo scoop ID 14585049, original published 2026-01-31, retrieved 2026-05-05)

Relevance: a new CTO can accelerate a compliance posture decision if they come in with a security or scale mandate. Woodward is an internal promotion from VP Eng -- not a security-pedigreed hire. #hypothesis: internal promotions of this type rarely accelerate certification timelines; more likely a stability signal than a change signal.

### Signal 2 — CMO / CGO departure (Jan 2026, low relevance)

Dave Sampson (Chief Growth Officer + CMO) left iVisa as of late January 2026 and is now CMO at RentRedi. (source: ZoomInfo scoop ID 15375250, original published 2026-01-31, retrieved 2026-05-05)

Relevance: C-suite turnover in a non-security function. Not a trigger for Onyxia. Noted for org-stability context. A company losing both a CGO and CMO in the same window is under some internal churn. #hypothesis: leadership churn at this level often correlates with a growth-mode pivot (headcount build, new enterprise customer requirements), which could pull compliance timelines forward -- but this is speculative without more data.

### Signal 3 — Senior Data Engineer hire open (Jan 2026, low-to-moderate relevance)

iVisa was hiring a Senior Data Engineer as of late January 2026. (source: ZoomInfo scoop ID 14326959, original published 2026-01-24, retrieved 2026-05-05)

Relevance: data engineering headcount at a company handling passport PII can precede a data governance or compliance build-out. Not a definitive signal, but worth noting alongside the ~1-year certification horizon Susan described. #hypothesis

### Signal 4 — Marketing hiring surge (Dec 2025, low relevance)

iVisa had more open Marketing roles than at any point in the prior 9 months as of December 2025. (source: ZoomInfo scoop ID 13777939, original published 2025-12-03, retrieved 2026-05-05)

Relevance: indicates growth investment in acquisition, not security. B2C / enterprise channel expansion could eventually pull in enterprise customer compliance requirements (SOC 2 for enterprise clients is a common forcing function). #hypothesis, not a current signal.

### Signal 5 — Senior PHP Developer hire open (Mar 2026, low relevance)

Open engineering role as of March 2026. (source: ZoomInfo scoop ID 14943178, original published 2026-03-21, retrieved 2026-05-05)

Relevance: no security relevance.

---

## News (last 90 days, ZoomInfo, retrieved 2026-05-05)

Source: ZoomInfo News enrichment on company ID 415242776, date range 2026-02-05 to 2026-05-05.

### News 1 — US B1/B2 visa support launch (Mar 2026)

iVisa launched a support service for US B1/B2 tourist visa applicants in March 2026, framed around tightening compliance requirements for DS-160 guidance. (source: https://www.globenewswire.com/news-release/2026/03/02/3247152/0/en/iVisa-Launches-Support-Service-for-US-B1-B2-Tourist-Visa-Applicants.html, retrieved 2026-05-05)

Relevance: product expansion. iVisa is broadening its document-assistance scope. A larger surface area of government ID handling increases data governance obligation -- but this is a slow-burn signal, not a certification trigger. The US visa product line likely brings them into contact with enterprise travel managers and corporate accounts who will eventually demand SOC 2. #hypothesis

### News 2 — Solo traveler visa rejection data release (Apr 2026)

iVisa published proprietary data on solo traveler visa rejection rates (5x higher than group applications). GlobeNewswire press release. (source: https://www.globenewswire.com/news-release/2026/04/09/3270809/0/en/Alone-and-denied-Solo-travelers-are-five-times-more-likely-to-face-visa-rejection-says-iVisa.html, retrieved 2026-05-05)

Relevance: marketing/PR data release. No compliance signal.

---

## Org chart / leadership layer (ZoomInfo contacts, retrieved 2026-05-05)

Full director+ contact sweep on iVisa (ZoomInfo company ID 415242776):

| Name | Title | Signal relevance |
|---|---|---|
| Konstantin Lange | COO | Budget owner candidate. No security mandate visible. |
| Sarai Ledford | VP, People | HR-level. Relevant only if they hire a security head. |
| Andee Woodward | CTO | New in role (promoted Jan 2026). Engineering-led, not security-led. |
| Susan Lloyd | Director, Information Governance & Security | Known contact. Our sole security thread. |
| Corey Trout | Director, Product Management | No security relevance. |
| Alejandro Ferrero | Director, Product | No security relevance. |
| Victor Gimenez | Director, Customer Experience | No security relevance. |

Key finding: there is no CISO, VP Security, VP of GRC, or Chief Information Security Officer in the ZoomInfo contact database for iVisa as of 2026-05-05. Susan Lloyd is the only security-titled contact. No new security leadership layer has been added above or alongside her. (source: ZoomInfo contact search on company ID 415242776, retrieved 2026-05-05)

---

## Firmographic baseline (ZoomInfo, retrieved 2026-05-05)

- Employees: 128 (range 100-250) (source: ZoomInfo enrich, retrieved 2026-05-05)
- Revenue: ~$7.7M (range $5M-$10M) (source: ZoomInfo enrich, retrieved 2026-05-05)
- HQ: Newark, Delaware, USA (source: ZoomInfo enrich, retrieved 2026-05-05)
- Type: Private, bootstrapped (source: ZoomInfo enrich + vault, retrieved 2026-05-05)
- Industry: Travel Agencies & Services / Hospitality (source: ZoomInfo enrich, retrieved 2026-05-05)
- Status: Active (source: ZoomInfo enrich, retrieved 2026-05-05)
- Last ZoomInfo update: 2026-05-05 (same day -- data is current)

Revenue at $7.7M puts iVisa in a size band where SOC 2 is aspirational, not obligatory, unless enterprise customers are demanding it. No enterprise customer requirements surfaced in public signals.

---

## Trigger verdict: NOT FIRED

The three conditions that would move this account are:

1. Certification announcement (LinkedIn, press, job post) -- not present
2. Security leadership hire above or alongside Susan -- not present
3. Funding event that signals growth requiring enterprise compliance -- not present

The CTO promotion and CMO departure are ambient churn signals, not compliance signals. The data engineering hire is worth a second look if a GRC or compliance engineering role opens alongside it. #hypothesis

---

## Re-touch timing recommendation

Current dark window: 2026-08-01. This scan does not change that date. No signal justifies earlier contact.

One watch item: the B1/B2 product launch (March 2026) is expanding iVisa's government ID surface area. If they announce a second major product expansion or a B2B enterprise partnership in the next 90 days, that could pull the certification timeline forward. Monitor LinkedIn and press quarterly, not monthly.

Maintain 2026-08-01 as the earliest re-touch date. If no trigger has fired by then, use the light 1-liner intel-share approach from the debrief nurture plan.

---

Related: [[iVisa]] [[../30_Meetings/2026-04-27-ivisa-debrief]] [[../50_Intel/industry/regulatory-calendar]]
