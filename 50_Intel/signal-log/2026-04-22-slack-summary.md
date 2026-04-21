---
type: intel
subtype: slack-staging
created: 2026-04-22
target_channel: C0AUB4DATP0
tags: [intel]
---

# Slack Post Staging — #miles-ai-ops

Slack MCP tool was not loaded in this environment. Paste the block below into `#miles-ai-ops` (channel ID `C0AUB4DATP0`).

---

**Top-50 pipeline staged, top-5 drafted — 2026-04-22**

Seeded from the 5 biggest closed-won deals (Centra, WellStar, Premera, Radiant Logic, Port Authority NY/NJ). Full list: `50_Intel/signal-log/2026-04-22-prospect-staging.md`

ICP score distribution: 8 at 5, 22 at 4, 20 at 3.

15 contact stubs written to `20_Contacts/` — all flagged `needs_verification: true` until ZoomInfo accuracy scoring runs.

**Top-5 drafts (all in `50_Intel/signal-log/2026-04-22-drafts.md`, NOT yet in Gmail):**

1. Tariq Habib (MTA NY) — peer-call with Sivan
   *Subject:* After LA Metro, how the MTA board is asking about transit cyber
   *Open:* Saw the LA Metro cyberattack claim in March. 500 TB wiped, rail yard management hit. Board conversations about transit resilience are probably live at MTA too.

2. Paul Curylo (Inova Health) — 15-min ask
   *Subject:* How Centra handles board reporting on cyber posture
   *Open:* You rebuilt Inova's cyber operations from 2019. Data governance, program maturity, all on public record. The one piece that usually stays manual even after rebuild is board-ready reporting.

3. Monique Hart (Piedmont Healthcare) — 15-min ask
   *Subject:* 19 hospitals, one view for the Piedmont board
   *Open:* Reached out because Piedmont is the closest structural peer to a customer of ours in Georgia. 19 hospitals is a lot of dashboards to reconcile before a board update.

4. Thien Lam (BayCare Health) — 15-min ask
   *Subject:* 14 hospitals, DR posture, and the board pack
   *Open:* Read your notes on DR as a first-class concern. The piece a lot of 14-hospital IDNs still do manually is the reporting that sits above DR + SIEM + GRC and goes to the board.

5. Sanjeev Sah (Novant Health) — 15-min ask
   *Subject:* Year-two program build at Novant
   *Open:* Year two is when the multi-year cyber plan you brought from CommonSpirit starts to need measurement behind it. Board wants proof the program is moving.

**Gating before send:**
- HubSpot dedupe on all 5 (no territory conflict check ran — MCP not loaded)
- ZoomInfo email-accuracy verification
- Miles's ✅ in-thread per each draft

**Environment caveat:** ZoomInfo + HubSpot + Gmail + Slack MCP tools were not loaded. Pipeline built from public research + vault knowledge. Downstream agent or Miles must run the three MCP-gated steps before send. Flag if anything needs redoing.
