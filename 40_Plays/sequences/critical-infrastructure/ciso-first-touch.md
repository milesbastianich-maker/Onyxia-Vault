---
type: play
vertical: critical-infrastructure
persona: ciso
trigger: cisa-kev-exposure OR nerc-cip-update OR tsa-pipeline-update OR new-ciso
created: 2026-04-22
tags: [play, v/ci, p/ciso]
---

# Critical Infrastructure CISO — First-Touch Sequence

Sector-regulated. NERC CIP (energy), TSA pipeline rules (transport), CISA KEV exposure. CIs often have slower buying cycles and deeper board oversight than commercial ICP.

## When to run

- CISA KEV adds a vendor the account is known to run (per `multi-thread-mapper` tech stack enrichment), OR
- NERC CIP-002 through CIP-014 update in effect inside 180d, OR
- TSA pipeline/rail cybersecurity directive update, OR
- New CISO at a utility / water / transit / energy account.

## Touch 1 (Day 0) — CISA KEV tech-stack variant

**Subject:** `<vendor/product> CVE-<id> — the remediation window`

**Body:**

> Hi <first>,
>
> CISA flagged <CVE-id> on <vendor/product> last week. Based on public vendor data, <Company> runs it in production. The remediation deadline is <dueDate>.
>
> The question most utility CISOs we work with hit first isn't "can we patch" — it's "how do we show NERC we closed this exposure gap on a clock."
>
> Sivan, CEO and ex-CISO, built Onyxia specifically for that evidence-on-a-clock problem.
>
> 20 minutes this week? No slides.
>
> Miles

## Touch 1 (Day 0) — NERC CIP variant

**Subject:** `CIP-007 R2 — the evidence gap most utility programs hit`

**Body:**

> Hi <first>,
>
> CIP-007 R2 patch management evidence is the item most utility CISOs I talk to describe as their hardest audit exchange. Not the patching. The evidence chain under a regional entity review.
>
> Sivan, ex-CISO, built Onyxia for exactly that audit-defensibility problem.
>
> 20 minutes next Tuesday? Peer-to-peer.
>
> Miles

## Touch 2 (Day 5) — Bump

**Subject:** `CIP-007 R2 audit trail — short example`

**Body:**

> Hi <first>,
>
> One-page example. The audit trail one of our utility customers uses for their regional entity exchange. No ask if it's not useful.
>
> Miles

## Touch 3 (Day 12) — Breakup

**Subject:** `closing the loop`

**Body:**

> <first>,
>
> Stopping here. The two moments when this usually becomes timely for utility CISOs:
>
> - 45 days before a regional entity audit.
> - Any week the sector gets named in a CISA advisory.
>
> Ping me if either hits.
>
> Miles

## Multi-thread

- Director of OT Security same day (if exists).
- Compliance Manager (CIP program owner) on Day 3.
- COO or VP Operations on Day 7 for utility accounts (OT budget).

## Runs

- YYYY-MM-DD — [[Account]] — outcome

## Cross-references

- [[../../../50_Intel/verticals/critical-infrastructure]]
- [[../../../50_Intel/industry/regulatory-calendar]]
- [[../manufacturing/ciso-first-touch]]
