---
type: audit
audit: leverage-menu
date: 2026-05-05
auditor: The Brain (Claude Code, opus-4-7)
scope: sub-agents + skills + hooks + scheduled jobs + MCPs + plugins
read_only: true
companion_to: 2026-05-05-brain-audit.md
---

# Leverage Menu — 2026-05-05

A menu of compounding moves. Different angle from the morning audit. The morning audit was structural (vault cartography, taxonomy, retrieval, plugins). This is operational: where the system still does manual work, where existing automation is dark, where sub-agents read but never write.

If you skim, read: section A move 1, section B move 1, section D move 1, section F move 1, and the single recommendation at the bottom.

---

## Inventory snapshot (the audit baseline)

### Sub-agents (6 total, in `~/.claude/agents/`)

| Agent | Last edit | Lines | MCPs wired | Writes back to vault? | Real-world usage signal |
|---|---|---|---|---|---|
| onyxia-operator | 2026-04-21 | 140 | 0 (orchestrator only) | yes | Daily — every shift entry-point |
| onyxia-drafter | 2026-05-05 | 510 | Gmail | yes (spine writeback live) | 9 contact files have `current_spine_pain` set — fresh as of today |
| onyxia-hunter | 2026-04-22 | 56 | HubSpot + ZoomInfo (13 tools) | yes (account stubs) | Last hunt log: `2026-05-04` — fired this week |
| onyxia-researcher | 2026-04-22 | 59 | HubSpot + ZoomInfo + Gmail-read + Slack-read + Calendar + Drive (24 tools) | NO — returns text only | No vault write trail |
| onyxia-auditor | 2026-04-22 | 75 | HubSpot read | yes (with ACK gate) | No audit log file at `60_Lessons/audits/` — has it ever fired? |
| the-brain | 2026-05-05 | 86 | none (web only) | yes (audit reports only) | This run is its second |

### Skills (8 total, in `~/.claude/skills/`)

| Skill | Status | Evidence of use |
|---|---|---|
| build-vertical-brief | live | 10 vertical files exist in `50_Intel/verticals/` |
| competitor-battlecard-builder | live | 11 competitor files exist |
| score-prospect-fit | live | called by hunter on every survivor |
| multi-thread-mapper | live | called by hunter on score≥4 survivors |
| weekly-pipeline-review | live | `60_Lessons/2026-W18-review.md` exists |
| regulatory-deadline-tracker | unknown | `50_Intel/industry/regulatory-calendar.md` exists, no fire log |
| **fireflies-debrief-pull** | **DEAD** | Fireflies paused 2026-04-27 per memory. Skill has not been retired or replaced. |
| prompt-master | meta | not for sales motion |

### Slash commands (7 total, in `~/.claude/commands/`)

`avoid-ai-writing.md`, `brainstorming.md`, `deep-research.md`, `operator.md`, `systematic-debugging.md`, `todo.md`, `writing-plans.md`. Only `/operator` is sales-routed. The rest are general-purpose.

### Hooks (in `~/.claude/settings.json`)

All six hook events route to `~/code/agent-mind/capture.sh` for telemetry. No domain-specific hooks. Telemetry lands in `~/ObsidianVault/70_Daily/claude-activity/YYYY-MM-DD.md` (10 days of logs, ~900 events for today). The capture is working; the hooks are not yet enriching the vault.

### MCPs wired (verified via `claude mcp list`)

| MCP | Status | Used by which agent? |
|---|---|---|
| HubSpot | connected | hunter, researcher, auditor |
| ZoomInfo | connected | hunter, researcher |
| Gmail | connected | drafter, researcher |
| Google Calendar | connected | researcher |
| Slack | connected | researcher |
| Google Drive | connected | researcher |
| **Granola** | **connected** | **NONE** — wired 2026-04-27 per memory, zero agents have it in `tools:` |
| **Clay** | **connected** | **NONE** — referenced in autopilot SPEC §4, no agent calls it |
| **n8n-mcp** | **connected** | **NONE** — workflow-management server idle, autopilot Workflow 1 still pending per task `164f9337` |
| Apollo.io | needs auth | none |
| LinkedIn (local) | configured | none — ad-hoc only |
| ElevenLabs | configured | operator can voice-clone but it is not in any agent's tools list |
| mcp-obsidian | configured | none — operator writes via filesystem instead |

### Shift schedule (per `00_Index/CLAUDE.md` lines 165-174)

| Shift | Time | Vault writeback | Evidence found |
|---|---|---|---|
| Morning brief | 07:00 ET wkdy | `70_Daily/YYYY-MM-DD.md` `## Morning brief` | yes — 2026-05-04 + 2026-05-05 confirmed |
| Watchdog | 07:15 ET wkdy | same file `## Watchdog` | yes — present 2026-05-04 + 2026-05-05 |
| Pre-meeting prep | 09:00 ET wkdy | same file `## Pre-meeting prep` | yes — 2026-05-05 confirmed |
| Midday signal | 12:00 ET wkdy | same file `## Midday` | NOT FOUND in any 2026-05-* daily |
| EOD wrap | 16:30 ET wkdy | same file `## EOD wrap` + `60_Lessons/auto-promote/YYYY-MM-DD.md` | morning brief 2026-05-04 said "EOD wrap yesterday: not found in last 15 messages" — gap confirmed |
| Reactivation sweep | Sun 20:00 ET | `50_Intel/signal-log/` | no recent file |
| Weekly synthesis | Fri 16:00 ET | `60_Lessons/YYYY-WW-review.md` | only `2026-W18-review.md` exists; one file in 4+ weeks |

**Reading:** the morning side of the day (07:00 / 07:15 / 09:00) is firing. The afternoon side (12:00 / 16:30 / Sun / Fri) is not consistently firing. The auto-promote-intelligence loop is logged in `60_Lessons/auto-promote/` only on three days: 2026-04-24, 2026-04-29, 2026-04-30. Eight calendar days have passed since the last fire.

### Autonomy plays (5, all `active: false`)

`autonomy-stalled-poc-escalation`, `autonomy-rb2b-hot-signal-book`, `autonomy-inbound-intent-form-reply`, `autonomy-qbr-deck-autodraft`, `autonomy-vault-to-hubspot-sync`. All 5 written 2026-04-22, all 5 still flagged inactive. Two weeks of pre-condition data should have gathered by now. Nothing has flipped on.

---

## Where the brain is failing to compound

The morning audit named one writeback gap (pain-spine selection). I found four more.

1. **Granola MCP is connected but not consumed by any sub-agent.** Granola is the primary post-call source as of 2026-04-27. Granola has the call data; no agent has Granola in `tools:`. Debriefs are still hand-written. Fix: build a `onyxia-debriefer` sub-agent OR add Granola to the operator agent.

2. **Researcher returns text, never writes.** `onyxia-researcher.md` line 24: "Never touch `~/ObsidianVault` write-side. Your output is returned to `onyxia-operator`, which decides what to commit." On every research call, the operator has to re-read, re-format, and re-write. The researcher has the hottest, most carefully sourced findings in the system, and they get re-paraphrased before they hit the vault, losing source citations. The mandate "every observation must land where it will be read again" fails because the researcher writes to chat, not to disk.

3. **Auto-promote-intelligence ran 3 of the last 14 days.** EOD shift is the parent, and EOD shift is intermittent. Patterns from this week's calls (Elevate Textiles, Medusind settlement window, Mitsubishi exec transition) are not getting promoted into `50_Intel/`. The brain is leaking the lessons it bothered to learn.

4. **Reply-intent-parser is specced but the routing is unclear.** Play file at `40_Plays/reply-intent-parser.md` says runs Midday + EOD. Both shifts are intermittent. `60_Lessons/replies/` has files for 7 days in the last 12, several gaps. Replies are landing in Gmail and the vault is not catching them.

5. **Five autonomy plays sit dark.** They were spec'd 2026-04-22 to "flip on after pre-condition data accumulates." Two weeks have passed. The pre-conditions are met for at least two of them (rb2b-hot-signal: ~50 RB2B hits across April; vault-to-hubspot-sync: 51 active accounts ready to sync). The blocker is decision, not data.

6. **Auditor has never written an audit log.** `60_Lessons/audits/` does not exist. Auditor agent file says "weekly mini sweep + quarterly full sweep." The morning audit found 23 schema-A/B accounts, the false-clean MEDDPICC dashboard, and the broken hash-prefix tags. Auditor was supposed to catch all three.

---

## Sub-agent scope quality

**Well-scoped:** drafter (single craft, deep playbook, mandatory writeback), hunter (clear input → vault stub → return), brain (audit-only, output-locked).

**Underscoped:** researcher (no writeback rule = throws away source citations every call), auditor (no fire schedule, no log target = no muscle memory), operator (catch-all for every workflow that doesn't fit a specialist agent — bloat risk).

**Missing entirely:** debriefer (Granola → vault), reply-classifier (Gmail → vault), promoter (daily-note → 50_Intel), shift-runner (the cron-style executor that fires the 6 shifts as a dedicated agent rather than as anonymous "scheduled triggers").

**Boundaries to clarify:** the auditor and the brain overlap at the edges. Brain is "strategic systems design." Auditor is "tactical drift fixes." But the morning audit found 6 items the auditor should have surfaced first. Either auditor needs a real cron, or its work needs to roll into a hardened EOD/Friday shift.

---

## A. New sub-agents to build

### A1. onyxia-debriefer (Granola → vault) — P0, S effort

**What it does:** subscribes to Granola transcripts via the Granola MCP. For every meeting that ended in the last 24h, finds the matching `30_Meetings/YYYY-MM-DD-{company}-prep.md` file, generates a structured debrief stub, writes the prep→debrief wikilink both ways, updates the account file's Timeline, updates touch-tracker `reply_state` and `next_touch_plan`, and runs the methodology-pointer section per the morning audit's P0-2 spec.

**Why it compounds:** every debrief hand-write is ~60 minutes (Elevate Textiles 2026-05-05 was an hour). This sub-agent makes that ~5 minutes (review + accept). At ~5 calls/week, that is 5 hours/week saved AND the vault stops missing debriefs (7 of 14 prep notes are currently undebriefed). Every debrief that lands is fuel for auto-promote-intelligence + measurement-log + closed-won-patterns + canon. The methodology brain compounds on debrief volume.

**Effort:** S. Granola MCP is already connected. The agent file is ~80 lines, mirroring drafter's pre-flight discipline.

**Payoff tier:** P0. This is the single biggest leak in the brain — confirmed by both audits today.

**Implementation approach:** new sub-agent. Mandatory writeback gate (same pattern as drafter's spine-pain writeback). No new MCP needed.

### A2. onyxia-promoter (daily-note → 50_Intel, replaces auto-promote-intelligence cron) — P0, M effort

**What it does:** dedicated agent that runs the auto-promote-intelligence loop. Reads modified files in last 24h, scans for cross-account patterns, proposes appends to `50_Intel/methodology/objections.md`, `competitors/*.md`, `icp.md` triggers, `winning-openers.md`. Writes proposal to `60_Lessons/auto-promote/YYYY-MM-DD.md` AND posts to `#miles-ai-ops` for ✅. On approval, executes the append. On rejection, logs reason.

**Why it compounds:** decouples promotion from EOD shift fragility. EOD ran 3 of 14 days. A dedicated agent invoked by either Friday synthesis OR ad-hoc OR a hardened cron means promotion fires on cadence regardless of operator availability. The methodology brain compounds because the synthesis layer fires reliably.

**Effort:** M. Existing play file at `40_Plays/auto-promote-intelligence.md` is already the spec. Half-day to convert spec into a sub-agent definition.

**Payoff tier:** P0. Without this, the methodology brain calcifies — the morning audit found exactly this (the methodology folder is a peninsula at 3 inbound links each, dead-end on outbound).

**Implementation approach:** new sub-agent. Wired into the EOD shift play AND callable ad-hoc via slash command `/promote`.

### A3. onyxia-replier (Gmail → vault + draft) — P1, M effort

**What it does:** the reply-intent-parser play converted into a sub-agent. Polls Gmail every shift (or hooks on UserPromptSubmit to scan since last run), classifies each reply against the 10 buckets in `40_Plays/reply-intent-parser.md`, writes to `60_Lessons/replies/YYYY-MM-DD.md`, generates a branch-default Gmail draft via the drafter sub-agent, posts to `#miles-ai-ops`.

**Why it compounds:** today, replies trigger an ad-hoc human read. The classifier and the draft-generator never get the same reply twice. With the agent, every classification feeds `measurement-log.md` (`reply_y_n` field is a stub); over time, reply-pattern accuracy improves and the drafter learns which tones convert which replies. The reply→draft loop becomes a compounding lookup.

**Effort:** M. ~150-line agent file plus chained call into drafter.

**Payoff tier:** P1. Important but the debriefer and the promoter both feed this loop, so build them first.

### A4. onyxia-shifter (cron executor) — P1, S effort

**What it does:** thin sub-agent invoked by the scheduling layer at 07:00, 07:15, 09:00, 12:00, 16:30, Fri 16:00, Sun 20:00. Reads the relevant `40_Plays/shifts/{shift}.md`, dispatches to the right sub-agent (operator for morning brief, debriefer for EOD, promoter at end of EOD, replier at Midday + EOD, weekly-pipeline-review skill on Friday). Writes a one-line "shift fired" log to `70_Daily/{date}.md`.

**Why it compounds:** today, every shift is its own ad-hoc invocation, and Watchdog's job is to detect when one didn't fire. Centralizing dispatch makes the schedule legible — one file owns the run order, missing fires are loud, watchdog becomes trivial. The schedule stops being aspirational.

**Effort:** S. Most of the shift logic already exists; this is glue.

**Payoff tier:** P1. Ships the schedule from "documented" to "executed."

---

## B. Existing sub-agents to harden

### B1. onyxia-researcher: add structured writeback gate — P0, S effort

**What it does:** flip the "never touch vault write-side" rule to "MUST write findings to a deterministic vault path." For account research → `10_Accounts/{Company}.md` Timeline section + a `## Research notes ({date})` block. For competitive intel → `50_Intel/competitors/{tool}.md` (use battlecard skill). For regulatory → `50_Intel/industry/regulatory-calendar.md`. Source citations preserved. The operator stops re-paraphrasing — it just verifies and links.

**Why it compounds:** every research call adds verifiable, dated, sourced intel to the vault permanently instead of disappearing into a chat-window paraphrase. The hottest intel becomes the most durable intel. The auto-promoter has more raw material, the drafter has more sourced hooks, the morning brief has fresher trigger context.

**Effort:** S. ~30-line addition to the agent file. Output shape is already structured markdown; just make it write.

**Payoff tier:** P0. Closes one of the four newly-found writeback gaps directly.

**Implementation approach:** sub-agent edit. Add the same writeback-confirmation pattern the drafter uses for spine-pain.

### B2. onyxia-auditor: actually fire it, with a log — P1, S effort

**What it does:** wire auditor into the Friday synthesis shift (mini sweep) and the first business day of each quarter (full sweep per `40_Plays/quarterly-self-audit.md`). Output goes to `60_Lessons/audits/YYYY-MM-DD.md` (this folder does not exist today — first run creates it). Findings post to `#miles-ai-ops` with ✅/👎 reaction gate.

**Why it compounds:** the audits I ran today (this file + the morning structural audit) are doing the auditor's job at opus pricing. The auditor at sonnet does the tactical sweep weekly; the brain at opus does the strategic audit quarterly. Cost-correct. And the schema drift, false-clean dashboard, and tag pollution would have surfaced two weeks ago instead of today.

**Effort:** S. ~10-line addition to the agent file (output target + ACK gate spec) + add a Friday-synthesis hook in the shift play.

**Payoff tier:** P1.

### B3. onyxia-drafter: add Granola transcript reader — P1, S effort

**What it does:** when drafting a `post_meeting_follow_up` or any draft to a contact who has a Granola transcript in the last 14 days, drafter reads the transcript via Granola MCP and pulls a verbatim quote. The "follow-up within 24 hours" Gong pattern (drafter doc line 440) requires verbatim recall; today it depends on the operator pasting the transcript in.

**Why it compounds:** post-meeting follow-ups become more verbatim, more concrete, more reply-likely. The 9-criteria scoring rubric will rate these higher. Replies feed measurement-log, which feeds canon.

**Effort:** S. Add Granola MCP to drafter's `tools:`, ~20-line procedure addition.

**Payoff tier:** P1.

### B4. onyxia-hunter: stop creating the duplicate `30_Contacts/staged/` folder — P2, S effort

**What it does:** hunter's stage-2-3-contacts step writes to `30_Contacts/staged/`. Per CLAUDE.md, contacts live at `20_Contacts/`. The morning audit already named this. Fix at the agent level so it stops recurring.

**Why it compounds:** every hunt fires correctly. Taxonomy stays clean. Auditor has less to flag.

**Effort:** S. One-line edit in the hunter's standard-loop step 9.

**Payoff tier:** P2 (already covered as QW-2 in morning audit; listing here so the agent fix gets bundled with the file move).

---

## C. New skills to build

### C1. granola-debrief-pull (replaces fireflies-debrief-pull) — P0, S effort

**What it does:** parametrized skill called by the debriefer agent. Input: meeting date OR Granola transcript ID OR account name. Output: structured debrief in `30_Meetings/{date}-{company}-debrief.md` with verbatim quotes, action items, MEDDPICC slot updates, methodology pointers section.

**Why it compounds:** skills are reusable across agents and slash commands. With this skill, `/operator "debrief the Elevate call"` works. Drafter uses it for follow-up quote retrieval. Auditor uses it for "deals with no debrief" sweeps.

**Effort:** S. The fireflies skill at `~/.claude/skills/fireflies-debrief-pull/SKILL.md` is the structural template. Swap Fireflies API for Granola MCP. Retire (archive, do not delete) the fireflies skill.

**Payoff tier:** P0.

### C2. spine-pain-writeback (extracted from drafter) — P1, S effort

**What it does:** the "Spine-pain writeback" procedure that drafter does inline today (drafter doc lines 272-300) becomes its own skill. Drafter calls it. The auditor can call it for backfill on the 9-of-51 active contacts that have spine writeback today (per morning audit, only 9 contact files have `current_spine_pain` set).

**Why it compounds:** backfill becomes scriptable. New sub-agents (replier, debriefer) can chain it. Contract is testable in isolation.

**Effort:** S. ~50-line skill file extracted from drafter.

**Payoff tier:** P1.

### C3. shift-runner (skill not agent — covers the routine bits) — P2, S effort

**What it does:** wraps the read-CLAUDE.md → read-MOC_This_Week → read-product-files → read-latest-lesson session ritual into a callable skill. Invoked at the top of every shift.

**Why it compounds:** the ritual is in CLAUDE.md and the operator agent and the morning-brief shift play. Three places. Drift target. Centralize.

**Effort:** S. ~40-line skill.

**Payoff tier:** P2.

---

## D. Hooks + automation

### D1. PostToolUse hook — auto-link new account/contact files into MOC — P1, S effort

**What it does:** when any agent writes a new file to `10_Accounts/` or `20_Contacts/`, a PostToolUse hook fires a small script that appends the file to `00_Index/MOC_Pipeline.md` index list and adds the canonical wikilinks (account ↔ contacts ↔ vertical ↔ persona ↔ methodology). Closes the cross-link debt the morning audit named (only 1/51 account files links to methodology; 0/75 contact files link to personas).

**Why it compounds:** every new note ships pre-threaded. The threading debt stops accruing while the backfill (P0-2 in morning audit) clears the existing 51 deals.

**Effort:** S. Hook script is ~30 lines bash + an Obsidian-API write call (or filesystem regex append).

**Payoff tier:** P1.

**Implementation approach:** hook in `~/.claude/settings.json` PostToolUse with matcher `Write|Edit` and path-filter on the two folders.

### D2. SessionStart hook — read CLAUDE.md + memory files automatically — P2, S effort

**What it does:** every Claude Code session, hook auto-reads `00_Index/CLAUDE.md`, the memory files referenced in `MEMORY.md`, and the latest weekly review. Drops a summary into the session context so the operator doesn't waste a turn re-reading.

**Why it compounds:** removes the "first move every session" cost from the operator. The session ritual becomes an environment fact, not a discipline.

**Effort:** S. ~20-line bash script.

**Payoff tier:** P2. Quality-of-life, not unblocking.

### D3. Stop hook — append touch-tracker writes from the session — P2, S effort

**What it does:** on session end, scan the session's tool calls for any Gmail draft creation and ensure each got a touch-tracker row. If not, append. (Today this is in the drafter's manual procedure; if drafter is interrupted, the row is missed.)

**Why it compounds:** touch-tracker becomes the durable measurement layer. Drafter is reliable but interrupted sessions leak. Stop hook closes the leak.

**Effort:** S.

**Payoff tier:** P2.

### D4. Real shift-cron via launchd or Claude Code background agent — P0, M effort

**What it does:** the documented schedule (07:00 / 07:15 / 09:00 / 12:00 / 16:30 / Fri 16:00 / Sun 20:00) needs an actual executor. Today the cadence depends on Miles initiating a session OR a manual scheduled trigger. Evidence: EOD wrap missed several days, Midday signal not found in any 2026-05-* daily, only 1 weekly review in 4 weeks.

**Why it compounds:** every shift firing reliably means the brain self-updates without operator presence. Auto-promote runs. Replier classifies. Debriefer pulls Granola. Auditor sweeps Friday. The intelligence loop closes from a cycle Miles drives manually to a cycle the system drives autonomously.

**Effort:** M. Half-day to set up launchd plist files (one per shift), verify the dispatch agent is callable from cron, smoke-test each shift.

**Payoff tier:** P0. The single most overdue automation.

**Implementation approach:** macOS launchd plist files in `~/Library/LaunchAgents/`, each invoking `claude --resume` or `claude -p "{shift prompt}"` with the right shift play context. Or hand off to n8n cron triggers (n8n is already wired).

---

## E. MCP + integration gaps

### E1. Wire Granola MCP into onyxia-debriefer (and drafter) — P0, S effort

Already covered as A1 + B3. Restating because it is the single most overdue MCP wire-up.

### E2. Wire n8n-mcp into the operator for autopilot Workflow 1 — P1, M effort

**What it does:** n8n is already a connected MCP, n8n cloud instance is live (`milesonyxia.app.n8n.cloud`). Autopilot Workflow 1 (Daily Prospect Discovery, task `164f9337` ID 4) is blocked on HubSpot custom properties (task ID 3, `pending`). Unblock task 3, build Workflow 1, and the morning brief moves from "operator runs the hunt-script" to "n8n handed me 30 ICP-scored prospects at 06:00, operator triages."

**Why it compounds:** prospecting volume scales without operator turn-time. Hunter agent goes from 30/week to 100/week capacity. The bottleneck moves from discovery to triage, which is where Miles's judgment is highest-value.

**Effort:** M. The HubSpot custom-property step is ~1 hour. Workflow 1 build is ~half-day. Integration smoke test ~1 hour.

**Payoff tier:** P1.

### E3. Wire Clay MCP into hunter for LinkedIn enrichment — P2, S effort

**What it does:** Clay is connected, no agent calls it. Per autopilot SPEC §4, Clay covers LinkedIn (headlines, recent posts, talks, podcasts) — the input to Personalization Level 4 in the drafter's ladder. Today, Level 4 personalization requires manual LinkedIn opens.

**Why it compounds:** Level 4 personalization is the dominant predictor of cold reply. Clay-driven enrichment makes Level 4 the default rather than the exception.

**Effort:** S. Add Clay tools to hunter's `tools:`, add a Clay step after ZoomInfo enrichment.

**Payoff tier:** P2.

### E4. Re-auth Apollo OR drop it — P2, S effort

Apollo MCP shows "Needs authentication" as of `~/.claude/mcp-needs-auth-cache.json` (timestamp 2026 mid-April). Either re-auth and use as a third enrichment source, or remove from the inventory so future agents stop assuming it.

**Effort:** S.

**Payoff tier:** P2.

### E5. Build a vault-write MCP for hooks — P2, M effort

**What it does:** the `mcp-obsidian` MCP server is in `~/.claude/settings.json` but no agent invokes it. Hooks (D-section) write via filesystem; an Obsidian API server would let hooks update active notes without conflicting with Obsidian's edit buffer.

**Why it compounds:** hook writes stop colliding with open Obsidian sessions. Race conditions disappear.

**Effort:** M.

**Payoff tier:** P2. Only matters if hooks become heavy.

---

## F. Architectural shifts

### F1. Flip 2 of 5 autonomy plays to active — P0, S effort

**What it does:** all five `40_Plays/autonomy-*.md` are flagged `active: false`. Two have met their stated pre-conditions:
- `autonomy-rb2b-hot-signal-book` precondition is "50+ rb2b hits with fit score and 90-day outcome." RB2B feed has been live since at least mid-April; per morning brief 2026-05-04 the feed went dark since "May 15, 2025" — actually that may itself be a signal that the integration broke. Validate first, then enable.
- `autonomy-vault-to-hubspot-sync` precondition is "MEDDPICC slots filled on 20+ active accounts." Per morning audit, 28 of 51 accounts have Schema-C MEDDPICC fields. Threshold cleared.

**Why it compounds:** every autonomy play that flips on takes one routine workflow off Miles's plate. RB2B-hot-signal alone unblocks "qualified visitor → meeting booked" without a turn. Vault-to-HubSpot sync stops the manual reconciliation tax.

**Effort:** S per play. Flip the flag, set the rollback criteria, watch one cycle.

**Payoff tier:** P0.

### F2. Move researcher from "return text" to "write structured intel files" — P0, S effort

Already covered as B1. Listing here because it is also an architectural shift in agent contract.

### F3. Consolidate operator's sprawl: spin out shifts as their own agents — P1, M effort

**What it does:** today, onyxia-operator is the entry point for everything. The shift plays at `40_Plays/shifts/*.md` say "fired by scheduled agent — runs onyxia-operator subagent with this prompt." That makes operator a god-agent. Splitting morning-brief, midday, EOD into their own thin agents (or at least their own slash commands) tightens scope and makes shift-specific tuning possible without bloating the operator system prompt.

**Why it compounds:** scope-clean agents are testable. Operator stops being the kitchen sink. Edits to one shift don't risk regressions in another.

**Effort:** M. Half-day to extract 6 shift agents from operator.

**Payoff tier:** P1.

### F4. Retire the Fireflies skill — P2, S effort

`~/.claude/skills/fireflies-debrief-pull/SKILL.md` references a paused integration. Retire to `~/.claude/skills/_archived/` so future agent searches don't surface it. Replace with the granola-debrief-pull skill (C1).

**Effort:** S.

**Payoff tier:** P2. House-cleaning.

### F5. Make `60_Lessons/audits/` and wire auditor's first run — P2, S effort

Folder does not exist. Auditor agent says it writes there. First run will create it; first run has not happened. Schedule it.

**Effort:** S.

**Payoff tier:** P2 (already covered in B2).

---

## Single recommendation for next week

**Build onyxia-debriefer (A1) and ship a real shift-cron via launchd (D4) in the same week.**

Pick those two together because they are both P0, both relatively small, and they combine into the largest single compounding lift in the brain right now.

The case: today, the brain's biggest leak is post-call. A meeting ends in Granola; the data sits there; if the operator is not present to invoke a debrief, the call becomes a memory. The morning audit confirmed 7 of 14 prep notes have no debrief. This evening's audit confirmed Granola MCP is connected but no agent has it wired. The cost is real — Elevate Textiles 2026-05-05 took an hour to hand-write; Spire Ortho, Cyber Diligent, AKUVO POC, Armstrong/TMF, IVISA all sit past the 8-day debrief half-life with nothing on file.

A debriefer agent (A1) closes the post-call gap. A shift-cron (D4) fires it on schedule whether Miles is present or not. Together: every meeting in Granola produces a vault debrief within 24 hours, the touch-tracker updates itself, the Timeline updates itself, and the methodology brain finally compounds because it gets fed daily instead of weekly. Auto-promoter (A2) and replier (A3) are next-week-after-that work; they all depend on this foundation firing.

Effort: A1 is S, D4 is M. Half-day for the agent, half-day for the cron, one day to smoke-test against tomorrow's calendar. By Friday, every meeting from Wednesday onward has a debrief on disk before EOD.

If you only ship one thing: A1. If you ship two: A1 + D4. If three: add B1 (researcher writeback) so next week's intel research compounds the same way.

---

## Surprise findings

1. **Claude activity log is 900 events/day.** `~/ObsidianVault/70_Daily/claude-activity/2026-05-05.md` already has 900 hook-captured events for today alone, on top of `mind.log` at 10K+ events. The telemetry plumbing is working; nothing reads from it. There is a latent intelligence layer here: which sub-agents fire when, which tool-call patterns Miles repeats, which files get touched daily. Could feed a future "agent self-improvement" loop that reads its own logs.

2. **`copilot/` folder is 15 prompts that mirror sub-agent functionality.** Risk of two stacks of "how to do sales work" diverging — the copilot prompts and the agent system prompts. Worth picking one stack as canonical.

3. **The drafter's spine-pain writeback is live AND working.** 9 contact files have `current_spine_pain` set as of today. That's the 2026-05-05 P0-2 fix from the morning audit shipping in real time. Confirms the writeback pattern works; replicate it for debrief writeback (A1) and research writeback (B1).

4. **n8n is built and idle.** Cloud instance live, MCP wired, four documented workflows pending. Two weeks of unused infrastructure. The blocker is HubSpot custom property creation (task ID 3) — a 1-hour job that gates ~3 weeks of automation lift.

5. **Fireflies skill still installed even though Fireflies is paused.** Will silently mislead the next agent that searches for "debrief" + "transcript". Retire it.

6. **Auditor agent has likely never written a real audit.** No `60_Lessons/audits/` folder exists. The two audits today (morning structural + this leverage menu) are doing the auditor's job at brain pricing. Cost-correct that.

7. **Watchdog alerts but no one acts on the alerts.** 2026-05-04 daily note's Watchdog section says "Morning brief: posted at 07:25 ET (25 min late, outside 06:55-07:15 window)" and "EOD wrap yesterday (2026-05-03): not found in last 15 messages." Watchdog is detecting failures correctly. Nothing is wired to fix them.
