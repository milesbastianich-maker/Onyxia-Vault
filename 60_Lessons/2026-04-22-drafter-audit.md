---
type: lesson
date: 2026-04-22
session: 2026-04-21-2343-session
tags: [lesson, drafter-audit]
---

# Drafter Audit + Hardening — 2026-04-22

## 1. Current state

**Sends in the last 7 days:** ~125+ outbound.
- **Register-A cold cohort (15 sends):** healthcare + fins + defense + med-device. 2026-04-21 and 2026-04-22. Draft score ~4-5/5. Personalization Level 4 (individual-specific, with verbatim hooks — settlement amount, exec hire date, employee count, $84B asset size). Reply rate TBD, 24-48h window still live.
- **Mfg cohort (6 sends):** Nordson, Mustang Cat, Milacron, Biomerics, Graco, Klein Tools. 2026-04-22 AM. Draft score 3-4/5. 2 shipped with em-dash violations (Biomerics, Graco). Reply window live.
- **Register-B mail-merge cohort (≥100 sends):** 2026-04-21 PM. 9 hook templates × 10-15 recipients each. Identical body with [First] and [Company] swapped. Personalization Level 2 (role-aware generic). Miles flagged "awful, all the same, not personalized" on 2026-04-22. Policy locked: do-not-bump-unless-trigger.
- **Live deal threads (6):** MHIA NDA blocker, IVISA meeting booked, Rocket/Ada/HP Pappas follow-ups, People Inc paused.

**Average ai_writing_score across the corpus:** 3.5/5 (weighted by volume — Register-B cohort drags it down significantly). Stripped of Register-B: 4.2/5. The Register-B cohort alone scores ~2/5 per avoid-ai-writing detect mode.

**Top 5 most-flagged AI tells across the corpus:**
1. Template-phrase mail-merge: "tend to inherit a toolbox that grew faster than the playbook" (Register-B hook, 10+ instances)
2. Template-phrase: "Twenty-plus tools, three that overlap, two that nobody's quite sure are still live" (Register-B, 10+ instances)
3. Em dashes in agent-written prose (agent-drafts only, Biomerics + Graco sends)
4. "specifically" / "exactly that X moment" hedge pattern (5 of 6 mfg drafts had a structurally identical Sivan sentence — mini-Register-B I created)
5. False-breadth constructions: "partners, clients, auditors, and regulators" (Register-B "proving the security program" variant, 5+ instances)

**3 confirmed bounces in Register-B cohort:**
- Symphony / Mitchell Hibbs
- Papaya Global / Aaron Slutsky
- Mutual of America / Mary McCarren

## 2. Harden deltas

### `~/.claude/agents/onyxia-drafter.md` — rewritten in place

**Added:**
- `<role>` framing: reply-rate is the only metric, never pitch the product.
- Who-you're-writing-as block: Miles's biographical voice (SDR/AE path, Beyond Identity, GuidePoint/Apono partners, Brad/Sivan reporting line, Miles vs Basti signoff selection).
- Tone calibration: 4-tier (default / warm intro / F500 CISO / SecOps).
- Mandatory context gathering: 18 real vault paths, translated from reference-spec paths (e.g., `Resources/Onyxia/product-positioning.md` → `50_Intel/product/positioning.md`, `Projects/[Account]/hot.md` → account Timeline section).
- ICP persona summaries (CISO / GRC / SecOps) with pain language + reply/delete triggers.
- **5-level personalization ladder as a hard gate.** Level 3 minimum. If draft can't hit Level 3, refuse to draft and return a research request.
- **Mandatory source-citation HTML comment at the top of every draft.** `<!-- Personalization source: ... -->`. If no citable source, refuse.
- 7 email-type playbooks: cold_first_touch, day_5_bump (30-40 words, new info mandatory), day_12_breakup (40-60 words, no hard ask), post_meeting_follow_up, reply_to_reply, event_invite, warm_intro_follow_up.
- Pre-send checklist (14 items) — absorbs exclusion-list check, banned-phrase check, framework-version check, rapport-level signature check, bump-contains-new-info check.
- Banned-phrases quick reference referencing `forbidden-words.md` (does NOT duplicate that file).

**Preserved verbatim:**
- Frontmatter (name, description, model, tools).
- 8-criteria scoring rubric from `draft-scoring.md`.
- `avoid-ai-writing` skill invocation before `create_draft`.
- Absolute prohibitions (never send, never fabricate, never invent customer names).
- Measurement-log row schema (extended with personalization_level + ai_writing_score + ai_tells_flagged fields).

**Gates that now fire:**
1. Personalization ladder Level 3+ check (NEW).
2. Source-citation HTML comment presence (NEW).
3. `avoid-ai-writing` detect-mode score ≥4 (existing, now enforced).
4. 8-criteria rubric score ≥4 (existing, now enforced).
5. `forbidden-words.md` phrase grep zero hits (existing, now enforced).
6. Em-dash count zero in agent-written prose (existing, hard fail).
7. Pre-send checklist all 14 items pass (NEW).
8. Exclusion-list grep zero hits (existing, hard fail).
9. Sivan peer-call saturation cap 2-3/week (existing, applies to peer-call-tier CTAs only).

**Any draft below score 4 on either rubric = operator returns a revise-request to the caller. The Gmail `create_draft` call never fires on a sub-standard draft.**

## 3. Touch-tracker seeded

File: `~/ObsidianVault/50_Intel/methodology/touch-tracker.md`

**Row counts:**
- 🔴 Priority (next 48h): 3 rows (MHIA NDA blocker, IVISA Monday meeting, Rocket follow-up)
- 🟡 Priority (next 7d): 9 rows (Ada, HP, People Inc, Nordson, Mustang, Milacron, Biomerics, Graco, Klein Tools)
- 🟢 Register-A cold cohort (touch 1 pending reply): 16 rows
- 🚫 Register-B cohort (DO-NOT-BUMP flagged): ≥100 rows, 3 bounces tracked
- Live deals in flight: 6 rows (MHIA, IVISA, Rocket, Ada, HP, People Inc)

Sort order: `next_touch_date` ASC. Auto-update runbook documented but **not live** — awaiting Miles ✅ to flip daily EOD scan on.

## 4. Next touches queued

**None as Gmail drafts tonight.** Reason: all 22 cold sends are <5 days old (earliest is 2026-04-21, today is 2026-04-22). Day-5 bumps trigger 2026-04-26 through 2026-04-28. Queuing tonight would create drafts that sit for 4+ days and drift from the personalization source's freshness.

**Bump/breakup templates (per vertical) — being written by sub-agent right now.** 4 verticals × (1 bump + 1 breakup) = 8 new templates appending to the existing sequence files. Will update this report with the sub-agent's deliverables when complete.

**Research requests (Level-3 gated drafts that need human input before they can ship):**
- Glenn Haddock / Mustang Cat: email unresolved. ZoomInfo COMPANY_ONLY_MATCH. Recommend routing via David Young (22-year tenure at Mustang Cat) as warm-intro, or LinkedIn connect note.
- No Register-B cohort re-touches queued (policy lock per Miles: do-not-bump-unless-trigger).

## 5. Highest-conviction asks for Miles

1. **Review Lucas Parker's MNDA** (Mitsubishi Heavy Industries America). Sent 2026-04-14, Lucas bumped 2026-04-20 asking for review, still unacknowledged. $75K active deal. Miles needs to either (a) redline and reply, (b) send to Onyxia legal, or (c) reply with an ETA. Even an ETA reply stops the thread from cooling. Do this first tomorrow.

2. **Prep for IVISA / Susan Lloyd meeting Monday 2026-04-27 2pm CT.** She booked the time herself, but flagged her tooling stance: "'if absolutely needed' before purchasing." Need a discovery-call angle that doesn't trigger that gate early. Reference `50_Intel/methodology/discovery-framework.md` (Convergence Discovery, Phase 1).

3. **Unlock HubSpot write access.** Current MCP is read-only. Autonomy matrix permits contact-create + activity-log, but the tool surface doesn't expose it. Either authorize MCP write scope or set up an n8n webhook workflow for HubSpot writes. Without this, the 6 mfg accounts (Nordson, Mustang, Milacron, Biomerics, Graco, Klein Tools) + their 16 contacts + the 22 cold-outbound activities stay uncommitted to CRM. Territory risk: someone on the team could work the same accounts without knowing Miles is live.

4. **Flip `auto-update runbook` for touch-tracker on or off.** Daily EOD Gmail scan to update `reply_state` + `reply_intent`. Without the flip, the tracker needs manual updates. With the flip, the EOD shift handles it. Low blast radius (reads only, writes only the tracker file).

5. **Confirm: Register-B cohort — permanent blacklist or allow trigger-event re-engage?** Currently policy says do-not-bump-unless-trigger. If you want permanent blacklist (never re-touch any of the ~100 recipients), say so and I update the touch-tracker rows to `excluded`. If trigger-event-re-engage is fine, no change needed.

## 6. Measurement delta

**Session t-zero for the new rubric (2026-04-22):**
- ai_writing_score mean (all sends, weighted by count): 3.5/5
- ai_writing_score mean (Register-A only): 4.2/5
- Reply rate: 0 of 22 Register-A cold touches have replied yet (too early — 24-48h window still open)
- Reply rate (Register-B cohort): 0 of ~100. 3 bounces. Rest silent.
- Meetings booked from this week's cold outbound: 0
- Meetings booked from warm/live-thread work: 1 (IVISA, Monday 2pm CT)

**Baseline to measure against:** Register-B cohort's ai_writing_score ~2/5 is the floor. Register-A cohort at 4.2/5 is the ceiling today. Target: every future send at 4.5/5 or higher via the hardened drafter's 9 gates.

**Reply-rate baseline (industry reference):** 3-8% on cold-enterprise-CISO is decent. Below 3% = copy problem or targeting problem. Above 8% = winning. Track weekly in `weekly-pipeline-review` skill output.

## Cross-references

- [[../50_Intel/methodology/touch-tracker]]
- [[../50_Intel/methodology/draft-scoring]]
- [[../50_Intel/product/winning-openers]]
- [[../50_Intel/product/forbidden-words]]
- [[../50_Intel/product/power-phrases]]
- [[../../.claude/agents/onyxia-drafter]]
- [[../10_Accounts/Mitsubishi Heavy]] — MHIA NDA blocker
- [[../40_Plays/sequences/]] — vertical Day-5/Day-12 templates landing via sub-agent
