---
type: intel
subtype: vertical
vertical: mfg
source: closed-won corpus + NIST IR 8183r2 + CMMC DoD schedule + DBIR 2025
created: 2026-04-22
tags: [intel, v/mfg]
---

# Manufacturing

Mid-market wins + defense-adjacent angle. Wins: Bausch + Lomb ($58.5K pharma/optics), Millennium Print/Pokemon ($45K print mfg), Adama ($16K agri-chemicals). Active pipeline: [[../../10_Accounts/Mitsubishi Heavy]], [[../../10_Accounts/Metalex Manufacturing]]. Pattern: OT/IT convergence + CMMC for defense primes + NIST CSF 2.0 alignment. Plants and corporate stacks live in different tool universes. See [[../playbook/closed-won-patterns]].

## Regulatory surface

- **NIST CSF 2.0 Manufacturing Profile (NIST IR 8183r2).** Initial public draft open for comment through 2025-11-17. Realigns guidance to CSF 2.0 Functions including the new **Govern** function. Source: [NIST CSRC](https://csrc.nist.gov/News/2025/csf-2-0-manufacturing-profile-initial-draft).
- **CMMC 2.0 rollout (DFARS 252.204-7021).** Four-phase DoD schedule:
  - Phase 1: 2025-11-10 (self-assessment in solicitations).
  - **Phase 2: 2026-11-10 — mandatory C3PAO Level 2 certification for applicable CUI contracts.** This is the forcing event for defense-primes + suppliers.
  - Phase 3: 2027-11-10 (Level 3 assessments).
  - Phase 4: 2028-11-10 (full rollout).
  - Capacity crunch: ~80 authorized C3PAOs vs ~80,000 contractors. Wait times will exceed 18 months by Q3 2026. Source: [Secureframe](https://secureframe.com/hub/cmmc/proposed-final-rule).
- **ITAR / EAR** — for dual-use + defense suppliers.
- **ISO 27001 + ISO 27017/27018** — for global manufacturers with EU ops.
- **NIS2 (EU)** — applies to manufacturers in scope from 2024 transposition onwards.
- **IEC 62443** — OT/ICS security standard.

## What manufacturing CISOs care about

1. **OT/IT convergence visibility.** Corporate SIEM + plant OT monitoring rarely normalize into one board view. Onyxia's [[../product/features]] data fabric pulls both.
2. **CMMC Level 2 readiness against the Nov 2026 clock.** Asset inventory + framework scoring is table stakes. Losing a DoD contract renewal because C3PAO slots are full is a real risk.
3. **Third-party + supplier cyber hygiene.** Supply chain is the mfg attack surface. DBIR 2025: third-party breaches doubled YoY.
4. **Board reporting across global plants.** Multi-region, multi-regime (NIS2 in EU, CMMC in US, ISO globally).

## Who wins the meeting

Primary: CISO, VP Security, Head of OT Security.
Secondary thread: CIO, Plant IT Director, Head of Supply Chain Risk, GC (export-controlled shops).
See [[../personas/ciso]], [[../personas/vp-security]].

## Attack vectors (DBIR 2025)

Manufacturing saw a nearly sixfold surge in espionage-motivated breaches, jumping to 20% from 3% YoY. IP theft + ransomware dominate. OT/ICS systems lag on basic controls. Source: [Verizon 2025 DBIR manufacturing snapshot](https://www.verizon.com/business/resources/infographics/2025-dbir-manufacturing-snapshot.pdf).

## Play selection

- New CISO at global manufacturer: [[../../40_Plays/sivan-peer-intro]]. Example: Takao Tsukui at [[../../10_Accounts/Mitsubishi Heavy]].
- Pre-CMMC Phase 2 (Nov 2026) defense-prime: [[../triggers/sec-cyber-rule]] (broad compliance-deadline play).
- NIST CSF 2.0 Manufacturing Profile finalization window: asset inventory + Govern function gap.
- Post-breach peer: [[../triggers/breach-event]].

## Accounts in play

- [[../../10_Accounts/Mitsubishi Heavy]] — Japan HQ global industrial, MNDA signed 2026-04-20.
- [[../../10_Accounts/Metalex Manufacturing]] — Tier 1 manufacturing fit.

## Closed-won references

- Bausch + Lomb ($58.5K, pharma/optics) — regulated manufacturer.
- Millennium Print Group / Pokemon ($45K) — B. Fisher-sold, brand-critical print mfg.
- Adama ($16K, agri-chemicals) — Sivan-sold, global.

## Closed-lost references

YAGEO Group (churned), Amdocs (in-house method). Common thread: long-cycle global orgs with federated IT. See [[../playbook/closed-lost-patterns]].

## Language that lands

- "CMMC Phase 2 locks in November 2026. Most primes aren't instrumented to score their own Level 2 readiness today."
- "Espionage-motivated breaches in manufacturing jumped from 3% to 20% in a year per Verizon's DBIR. How is the board tracking that shift?"
- "Onyxia sits above your plant OT stack and your corporate SIEM, normalizes both, and produces a single board view." (verbatim-style anchor from [[../product/positioning]])

## Cross-references

- [[../playbook/closed-won-patterns]]
- [[../playbook/closed-lost-patterns]]
- [[../product/positioning]]
- [[../product/features]]
- [[../methodology/objections]]
- [[../industry/regulatory-calendar]]
- [[../industry/breach-report-synthesis]]
- [[../triggers/exec-hire]]
- [[../triggers/sec-cyber-rule]]
- [[../../40_Plays/sivan-peer-intro]]
- [[../../90_Templates/tpl-ciso-cold]]
- [[../../90_Templates/tpl-vpsec-cold]]
