---
type: intel
subtype: progress-log
date: 2026-04-22
tags: [intel, hunt-research]
---

# Vertical Expansion — Progress Log

Executing 7-phase scope expansion beyond healthcare/fins/mfg/CI. Git-checkpointed per phase.

## Progress

### Phase 1 — HubSpot density analysis — COMPLETE
Shipped: `50_Intel/hunt-research/2026-04-22-vertical-density-analysis.md`.
Key findings:
- 10 non-covered industries scanned by company count. Top 6 with critical mass: Computer Software (1,267), Higher Ed (286), Real Estate (243), Retail (206), Legal Services (141), Oil/Energy (88), Defense (83), Govt Admin (83).
- 2,247 CISO-titled contacts + 10,124 Security-titled contacts across all industries. Address book is 100x larger than closed-won count; bottleneck is prioritization + territory overlap with Brad.
- Real Estate, Retail, Legal Services each have non-healthcare closed-won precedent — candidates for vertical-file treatment.
- Higher Ed, Computer Software, Defense are high-density but no existing wins — candidates for exploratory expansion.
Budget: 8/15 Phase 1 tool calls used.
Next: Phase 2 — synthesize closed-won patterns for non-covered verticals, identify which have ≥2 wins.

### Phase 2 — Closed-won pattern synthesis — COMPLETE
Shipped: `50_Intel/hunt-research/2026-04-22-closed-won-nonhealthcare-synthesis.md`.
Non-covered verticals with file-worthy precedent: Real Estate (2 wins), Retail/Hospitality (1 direct + 1 adjacent + 1 pipeline), Legal Services/BigLaw (1 win, 577-day cycle caveat), SaaS/Tech (3 wins, security-vendor exclusion guardrail).
Verticals to carry into Phase 3: Real Estate, Retail, Legal, SaaS, Higher Ed, Defense.
Singletons that stay footnotes: Staffing (AXNY), PE (Vista), Agri-Chem (Adama).
Next: Phase 3 — regulatory tailwind scan for the 6 carrying verticals.


### Phase 3 — Regulatory tailwind scan — COMPLETE
Shipped: `50_Intel/hunt-research/2026-04-22-regulatory-tailwind-scan.md`.
Key findings:
- Defense/Aerospace: CMMC Phase 2 hard deadline November 10, 2026. Urgency score 5/5. 6.5 months from today, ~1% of 220K contractors are ready.
- Retail/Hospitality: PCI-DSS 4.0.1 fully mandatory since March 31, 2025. Monthly fines accumulating now. Urgency 4/5.
- Legal Services: NYC Bar Opinion 2024-3 + NY mandatory CLE (hard-stop 2026). Note: ABA 512 is AI ethics, not cyber directly. Urgency 2/5, 577-day cycle caveat confirmed.
- SaaS/Technology: SOC 2 table stakes + SEC rule for public SaaS + CPRA audit mandate (scoping now, certifications 2028+) + EU DORA for EU-facing SaaS.
- Higher Education: GLBA Safeguards active since June 2023, NIST 800-171 Rev 3 DoD implementation late 2026–early 2027.
- Real Estate: SEC cyber disclosure rule in effect, FY 2026 exam cycle actively reviewing disclosure quality.
Next: Phase 4/5 — tool ecosystem + vertical file writes.

### Phase 4 — Tool ecosystem research — COMPLETE (folded into vertical files)
Competitive context integrated directly into each vertical file (incumbents, gap analysis, Onyxia positioning). No standalone file needed.
Next: Phase 5 — vertical file writes.

### Phase 5 — Vertical file writes — COMPLETE
6 new vertical files shipped to `50_Intel/verticals/`:
- `real-estate.md` — 2 wins, SEC tailwind, Sivan-intro dependent
- `retail-hospitality.md` — Chipotle + Starboard pipeline, PCI urgency
- `saas-technology.md` — 3 wins, 1,267 HubSpot companies, security-vendor guardrail
- `higher-education.md` — 0 wins, GLBA + NIST 800-171 Rev 3, R1 research hook
- `defense-aerospace.md` — 0 wins, CMMC Nov 10 hard deadline, highest urgency
- `legal-services.md` — 1 win 577 days, deprioritized, warm-intro only
Next: Phase 6 — priority ranking.

### Phase 6 — Priority ranking — COMPLETE
Shipped: `50_Intel/hunt-research/2026-04-22-vertical-expansion-ranking.md`.
Final ranking:
1. SaaS/Technology (9/10) — biggest pool, 3 wins, Miles's territory
2. Defense/Aerospace (8/10) — CMMC deadline urgency substitutes for precedent
3. Retail/Hospitality (7/10) — live Starboard pipeline + PCI enforcement
4. Real Estate (6/10) — Sivan-intro dependent, SEC tailwind
5. Higher Education (5/10) — long arc, no precedent, warm-intro gated
6. Legal Services (3/10) — deprioritized, 577-day cycle

**Verdict:** Run SaaS + Defense in parallel as primary expansion plays. Starboard is already warm in Retail. Real estate needs Sivan. Higher Ed and Legal are bench.
Next: Phase 7 — Slack post + walkthrough.

### Phase 7 — Slack post — STAGED (requires claude.ai session for MCP OAuth)
Slack MCP OAuth not available in CLI context. Message staged below — paste into #miles-ai-ops from claude.ai or copy manually.

```
**Vertical expansion — Phases 3-6 complete** ✅

Priority ranking:
1. SaaS/Technology (9/10) — 1,267 HubSpot companies, 3 wins, Miles's territory
2. Defense/Aerospace (8/10) — CMMC Nov 10 hard deadline, 6.5 months, ~1% ready
3. Retail/Hospitality (7/10) — PCI fines accumulating now, Starboard live ($150K)
4. Real Estate (6/10) — SEC cyber rule, 2 wins, Sivan-intro dependent
5. Higher Education (5/10) — GLBA + NIST 800-171 Rev 3, long arc, 0 wins
6. Legal Services (3/10) — deprioritized, 577-day cycle

Biggest finding: CMMC Nov 10 is the hardest urgency hook in the vault — stronger than HIPAA NPRM. Cold outreach viable because the deadline sells itself.

Immediate plays: SaaS (filter 1,267 → 20-account list) + Defense (83 HubSpot → CMMC cold sequence) + close Starboard + Sivan intro for CRE.

9 files committed @ 2fc4702
```

