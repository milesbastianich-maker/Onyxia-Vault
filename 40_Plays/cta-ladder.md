---
type: play
subtype: rule
trigger: applied on every draft
vertical: all
created: 2026-04-22
tags: [play]
---

# CTA Ladder

Three tiers. Pick by signal strength, not by default. Every outbound draft picks one.

## The three tiers

| Tier | Ask | Example phrasing | When to use |
|---|---|---|---|
| **Passive** | "Curious if on your radar" | "Curious if that's on your radar as you're setting strategy." | No prior thread. Cold. Signal ≥3 but no named trigger event. |
| **Specific** | "15 min next Tues" | "Worth 15 minutes next Tuesday or Thursday to compare notes?" | Named trigger event (new CISO, breach, compliance deadline, M&A). Fit score ≥4. |
| **Peer-call** | "Sivan + 20 min" | "Not a demo. 20 minutes with Sivan (our CEO + ex-CISO). She built this for this moment." | CISO persona + Tier 1 ICP + trigger event ≤90 days old. Highest conversion lever per [[../50_Intel/playbook/closed-won-patterns]]. |

## Rule for picking

Score the prospect signal. Map to tier.

```
if persona in {CISO, VP Security} AND trigger_event_age <= 90 days AND tier_1_icp:
    cta = "peer-call"
elif named_trigger_event OR fit_score >= 4:
    cta = "specific"
else:
    cta = "passive"
```

## Why not always peer-call

Overuse burns the asset. Sivan is a finite resource. [[sivan-peer-intro]] lists 6 active runs as of 2026-04-21. Saturate Sivan and the conversion signal degrades.

Rule of thumb: cap peer-call CTAs at 2-3 new ones per week.

## Why not always passive

"Curious if on your radar" converts at the lowest rate. Use it when we have no real hook. It acknowledges the cold call for what it is.

## Where this gets logged

Every draft logs its `cta_tier` in [[../50_Intel/methodology/measurement-log]]. Weekly synthesis re-ranks conversion by tier + persona combo.

## Anti-pattern

Two CTAs in one email. Pick one. The ladder is about choosing the right rung, not stacking them.

## Examples from existing plays

- [[sivan-peer-intro]] uses peer-call tier by design.
- Trigger-event hunt opener defaults to specific.
- Reactivation sweep opener defaults to passive on first touch, escalates to specific if trigger event lands.

## Runs

Every draft this rule touches tags the chosen tier in [[../50_Intel/methodology/measurement-log]]. Appends here only when a tier choice is reviewed post-reply.

| date | account | tier picked | reply y/n | note |
|---|---|---|---|---|
