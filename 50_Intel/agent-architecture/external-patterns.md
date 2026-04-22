---
type: intel
subtype: agent-architecture
source: public research, session 2026-04-21
created: 2026-04-21
tags: [intel, agent-architecture]
---

# External Patterns: Leading AI Sales Agents & Autonomous Systems

## Why this file exists

The AI sales agent landscape has exploded in 2025 (Regie, 11x, Clay, Artisan) with established deep-research patterns (OpenAI, Perplexity, Anthropic) and open orchestration frameworks (LangGraph, crewAI, AutoGen). This document captures verified patterns Miles's Onyxia operator should adopt or steal without reimplementing the wheel.

## Architectural patterns observed across leading agents

### 1. Intent Classification at Inbox Scale

**Definition:** Autonomously parse inbound emails/replies, classify intent (interested, objection, out-of-office, not-interested, auto-reply), extract sentiment and urgency, route to appropriate agent or escalate.

**Who uses it:** Regie.ai Auto-Pilot, 11x Alice, Artisan Ava, Outreach AI (Nia).

**Why it matters:** Regie reports intent classification at >95% accuracy reduces SDR triage work by 80%. Allows autonomous follow-up decisions without human eyes on every reply. Signal velocity matters: first reply often comes within 24h; delay kills momentum.

### 2. Dynamic Sequencing (Adaptive Touch Patterns)

**Definition:** Modify outreach cadence, channel, and tone in real-time based on engagement signals. If email opens but no reply after 3 days, switch to LinkedIn or phone. If objection detected, auto-escalate or attempt rebuttal.

**Who uses it:** Regie.ai, Clay (autonomous agents), Artisan Ava (80% of work automated).

**Why it matters:** Static sequences kill deals. Regie reports engagement improves measurably when sequences adapt to warm vs cold cohorts, reply patterns by vertical, and time-of-day opens. Onyxia currently sends fixed sequences; dynamic sequencing multiplies velocity.

### 3. Multi-Agent Task Delegation (Orchestration)

**Definition:** Decompose complex sales workflows (research → enrichment → messaging → follow-up) into specialized agents, route tasks hierarchically or by supervisor agent. Crew coordinates.

**Who uses it:** 11x rebuilt Alice as multi-agent system, Clay agents, Artisan pipeline splits research/drafting/booking, crewAI framework, LangGraph supervisor pattern, AutoGen group chat.

**Why it matters:** Single monolithic agents hallucinate or lose context. 11x's multi-agent redesign improved Alice's personalization depth (prospect research now includes 50+ data sources per contact). Onyxia could split: research-agent, enrichment-agent, drafting-agent, reply-parser-agent, meeting-setter-agent.

### 4. State Management & Checkpointing

**Definition:** Persist agent state (current task, context window, conversation history) across multiple invocations. Enable resumption from failure, multi-session continuity, and safe parallelism.

**Who uses it:** LangGraph (reducer-driven state with TypedDict), AutoGen (serialization/deserialization), Anthropic Claude SDK (context compaction), Cognition Devin (DeepWiki codebase state).

**Why it matters:** Long-running agent tasks (12+ month deal cycles) will exhaust context or fail. LangGraph's checkpointing ensures agent can pause, resume, and branch without losing context. Onyxia's 7-shift architecture relies implicitly on vault state; explicit checkpointing would enable parallel agents safely.

### 5. Iterative Planning & Feedback Loops

**Definition:** Agent plans high-level strategy, executes one step, observes results, adjusts plan. Feedback loop continues until goal or abort condition.

**Who uses it:** OpenAI Deep Research (reinforcement learning trained on multi-step research), Devin (interactive planning before execution, 1000s of sequential decisions), Perplexity Deep Research (iterative retrieval, refines plan as new insights emerge), Claude Code (ReAct loop: reason → act → observe → repeat).

**Why it matters:** One-shot planning fails. Deep Research's key breakthrough was learning to backtrack and pivot when initial search results weren't relevant. Onyxia's pre-meeting-prep shift could add feedback: research → draft talking points → simulate objections → refine → iterate until ready.

### 6. Confidence-Based Human-in-the-Loop Escalation

**Definition:** Autonomous agent makes decisions with confidence scores. Route decisions below threshold (e.g., <70% confidence) or above impact threshold (e.g., high-value account, C-level request) to human for review. Target 10-15% escalation rate.

**Who uses it:** Outreach, financial services agents, healthcare auth systems, Regie (human review for high-value prospects).

**Why it matters:** True autonomy without guardrails causes reputation damage (wrong email sent to wrong prospect, missed urgency signals). Confidence thresholds let Onyxia scale faster: auto-approve routine follow-ups, escalate edge cases.

### 7. Scheduled Autonomy & Shift Architecture

**Definition:** Schedule agents to run at fixed times (morning, mid-day, EOD, weekly). Each shift has a bounded scope (check new signals, synthesize intelligence, trigger actions). No continuous polling.

**Who uses it:** Regie Auto-Pilot (autonomous 24/7 prospecting, but triggered by daily intent refresh), modern agentic orchestration platforms (scheduler + event triggers), Temporal + LangGraph patterns.

**Why it matters:** Continuous agents drain API budgets and context windows. Onyxia already does this (7 shifts). The leverage comes from *specialization* within each shift: morning-brief discovers new signals, watchdog escalates risks, EOD-wrap closes loops, weekly-synthesis learns patterns.

### 8. Reasoning Over Long Horizons

**Definition:** Model trained on reinforcement learning to plan and execute 100s-1000s of sequential decisions. Maintains persistent reasoning state (like Devin's DeepWiki or Claude's context compaction).

**Who uses it:** OpenAI o3-deep-research, Cognition Devin (SWE-1.5 frontier model), Claude 4.5+ with context compaction.

**Why it matters:** Sales deals span months. A single agent call can't reason from first touch to close. Devin's "agent-native" approach maintains codebase understanding across sessions. Onyxia needs equivalent for *deal state*: remember prospect history, objections, economic buyer dynamics, timeline constraints across shifts.

## Sales-specific patterns

### 1. Multi-Signal Orchestration

**Definition:** Fuse intent signals from web/email/LinkedIn/events, score accounts in real-time, trigger orchestrated multi-channel outreach within 2-4 hours of signal.

**Who uses it:** Outreach (Nia), Clay (Claygent + agents), Regie, Apollo (signal-based selling framework).

**Why it matters:** Apollo reports teams using signal-triggered outreach see 8-15% reply rates vs 2-5% for static lists. Signal decay is real: prospect researches your product Tuesday 3pm, you email them Wednesday afternoon, signal is cold. Onyxia's intent-signal-hunt play exists; automation latency needs <2 hours.

### 2. Prospect Research Pipeline (Automated Enrichment at Scale)

**Definition:** Given a prospect name + company, autonomously visit 50+ data sources (LinkedIn, company website, recent press, job boards, funding DBs, tech stack trackers, industry news) and synthesize into a personalized talking point + email skeleton.

**Who uses it:** Artisan Ava (dozens of sources per prospect), Clay (150+ data sources, Claygent visits websites autonomously), 11x Alice (rebuilt for deeper research), Perplexity Deep Research.

**Why it matters:** Ava reports 80% of outbound work is now automated. Artisan customers run 10-20x higher outreach volumes than manual SDRs. Onyxia's ZoomInfo + Clay integration works; but could add: recent founding changes (LinkedIn company page timeline), press release monitoring, competitor tech adoption (Patent DB / G2 reviews), earnings call transcripts for large-cap prospects.

### 3. Persona-Aware Drafting

**Definition:** Configure AI to adopt specific voice (formal/casual, detail level, assertiveness). Preserve personalization (no templates, every email unique) while maintaining voice consistency.

**Why it matters:** Artisan lets users set voice config. Result: outreach feels like peer, not bot. Onyxia's voice rules are explicit (peer tone, no jargon). Adding persona-aware tone adaptation per vertical (CISOs = direct + technical, procurement = process-focused) scales personalization.

**Who uses it:** Artisan Ava, Clay, Regie.

### 4. Reply-Intent Parsing & Auto-Response

**Definition:** Parse reply, classify intent (yes → meeting booked, no → disqualify, maybe → nurture, objection → counter, out-of-office → re-trigger 2 weeks), auto-execute next-best-action.

**Who uses it:** 11x Alice (handles simple follow-ups, saves SDR manager triage), Regie (uses GPT-4o for reply classification >95%), Outreach.

**Why it matters:** Onyxia already has `reply-intent-parser.md` play. Current status: unknown if live. If live, opportunity is: escalate edge cases (competitor mention, legal pushback) to Miles, auto-approve routine "not interested" disqualifications, auto-schedule follow-up calls on "yes" replies.

### 5. Engagement Signal Scoring & Tiering

**Definition:** Assign each prospect/account a multi-dimensional signal score (web visits, email opens, LinkedIn profile views, content downloads, meeting attendance). Bucket into tiers (T1: 3+ signals in 48h, T2: 1-2 signals, T3: no recent signals). Route different messaging + cadence to each tier.

**Who uses it:** Outreach (intent tiers), Apollo (signal-based framework), Regie, Clay.

**Why it matters:** Apollo reports companies using intent tiers see 35% lift in meeting bookings. Onyxia has `signal-log/` folder; unclear if signals feed into real-time routing. If Miles is monitoring RB2B + ZoomInfo visitor signals, a simple scoring function (web visit = +2, email open = +1, LinkedIn view = +0.5, threshold = 3 = immediate outreach) could trigger automatic reply sequences or escalation.

## Gap analysis vs Miles's current operator

| Pattern | Onyxia has it? | Why useful |
|---------|----------------|-----------|
| Intent classification on replies | Partial (play exists, live status unclear) | Enables true reply-handling autonomy, reduces Miles's triage by 80% |
| Dynamic sequencing | No | Adaptive cadence multiplies engagement. Static sequences leave engagement on table. |
| Multi-agent task delegation | No | Current monolithic approach loses context on complex research. Splittable into specialists. |
| State checkpointing across shifts | Implicit (vault state) | Explicit checkpointing enables safe parallelism, resume-on-failure, and context compaction for long deals. |
| Iterative planning + feedback | Partial (shifts exist, but no explicit feedback loop) | Feedback loops improve decision quality (simulate objections, refine messaging, plan before execution). |
| Confidence-based escalation | No | Manual approval gate exists; could replace with confidence thresholds to auto-approve routine actions. |
| Scheduled shifts | Yes (7 shifts shipped 2026-04-22) | Already implemented. Opportunity: deepen specialization within each shift. |
| Long-horizon reasoning | Partial (vault provides context, but no explicit compaction) | Deals last 12+ months; explicit context compaction enables agent to maintain reasoning across 20-40 shift invocations. |
| Multi-signal orchestration | Partial (hunt plays exist, unclear if real-time) | Signal decay is real. Latency >2h kills momentum. Current plays are manual. |
| Prospect research automation | Yes (ZoomInfo, Clay) | Tools exist; opportunity: add press release monitoring, recent hiring, earnings calls, competitor tech adoption. |
| Persona-aware drafting | Yes (voice rules explicit) | Already strong. Opportunity: tier-aware tone adaptation (CISO vs procurement vs CFO). |
| Reply-intent parsing | Partial (play exists) | Critical for autonomy. Status unclear; if not live, highest leverage. |
| Signal scoring + tiering | Partial (signal-log exists) | Unclear if feeds into routing. If not, simple scoring function (3+ signals in 48h = T1) could unlock 35% lift. |

## Top 5 techniques to steal

### 1. **Reply-Intent Classification with Confidence Thresholds** (Highest leverage)

**Source:** Regie (>95% accuracy via GPT-4o), 11x Alice (handles simple follow-ups autonomously), Outreach Nia.

**Adaptation to Onyxia:** Implement in `reply-intent-parser.md` if not already live. On every inbound email to Miles or flagged sales address: parse with Claude (or GPT-4o), extract intent + confidence. If confidence >85% and intent = "not interested" or "out of office" → auto-disqualify or re-trigger 2 weeks. If confidence >90% and intent = "yes" → auto-escalate to Miles with "MEETING READY" flag. If confidence <70% or objection detected → escalate to Miles with full context.

**Estimated build effort:** 4-6 hours (parse Gmail API, route via MCP, store intent + confidence in vault contact record, trigger escalation logic).

**Measurement hook:** Track % of replies auto-handled vs escalated, velocity of reply-to-next-action (target: <2 hours for T1 accounts), reply-rate lift from auto-follow-up.

---

### 2. **Dynamic Engagement Signal Scoring + Auto-Sequencing** (Second highest)

**Source:** Apollo signal-based selling, Outreach Nia, Clay multi-signal orchestration.

**Adaptation to Onyxia:** Create `signal-scoring-engine.md` play. Input: prospect web visits (RB2B), email opens (Gmail), LinkedIn profile views (LinkedIn API if available), ZoomInfo triggers, calendar visits, content downloads. Scoring: web visit = +2, email open = +1, LinkedIn view = +0.5, meeting scheduled = +3. Threshold logic: score >3 in 48h = Tier 1 (immediate reply sequence), 1-3 = Tier 2 (standard), <1 = Tier 3 (nurture). Route to different email skeletons (Tier 1 = urgency-framing, Tier 2 = peer-intro, Tier 3 = value education) and cadence (Tier 1 = 48h follow-up, Tier 2 = 5-day, Tier 3 = 14-day).

**Estimated build effort:** 8-10 hours (aggregate signals from RB2B, Gmail, Clay, ZoomInfo; implement scoring schema; connect to sequence router in morning-brief shift).

**Measurement hook:** Reply rate by signal tier (should see 8-15% T1 vs 2-5% T3), conversion rate by tier, cycle time reduction.

---

### 3. **Interactive Planning Before Execution (Reasoning Loop)**

**Source:** Cognition Devin (interactive planning before code execution), OpenAI Deep Research (iterative plan + backtrack + pivot), Claude Code (feedback loop).

**Adaptation to Onyxia:** For complex deals (12+ month cycles, 3+ stakeholders, procurement-heavy), implement in `pre-meeting-prep.md` shift. Before drafting outreach or scheduling call: generate high-level strategy (persona map, economic buyer hypothesis, objection anticipation, timeline), ask Miles to approve or iterate, then execute. For research tasks: draft research hypothesis, execute (ZoomInfo + Clay + web), observe (are we finding the right signals?), adjust (pivot to different keywords or data sources), re-execute. Current pre-meeting-prep likely reads static account info; adding feedback loop forces strategy before action.

**Estimated build effort:** 6-8 hours (add Claude prompt for strategy generation, Miles approval gate, execute after approval, add reflection step to research plays).

**Measurement hook:** Win rate on deals with interactive planning vs baseline, cycle time, number of pivots before finding right economic buyer.

---

### 4. **Prospect Research Automation: 50+ Data Sources to Single Dossier**

**Source:** Artisan Ava (press releases, funding, tech stack, hiring, M&A, LinkedIn timeline), Clay (150+ sources, Claygent website visits), 11x Alice (rebuilt for depth).

**Adaptation to Onyxia:** Extend `continuous-research.md` play. Current state: likely uses ZoomInfo + Clay. Add: (a) LinkedIn company page timeline for recent executive changes, (b) press release aggregator (Cision / Google Alerts API), (c) earnings call transcripts for large-cap prospects (Seeking Alpha / company IR pages), (d) tech adoption signals (G2 reviews, Patent DB for innovation signals, Crunchbase for funding events), (e) news sentiment (positive = expansion signal, negative = pain point). Run weekly per warm account. Synthesize into short "deal dossier" that pre-meeting-prep uses for objection prep.

**Estimated build effort:** 10-12 hours (add data source collectors as scheduled tasks, implement synthesis prompt in Claude, store dossiers in vault).

**Measurement hook:** Objection anticipation accuracy (were anticipated objections the ones Miles faced?), deal velocity (earlier economic buyer discovery), stage progression rate.

---

### 5. **Context Compaction for Long-Running Deal State**

**Source:** Anthropic (context compaction in Claude SDK for long-running agents), Devin (DeepWiki persistent codebase state), Claude 4.5+ with structured note-taking.

**Adaptation to Onyxia:** Deals run 3-12 months; each shift invocation adds context to account record (who we talked to, what they said, objections raised, timeline constraints, competitive threats). Without compaction, the vault account file becomes noise. Implement: weekly `quarterly-self-audit.md` shift (already exists) should auto-generate "compact summary" of deal state: 1 sentence per stakeholder (name + title + position + last interaction), 1 sentence per key objection (what it was, how we rebutted, still open?), 1 sentence on timeline (when they want to decide?). Store in vault as `10_Accounts/{Company}.md` in structured YAML front matter. Pre-meeting-prep and reply-handler read *compact summary* first, then full history if context window permits.

**Estimated build effort:** 4-6 hours (add Claude prompt for deal state extraction, store in frontmatter, update weekly, teach shifts to read compacted state first).

**Measurement hook:** Shift invocation context window usage (should reduce after compaction), agent decision quality on long deals (are we remembering stakeholder preferences?), error rate on deal detail (wrong stakeholder name, wrong timeline).

---

## Which ONE to prototype this session

**Pick: Reply-Intent Classification with Confidence Thresholds**

**Rationale:** 
- Onyxia already has the `reply-intent-parser.md` play documented. This is a *live status question* that, if answered as "not live," opens the fastest path to measurable autonomy lift.
- If the play is live but not confidence-gated, adding thresholds takes <2 hours and unlocks auto-approval on routine replies.
- Measurement is immediate: track escalation rate (target 10-15%), time-to-response (target <2h for T1), reply-rate lift from faster follow-ups.
- Impacts Miles directly every single day (reduces inbox triage load).

**Minimal implementation sketch:**

1. **Step 1 (Status check):** Read `reply-intent-parser.md` play. Identify: is it live? Does it include confidence scoring? If yes and yes, move to Step 4.
2. **Step 2 (Create intent classif MCP):** Add a lightweight Python function in Onyxia's MCP tools (or use Claude API directly in watchdog shift): input = inbound email, output = {intent: string, confidence: 0-1, keywords: [list]}.
3. **Step 3 (Routing logic in watchdog shift):** When watchdog checks Gmail inbox for new replies:
   - For each reply: call intent classifier.
   - If confidence >85% AND intent in ["not_interested", "out_of_office"] → tag in vault contact record, do NOT escalate.
   - If confidence >85% AND intent = "yes" AND "meeting" in keywords → tag with "MEETING_READY", post to ops channel.
   - If confidence <75% OR intent = "objection" → escalate to Miles with full email + intent + confidence.
   - Log all classifications in vault for feedback loop.
4. **Step 4 (Feedback loop):** Weekly, audit escalations. For any that Miles immediately approves/rejects, retrain thresholds. (E.g., if 80% of <75% confidence escalations turn out to be disqualifications, raise threshold to 80%).
5. **Step 5 (Measurement):** Track: % auto-handled vs escalated, avg time from reply to next action, reply-rate on auto-follow-ups.

**File paths:**
- Create: `~/ObsidianVault/40_Plays/reply-intent-classifier-automated.md` (if not already live).
- Update: `~/ObsidianVault/40_Plays/shifts/watchdog.md` (add intent classification logic).
- Create: `~/ObsidianVault/60_Lessons/reply-intent-feedback-log.md` (weekly audit + threshold updates).

## Sources

- [Regie.ai 2025 Predictions](https://www.regie.ai/blog/the-next-evolution-of-ai-in-sales-predictions-for-2025)
- [Regie.ai Auto-Pilot](https://www.regie.ai/blog/sales-auto-pilot-regie-ai)
- [RegieOne AI SEP](https://www.regie.ai/blog/introducing-regie-one)
- [11x.ai Alice Overview](https://www.11x.ai/worker/alice)
- [11x.ai Multi-Agent Architecture](https://www.zenml.io/llmops-database/rebuilding-an-ai-sdr-agent-with-multi-agent-architecture-for-enterprise-sales-automation)
- [11x Series B Funding](https://www.maginative.com/article/11x-raises-50m-series-b-led-by-a16z-for-ai-digital-workers/)
- [Clay AI Agents](https://www.salescaptain.io/blog/clay-ai-agent)
- [Clay Series C Valuation](https://mlq.ai/news/clay-raises-100m-series-c-at-31-1b-valuation-to-expand-ai-sales-automation-platform/)
- [Clay Achieving 10x Growth](https://openai.com/index/clay/)
- [OpenAI Deep Research Intro](https://openai.com/index/introducing-deep-research/)
- [OpenAI Deep Research Architecture](https://cobusgreyling.medium.com/openai-deep-research-ai-agent-architecture-7ac52b5f6a01)
- [OpenAI Deep Research Cookbook](https://cookbook.openai.com/examples/deep_research_api/introduction_to_deep_research_api_agents)
- [LangGraph Framework](https://www.langchain.com/langgraph)
- [LangGraph State Management](https://sparkco.ai/blog/mastering-langgraph-state-management-in-2025/)
- [LangGraph Multi-Agent Guide](https://latenode.com/blog/ai-frameworks-technical-infrastructure/langgraph-multi-agent-orchestration/langgraph-multi-agent-orchestration-complete-framework-guide-architecture-analysis-2025)
- [Artisan Ava AI Sales Agent](https://www.artisan.co/ai-sales-agent)
- [Artisan Review 2026](https://www.quotaengine.com/tools/artisan/)
- [CrewAI Framework](https://docs.crewai.com/en/introduction)
- [CrewAI Orchestration Guide](https://www.digitalocean.com/community/tutorials/crewai-crash-course-role-based-agent-orchestration)
- [CrewAI AWS Guidance](https://docs.aws.amazon.com/prescriptive-guidance/latest/agentic-ai-frameworks/crewai.html)
- [Cognition Devin Intro](https://cognition.ai/blog/introducing-devin)
- [Devin 2.0 Release](https://cognition.ai/blog/devin-2)
- [Devin AI Technical Design](https://medium.com/@takafumi.endo/agent-native-development-a-deep-dive-into-devin-2-0-s-technical-design-3451587d23c0)
- [Perplexity Deep Research](https://www.perplexity.ai/hub/blog/introducing-perplexity-deep-research)
- [Perplexity Sonar Deep Research](https://docs.perplexity.ai/getting-started/models/models/sonar-deep-research)
- [Simon Willison Agentic Patterns Guide](https://simonwillison.net/guides/agentic-engineering-patterns/)
- [Simon Willison Newsletter on Agentic Patterns](https://simonw.substack.com/p/agentic-engineering-patterns)
- [Intent Classification Sales Agents](https://www.inogic.com/blog/2025/11/how-to-automate-email-workflows-using-autonomous-and-multi-agent-ai-copilot/)
- [Intent Recognition Auto-Routing](https://gist.github.com/mkbctrl/a35764e99fe0c8e8c00b2358f55cd7fa)
- [Intent Classification Accuracy](https://www.helpshift.com/glossary/intent-classification/)
- [Signal-Based Selling Framework](https://www.apollo.io/insights/signal-based-selling)
- [Apollo Signal-Based Selling Guide](https://www.amplemarket.com/blog/signal-based-selling)
- [Outreach Nia Signal Monitoring](https://www.warmly.ai/p/blog/sales-engagement-tools)
- [Human-in-the-Loop Agentic AI](https://onereach.ai/blog/human-in-the-loop-agentic-ai-systems/)
- [Human-in-the-Loop Oversight](https://galileo.ai/blog/human-in-the-loop-agent-oversight/)
- [Human-in-the-Loop Escalation Patterns](https://orkes.io/blog/human-in-the-loop/)
- [Confidence-Based Routing Best Practices](https://www.elementum.ai/blog/human-in-the-loop-agentic-ai)
- [AutoGen Conversation Patterns](https://microsoft.github.io/autogen/0.2/docs/tutorial/conversation-patterns/)
- [AutoGen State Management](https://medium.com/@senol.isci/exploring-multi-agent-conversation-patterns-with-the-autogen-framework-29946f199ca5)
- [AutoGen Multi-Agent Chat](https://github.com/microsoft/autogen/discussions/7144)
- [Latent Space Podcast](https://www.latent.space/podcast)
- [Latent Space Deep Research Episode](https://podcasts.apple.com/us/podcast/the-inventors-of-deep-research/id1674008350?i=1000693616210)
- [AI Agent Scheduling Patterns](https://fast.io/resources/ai-agent-job-scheduling/)
- [AI Agent Orchestration](https://www.n-ix.com/ai-agent-orchestration/)
- [Microsoft AI Agent Patterns](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/ai-agent-design-patterns/)
- [Claude Code Agent Loop](https://code.claude.com/docs/en/agent-sdk/agent-loop)
- [Claude Advanced Tool Use](https://www.anthropic.com/engineering/advanced-tool-use)
- [Claude Code Feedback Loops](https://claudefa.st/blog/guide/development/feedback-loops)
- [Claude Code Agentic Patterns](https://medium.com/@reliabledataengineering/agentic-workflows-with-claude-architecture-patterns-design-principles-production-patterns-72bbe4f7e85a)
- [Anthropic Context Engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- [Anthropic Multi-Agent Research System](https://www.anthropic.com/engineering/multi-agent-research-system)
- [Anthropic Long-Running Agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- [Anthropic 2026 Agentic Coding Report](https://resources.anthropic.com/hubfs/2026%20Agentic%20Coding%20Trends%20Report.pdf)

