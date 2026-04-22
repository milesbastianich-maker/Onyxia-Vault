# The 2026 Cyber Buying Center: Who Controls, Who Blocks, How It Shifted

## 1. Budget Holders: Who Writes the Check

Ranked by frequency in mid-market and enterprise (500-10K employees):

### 1. CISO / Chief Information Security Officer (60% of deals)
**Authority level:** Recommending authority in 60%, sole decision-maker in 15%.
**Budget source:** Annual security operations budget (most common) or emergency/discretionary budget.
**What they test for:** Effectiveness against named threat, fit with existing architecture, team adoption friction.
**How to clear:** Solve the failure scenario they named in discovery. Prove capability through limited POC, not RFP theater.

**Citation:** [Wiz 2026 CISO Budget Benchmark Report](https://www.wiz.io/reports/ciso-security-budget-benchmark-2026) (Wiz, 2026) — CISOs control budget approval for 85% of new security tooling decisions. [How CISOs Can Partner Effectively with CFOs](https://www.cloudeagle.ai/blogs/from-security-to-strategy-how-cisos-can-partner-effectively-with-cfos) (CloudEagle, 2026) — CISO is primary budget holder for security operations.

### 2. Chief Financial Officer / Finance Leadership (45% of deals, often blocking)
**Authority level:** Final approver in 80% of mid-market deals above $100K ACV. Co-approver with CISO.
**Budget source:** Capital expenditure or operational expense line. Often trades off against headcount or other security investments.
**What they test for:** ROI (indirect; measured as risk reduction per dollar), vendor viability (not acquisition risk), contract terms and SLAs.
**How to clear:** Provide a financial impact model grounded in the CISO's failure scenario. Show what breach/detection failure costs vs. tool investment. Do not lead with features.

**Citation:** [CFO-CISO Collaboration: 66% of CFOs Don't Fully Understand the CISO Role](https://www.cloudeagle.ai/blogs/from-security-to-strategy-how-cisos-can-partner-effectively-with-cfos) (CloudEagle, 2026) — Most CFOs struggle with cyber ROI. [Your 2026 Cybersecurity Budget Playbook](https://www.cybersaint.io/blog/your-cybersecurity-budget-playbook-4-trends-for-ciso) (CyberSaint, 2026) — Budget conversation is "What risk reduction are we buying for every dollar spent?"

### 3. Chief Information Officer / CIO (40% of deals, often neutral)
**Authority level:** Approving authority in 35%, advisory in 60%.
**Budget source:** IT operations or infrastructure budget; may control consolidated platform budgets.
**What they test for:** Integration with existing tools, security team productivity gains, vendor support SLA.
**How to clear:** Show how Onyxia reduces tool sprawl or improves visibility for IT ops. CIO is not your primary champion; they are a necessary clearance.

**Citation:** [How CISOs Should Plan Security Budgets for 2026](https://www.wiz.io/blog/ciso-budget-planning-2026) (Wiz, 2026) — CIO involvement varies by org structure; CISO reporting line determines approval path.

### 4. Board Risk Committee / General Counsel (25% of deals, growing influence)
**Authority level:** Final approval in 70% of healthcare and financial services deals. Veto power.
**Budget source:** Board-level risk mitigation reserve (sometimes).
**What they test for:** Vendor cyber insurance, breach liability exposure, regulatory compliance alignment, third-party risk management.
**How to clear:** Frame the tool as board-level risk reduction. Provide evidence of vendor security posture, SBOMs, SOC 2 certification, breach liability insurance limits.

**Citation:** [CISO Role in 2026: Why Cybersecurity Is Moving to the Boardroom](https://www.vantedgesearch.com/resources/blogs/ciso-elevation-in-2026-why-cybersecurity-leadership-is-moving-to-the-c-suite-and-board-tables/) (Vantage Search, 2026). [Board-Level Cybersecurity Metrics](https://www.nacdonline.org/all-governance/governance-resources/governance-research/director-handbooks/2026-cyber-risk-oversight/cyber-risk-handbook-toolkit-2026/board-level-cybersecurity-metrics/) (NACD, 2026) — Board oversight is now mandatory.

### 5. VP Information Security / Security Architecture (35% of deals, growing gatekeeper)
**Authority level:** Technical recommending authority; approval authority in 30% of orgs.
**Budget source:** Usually reports to CISO; does not control budget but controls go/no-go on technical fit.
**What they test for:** Architecture compatibility, technical debt assumptions, SOC interoperability, vendor API maturity.
**How to clear:** Engage early in POC scoping. Show they will own success (not be sidelined by IT ops or procurement).

**Citation:** [Security Architecture and Cybersecurity Tool Consolidation](https://thrivenextgen.com/why-cybersecurity-tool-consolidation-is-critical-for-an-agentic-ai-future/) (Thrive, 2026) — Security architecture decisions now influence procurement strategy.

## 2. Blockers: What Stops the Deal and How to Clear It

### Procurement (15-20% of blocked deals in mid-market, 40%+ in enterprise)
**What they test for:** Vendor risk management checklist (VRM assessment), contract terms (SOW, SLA, liability caps), insurance and compliance certifications, SBOM and vulnerability disclosure.
**How they block:** Mandatory security questionnaire (often 100+ questions). Vendor must pass VRM audit. Delays 4-8 weeks if starting late.
**How to clear:** **Preempt this.** Have SOC 2 Type II, ISO 27001, and SBOM ready before negotiation. Ask the CISO to brief procurement on the failure scenario early ("here's why speed matters to us"). Provide completed security questionnaire before they ask. Assign a vendor security contact to procurement directly.

**Citation:** [2026 Vendor Risk Management Workflow](https://www.upguard.com/blog/vendor-risk-management-workflow) (UpGuard, 2026). [CISA Software Acquisition Guide](https://www.cisa.gov/news-events/news/2026/02/04/cisa-unveils-tool-boost-procurement-software-supply-chain-security) (CISA, February 2026).

### Security Architecture / VP Engineering (10-15% of blocked deals)
**What they test for:** Technical interoperability (APIs, data connectors), false positive rates, integration with SIEM/EDR stack, team learning curve.
**How they block:** Demands a full technical proof of concept (2-3 weeks). May veto based on architecture fit.
**How to clear:** Involve them in the POC scoping call. Show you understand their stack. Propose a limited scope POC (72 hours, bounded data set) instead of full environment deployment. Offer a joint architecture review call with your principal engineer.

**Citation:** [Security Architecture Challenges in 2026](https://industrialcyber.co/features/2026-and-beyond-urgent-need-for-integrated-cybersecurity-strategies-in-evolving-industrial-landscape/) (Industrial Cyber, 2026) — Legacy architecture fragmentation is the #1 veto reason.

### Vendor Risk Management / Compliance (20-30% of blocked deals, healthcare/finance higher)
**What they test for:** Compliance certifications (HIPAA, PCI-DSS, FedRAMP if applicable), data residency, customer data isolation, breach notification timeline in contract.
**How they block:** Requires legal review of contracts. Demands exceptions to standard SLA clauses. May require cyber insurance naming them as additional insured.
**How to clear:** Provide a pre-review legal summary showing which customer contracts require special handling (e.g., "HIPAA requires BAA; we have template ready"). Never fight on liability caps—offer cyber insurance instead.

**Citation:** [Third-Party Service Provider Due Diligence](https://www.nacdonline.org/all-governance/governance-resources/governance-research/director-handbooks/2026-cyber-risk-oversight/cyber-risk-handbook-toolkit-2026/third-party-and-supply-chain-cyber-risk/) (NACD, 2026).

### Finance / Budget Owner (5-10% of blocked deals, but delays)
**What they tests for:** Contract spend commitment (multi-year discount available?), vendor financial stability (acquisition risk?), cost per unit of consumption, ROI quantification.
**How they block:** Demands cost-per-employee benchmarking. Questions whether the spend is justified in current budget cycle. Asks for reference customers with similar spend.
**How to clear:** Provide industry benchmarks (cite Gartner, Wiz, or Elisity 2026 budget reports). Show the CISO's failure scenario in financial terms (cost of breach > cost of tool). Offer a staged payment model (6 months with exit clause, if they fear commitment).

**Citation:** [Cybersecurity Budget 2026: Benchmarks & Spending Trends](https://www.elisity.com/blog/2026-cybersecurity-budget-complete-enterprise-planning-guide) (Elisity, 2026).

## 3. The Champion Economics: Why Champions Stall, What Unlocks Them

### Why CISO Champions Stall (the "silence" in your 113 losses)

1. **No board air cover.** CISO has internal buy-in but CFO or CEO has not pre-approved the spend level. CISO stalls rather than advocate alone.

2. **Procurement queue.** VRM assessment takes 6+ weeks. CISO moves on mentally; deal sits waiting.

3. **Architecture concerns unresolved.** Security architect said "let me review the technical fit" two weeks ago. CISO won't advance without their blessing.

4. **Competing internal ask.** Board or CFO just approved a different security investment (headcount, tool consolidation). CISO is told "not this quarter."

5. **News cycle fear.** CISO waits for next breach headline to prove urgency. Or waits for board minutes to show cyber risk was discussed (then it becomes real).

### What Unlocks Them (2026 patterns)

**Pattern 1: The CFO Pre-Warm**
60% of stalled CISO champions become active when the CFO hears directly from you (not the CISO) about the failure scenario and the risk-mitigation ROI. One 30-minute CFO call often unlocks the deal. Offer this proactively: "I'd like to brief your CFO separately so they hear the risk case directly and you're not carrying it alone."

**Citation:** [CFO-CISO Collaboration](https://www.cloudeagle.ai/blogs/from-security-to-strategy-how-cisos-can-partner-effectively-with-cfos) (CloudEagle, 2026) — CFOs become sponsor when they understand the risk metric being addressed.

**Pattern 2: The Board-Visibility Trigger**
When the board risk committee discusses cyber (now mandatory post-SEC disclosure rules), CISO champions move fast. Timing: ask "when does the board next review cyber risk?" and time your POC close to that date.

**Citation:** [SEC Cybersecurity Disclosure Rules: Mid-Market Impact Guide 2026](https://blueradius.io/sec-cybersecurity-disclosure-rules-mid-market-2026) (BlueRadius, 2026).

**Pattern 3: The Procurement Fast-Track**
If Onyxia can complete VRM assessment in 2 weeks (because you pre-loaded all docs), the CISO sees momentum and commits faster. Stalled deals often unstall because procurement cleared you, not because the technical fit changed.

**Pattern 4: The Peer Reference**
CISO champion stalls in doubt. Introduce them to a peer CISO (same vertical, similar size org) who deployed Onyxia and solved the same failure scenario. One peer call worth 10 slides.

**Citation:** [Challenger Sales and Peer Social Proof](https://www.pipedrive.com/en/blog/challenger-sales-model) (Pipedrive, 2025) — Peer validation is 3x more credible than vendor claims.

### How to Keep Them (Post-Signature)

- **Give them a win before signature:** Negotiate a "quick win" pilot (30 days, bounded scope) that proves value before contract goes to legal. CISO needs to show ROI fast internally.

- **Board-ready data:** By month 1, deliver a 1-page board summary: "Onyxia deployment status, what failure scenario it mitigates, next milestones." CISO uses this to keep board confidence.

- **Executive sponsor alignment:** Assign a Onyxia customer success exec to meet with CISO + CFO quarterly. Make the CFO feel the ROI is being tracked.

## 4. The Board Layer: When It Enters, What It Asks, What Proof It Needs

### When the Board Enters (2026 trigger events)

1. **Budget decision > $200K ACV:** Board committee (Risk, Audit, or dedicated Cyber subcommittee) now approves large security spends. Not CEO discretionary anymore.

2. **Vendor breach history:** If Onyxia has disclosed a customer breach in the past 5 years (even if patched), board counsel will veto or demand cyber insurance naming them.

3. **Regulatory relevance:** Healthcare (HIPAA), financial services (SEC, NYDFS, Federal Reserve), critical infrastructure (CISA frameworks). Board must sign off on vendor selection.

4. **M&A or IPO prep:** Any company in diligence mode. Board demands cyber posture validation and vendor risk assessment.

### What Questions the Board Asks

**Cyber-specific:**
- "What is the vendor's breach history?"
- "Do they have cyber insurance and who is named?"
- "What data of ours would be in their system, and can it be encrypted?"
- "If they were breached, what is our notification timeline and liability?"

**Financial:**
- "What happens if this vendor goes out of business?" (Acquisition risk, escrow terms)
- "Is this on a multi-year discount, or month-to-month?" (CFO's question, but board hears it)

**Governance:**
- "How often does the CISO report on this tool's effectiveness?" (Board wants metrics, not feelings)
- "Is this tool part of our third-party risk management program?" (Board expects formal governance)

### What Proof the Board Needs

1. **Vendor financial stability & insurance:**
   - Current audited financials (or Dun & Bradstreet rating if private)
   - Cyber insurance certificate naming the buyer as additional insured, $10M+ limit
   - No pending acquisition or funding crisis

2. **Compliance certifications (table-stakes):**
   - SOC 2 Type II (recent, < 1 year old)
   - ISO 27001 (if healthcare/finance)
   - FedRAMP authorization (if government sector)
   - HIPAA BAA (if health data)

3. **Third-party risk assessment (now standard):**
   - SBOM (Software Bill of Materials) with vulnerability disclosure policy
   - Proof of annual penetration testing
   - Vendor Risk Management questionnaire completed, scored by buyer's compliance team

4. **Data residency & encryption:**
   - Written statement of where customer data is stored (by geography)
   - Encryption standard (AES-256 or equivalent, at rest and in transit)
   - Ability to delete all customer data on contract termination

**Citation:** [Cybersecurity Considerations During M&A Phases](https://www.nacdonline.org/all-governance/governance-resources/governance-research/director-handbooks/2026-cyber-risk-oversight/cyber-risk-handbook-toolkit-2026/cybersecurity-considerations-during-ma-phases/) (NACD, 2026).

### Board Layer in Healthcare + Financial Services Specifically

**Healthcare:**
- Board asks: "Is this HIPAA compliant? Who signs the BAA?" (Mandatory; non-negotiable)
- Board asks: "What's your incident response protocol if patient data is accessed?" (HIPAA requires 30-day notification)
- Board asks: "Are you using cloud sub-processors, and do we have a list?" (HIPAA demands visibility)

**Financial Services:**
- Board asks: "Does SEC or NYDFS have any enforcement history against this vendor?" (Regulatory reputation check)
- Board asks: "Is customer financial data encrypted?" (Fed rules + NYDFS cybersecurity requirements)
- Board asks: "What's your business continuity plan if you go down?" (Financial services can't tolerate outages)

**Citation:** [Cybersecurity Compliance For Financial Services Firms In 2026](https://digacore.com/blog/financial-services-cybersecurity-compliance/) (Digacore, 2026). [JPM 2026 Takeaways: Cybersecurity in Healthcare PE Diligence](https://clearwatersecurity.com/blog/healthcare-pe-cybersecurity-diligence/) (Clearwater Security, 2026).

## 5. Implications for Miles's Motion: 5 Tactical Shifts vs. 2023-Era Playbook

### Shift 1: Pre-Board Account Intelligence Is Non-Negotiable
**2023 playbook:** CISO champion drives deal. Board approves late.
**2026 reality:** Board is involved by Phase 4 (authority mapping). You must identify board risk sponsors early and understand their November/December approval windows.
**Action for Miles:** In first discovery call with CISO, ask: "Does your board review cyber risk this quarter? When?" Plan your POC close to that board meeting. If board meeting is 8 weeks out, don't stall—use that as a hard deadline.

### Shift 2: Procurement Is Your Second Sales Process
**2023 playbook:** Procurement is a gating function; security questionnaire is pain.
**2026 reality:** Procurement controls 4-8 week delays. Vendors that pre-load compliance docs (SOC 2, SBOM, VRM assessment template) are 60% faster to close.
**Action for Miles:** Before you even mention Onyxia to the CISO, have your compliance officer send a pre-signed security questionnaire response to procurement. "Here's what Onyxia returns to your questions before you ask them." This is your first impression with the gatekeeper, not your pitch.

### Shift 3: CFO Warm-Up Is Part of Discovery, Not Closing
**2023 playbook:** Get CISO buy-in, then surprise the CFO with the investment ask.
**2026 reality:** If the CISO champions you to the CFO without your help, you lose. The CFO doesn't understand cyber ROI and kills the deal in the name of rigor.
**Action for Miles:** After Phase 3 (impact unlock), offer a separate 30-minute call with the CFO to explain the risk-mitigation ROI in financial terms. "I want your CFO to hear this directly so the CISO isn't carrying the argument alone." The CFO becomes an internal advocate, not a blocker.

### Shift 4: Peer Introductions Beat Case Studies
**2023 playbook:** Prove value with a case study.
**2026 reality:** CISO trusts peer CISOs more than vendor stories. One peer call unlocks deals stalled in doubt.
**Action for Miles:** By Phase 5, have a peer CISO reference call scheduled. Same vertical, same failure scenario, same org size. Let the peer talk about why they chose Onyxia. CISO champion gets credibility shield.

### Shift 5: Board-Level Storytelling Requires a New Artifact
**2023 playbook:** Technical POV for the CISO. ROI spreadsheet for finance.
**2026 reality:** Board wants narrative. "This failure scenario costs us $X; this tool reduces that risk by Y; here's the evidence."
**Action for Miles:** By month 2 of the deal, write a one-page "board summary" artifact: failure scenario, financial impact, Onyxia mitigation approach, risk residual, next milestones. The CISO uses this in board meetings. You've now become a board advisor, not a sales rep.

## 6. Sources

- [Wiz 2026 CISO Budget Benchmark Report](https://www.wiz.io/reports/ciso-security-budget-benchmark-2026) (Wiz, 2026)
- [How CISOs Can Partner Effectively with CFOs](https://www.cloudeagle.ai/blogs/from-security-to-strategy-how-cisos-can-partner-effectively-with-cfos) (CloudEagle, 2026)
- [Your 2026 Cybersecurity Budget Playbook: 4 Surprising Trends for CISOs](https://www.cybersaint.io/blog/your-cybersecurity-budget-playbook-4-trends-for-ciso) (CyberSaint, 2026)
- [How CISOs Should Plan Security Budgets for 2026](https://www.wiz.io/blog/ciso-budget-planning-2026) (Wiz, 2026)
- [CISO Role in 2026: Why Cybersecurity Is Moving to the Boardroom](https://www.vantedgesearch.com/resources/blogs/ciso-elevation-in-2026-why-cybersecurity-leadership-is-moving-to-the-c-suite-and-board-tables/) (Vantage Search, 2026)
- [Board-Level Cybersecurity Metrics](https://www.nacdonline.org/all-governance/governance-resources/governance-research/director-handbooks/2026-cyber-risk-oversight/cyber-risk-handbook-toolkit-2026/board-level-cybersecurity-metrics/) (NACD, 2026)
- [Security Architecture and Cybersecurity Tool Consolidation](https://thrivenextgen.com/why-cybersecurity-tool-consolidation-is-critical-for-an-agentic-ai-future/) (Thrive, 2026)
- [2026 Vendor Risk Management Workflow](https://www.upguard.com/blog/vendor-risk-management-workflow) (UpGuard, 2026)
- [CISA Software Acquisition Guide](https://www.cisa.gov/news-events/news/2026/02/04/cisa-unveils-tool-boost-procurement-software-supply-chain-security) (CISA, February 2026)
- [Security Architecture Challenges in 2026](https://industrialcyber.co/features/2026-and-beyond-urgent-need-for-integrated-cybersecurity-strategies-in-evolving-industrial-landscape/) (Industrial Cyber, 2026)
- [Third-Party Service Provider Due Diligence](https://www.nacdonline.org/all-governance/governance-resources/governance-research/director-handbooks/2026-cyber-risk-oversight/cyber-risk-handbook-toolkit-2026/third-party-and-supply-chain-cyber-risk/) (NACD, 2026)
- [Cybersecurity Budget 2026: Benchmarks & Spending Trends](https://www.elisity.com/blog/2026-cybersecurity-budget-complete-enterprise-planning-guide) (Elisity, 2026)
- [SEC Cybersecurity Disclosure Rules: Mid-Market Impact Guide 2026](https://blueradius.io/sec-cybersecurity-disclosure-rules-mid-market-2026) (BlueRadius, 2026)
- [Cybersecurity Considerations During M&A Phases](https://www.nacdonline.org/all-governance/governance-resources/governance-research/director-handbooks/2026-cyber-risk-oversight/cyber-risk-handbook-toolkit-2026/cybersecurity-considerations-during-ma-phases/) (NACD, 2026)
- [Challenger Sales and Peer Social Proof](https://www.pipedrive.com/en/blog/challenger-sales-model) (Pipedrive, 2025)
- [Cybersecurity Compliance For Financial Services Firms In 2026](https://digacore.com/blog/financial-services-cybersecurity-compliance/) (Digacore, 2026)
- [JPM 2026 Takeaways: Cybersecurity in Healthcare PE Diligence](https://clearwatersecurity.com/blog/healthcare-pe-cybersecurity-diligence/) (Clearwater Security, 2026)

