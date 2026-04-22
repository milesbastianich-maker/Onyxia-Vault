---
type: intel
subtype: vertical
vertical: retail-hospitality
source: closed-won corpus + PCI-DSS 4.0.1 enforcement + HubSpot density analysis 2026-04-22
created: 2026-04-22
tags: [intel, v/retail, v/hospitality]
---

# Retail / Hospitality

1 direct win (Chipotle $80K, Maura) + 1 adjacent win (CWT $100K, Brad) + 1 live pipeline (Starboard Group $150K, Miles). 206 retail companies in HubSpot. PCI-DSS 4.0.1 mandatory since March 31, 2025 — 2026 is the first full enforcement year with no exceptions.

See [[../playbook/closed-won-patterns]] and [[../hunt-research/2026-04-22-closed-won-nonhealthcare-synthesis]].

## Regulatory surface

- **PCI-DSS 4.0.1 (active since March 31, 2025).** All previous grace periods expired. v3.2.1 retired December 31, 2024. Any merchant accepting card payment — QSR, hospitality, franchise, retail — must comply continuously.
  - **Requirements 6.4.3 and 11.6.1 (new):** real-time visibility into payment-page scripts to prevent e-skimming and script-injection attacks. Hardest new burden for multi-location operators.
  - **Continuous compliance model:** controls must be in place and documented year-round, not assembled before an annual audit.
  - **Non-compliance penalty:** acquiring banks levy $5K–$100K/month depending on merchant tier and duration. Source: [UpGuard PCI 4.0.1 Guide](https://www.upguard.com/blog/pci-compliance).
- **State privacy laws (CPRA, TX HB 4, VA CDPA).** Multi-location retailers collecting consumer data at scale face state-law cybersecurity audit triggers. CPRA mandates independent audits for businesses processing 250K+ CA consumers.
- **Breach-notification cascade.** A breach at any single location triggers multi-state notification. 2025 DBIR: payment-card skimming incidents up in physical retail. Source: [Verizon 2025 DBIR](https://www.verizon.com/business/resources/reports/dbir/).

## What retail / hospitality CISOs care about

1. **Franchisee/location scorecard.** The Chipotle pattern. Multi-unit operators have hundreds of locations, each a separate risk surface. A single-pane view of which locations are PCI-compliant matters to the CISO and the brand.
2. **Continuous compliance evidence.** PCI 4.0.1's shift from annual to continuous means the CISO needs an ongoing audit trail — not a point-in-time report.
3. **Payment-page script monitoring (6.4.3).** New requirement is operationally burdensome. Any vendor that simplifies this wins.
4. **Brand-risk quantification.** A breach costs more than the fine — it costs the brand. Onyxia's risk quantification layer translates technical risk into board-digestible dollar exposure.

## Who wins the meeting

Primary: CISO, VP Security.
Secondary thread: CIO, CFO, General Counsel (post-breach).
Chipotle was brand-risk + franchisee pattern. CWT was B2B travel management (different motion — more enterprise-IT-budget-driven). Starboard Group (pipeline) is hospitality franchise — closest analog to Chipotle.

## Competitive context

Retail IT security skews heavily toward POS/payment-specific tools (Trustwave, SecurityMetrics, Foresite) and the big PCI QSAs. GRC/reporting layer is typically absent or siloed in a spreadsheet. Onyxia enters as the continuous-monitoring reporting layer that sits above the technical tools.

## Play selection

- PCI 4.0.1 non-compliance hook: "Your acquiring bank is running monthly checks now — not annual audits." Urgency angle works immediately.
- Multi-location franchisee: Chipotle reference (do NOT name-drop unless cleared). Use pattern, not name.
- Starboard Group pipeline ($150K, Miles): active, closing motion in play. Do not re-prospect without checking deal status in HubSpot.
- New CISO/VP Security at a retail chain (trigger): exec-hire play within 90 days. See [[../triggers/exec-hire]].

## HubSpot targets

206 retail companies in CRM. Notable:
- Circle K (46K emp), El Corte Inglés (90K), Mohawk Industries — enterprise-class depth
- MSX International, TFG Limited, American Woodmark — mid-market tier
- Filter for US-based, 500+ employees, multi-location / franchise operators first

## Closed-won references

- Chipotle Mexican Grill ($80K, Maura, QSR, brand-risk + franchisee pattern)
- CWT / Corporate Travel ($100K, Brad, B2B travel adjacency)
- Starboard Group ($150K pipeline, Miles, hospitality franchise — in flight)
