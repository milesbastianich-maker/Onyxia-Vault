---
type: intel
subtype: trigger
trigger: m-and-a
source: closed-won corpus + post-close integration patterns
created: 2026-04-22
tags: [intel]
---

# M&A Activity

Post-close security integration is a budget-release event. Ranked trigger #4 in [[../icp]]. Acquirer inherits the target's stack + compliance posture. Integration raises board-level visibility. PE portfolio acquisitions especially generate Onyxia-shaped problems: visibility across newly-federated estates.

## Detection pattern

- SEC 8-K Item 1.01 (material definitive agreements) + 2.01 (completion of acquisition or disposition).
- PE firm press releases on portfolio moves.
- Antitrust filings (HSR).
- LinkedIn announcements of integration leadership roles.
- ZoomInfo org-level M&A flags.
- News search on [company] + "acquires" / "merger" / "portfolio company."
- Corp dev hires at PE-backed targets (e.g., Colton Houseman at Alpine/Medusind).

## Response timing

- **Announcement → close:** too early. Regulators, outside counsel, diligence teams own the room.
- **Close + 30 days:** still too early. Integration planning forming.
- **Close + 60-180 days:** sweet spot. Acquirer CISO owns integrating the target's security program. Visibility gaps are now apparent and painful.
- **Close + 180-365 days:** still convertible. Annual plan cycle is forming. Board is asking for combined-entity posture.
- **Close + 365 days+:** integration has settled; harder to open. Move to nurture.

## Historical win examples

- Radiant Logic ($165K, 36 days) — SaaS identity vendor win. Likely adjacent to M&A integration pain in the identity space.
- PE-backed wins: CCC ($120K), Vista Equity ($37.5K). Vista is a PE firm itself — the win hints at PE-portfolio visibility as an opening.

## Historical loss examples

Vault-silent on clean M&A-triggered losses specifically. Some PE-adjacent losses in the 113-deal corpus may trace to M&A timing. Propose tagging M&A-sourced deals explicitly going forward.

## Active example

- [[../../10_Accounts/Medusind]] — Alpine Investors-backed, multi-entity structure across US + India. Not a fresh M&A but PE-portfolio dynamics create the same Onyxia-shaped visibility problem. Corp Dev contact (Colton Houseman) is a latent PE-liaison thread.

## Who wins the meeting

- Acquirer CISO (usually leads integration).
- CIO (infrastructure integration).
- GC (BAA / DPA / regulatory consolidation).
- PE ops team (portfolio-wide cyber program).

## Template reference

Use [[../../90_Templates/tpl-ciso-cold]] with an M&A-integration opener. Anchor on specific integration pain ("your new entity uses Splunk while your corporate stack uses Sentinel; reporting combined posture today is a spreadsheet").

## Language that lands

- "You just inherited [target]'s security stack. Integrating that into one board-level view usually eats two quarters of your team's time. Onyxia shortcuts it."
- "PE portfolio companies need a single-lens view across entities. We build that lens."
- "Post-close integrations fail when the combined-entity compliance report doesn't exist. We make that report continuous."

## Cross-references

- [[../icp]]
- [[../playbook/closed-won-patterns]]
- [[10k-8k-filing]]
- [[exec-hire]]
- [[../personas/ciso]]
- [[../personas/vp-security]]
- [[../personas/general-counsel]]
- [[../methodology/objections]]
- [[../verticals/financial-services]]
- [[../verticals/healthcare]]
- [[../verticals/manufacturing]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../40_Plays/hunt/trigger-event-hunt]]
