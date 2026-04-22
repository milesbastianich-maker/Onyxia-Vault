---
type: play
active: false
blast_radius: high (writes to HubSpot)
rollback_criteria: any incorrect write detected; pause until root cause fixed
measurement_precondition: field-by-field mapping approved by Miles in writing
created: 2026-04-22
tags: [play, autonomy]
---

# Autonomy — Vault-to-HubSpot MEDDPICC Sync

## What it does

Writes MEDDPICC slot values from vault account files (`10_Accounts/{Company}.md` frontmatter + body sections) into HubSpot deal custom properties. Currently: MEDDPICC lives in vault, HubSpot has the deal stage + amount. Sales management wants MEDDPICC visibility in HubSpot reports. This closes that gap without Miles re-typing.

## Why

Currently the vault is the source of truth for MEDDPICC, and HubSpot is silent on it. That means Brad (manager) and Sivan (CEO) can't see MEDDPICC progress in HubSpot dashboards. Miles currently either (a) types MEDDPICC into HubSpot manually every time it updates, or (b) skips it and sales-management asks him in-person. Both are bad.

## Trigger conditions

- Vault account file frontmatter or MEDDPICC body section changed since last sync.
- Run on EOD shift daily.
- Only syncs for deals owned by Miles (owner_id = 86806986). Never writes to other reps' deals.

## Pipeline

1. Auditor (read-only) diffs vault state vs last-sync state.
2. For each changed account: compile MEDDPICC slot values to HubSpot custom property format.
3. **Preview write** to `#miles-ai-ops` — list of deals + new values. Miles ✅ all or individual.
4. On ✅: execute HubSpot `update_object` on the deal.
5. Log to `50_Intel/methodology/measurement-log.md` with `action: hubspot_sync` + accounts affected.

## HubSpot property mapping (MUST be approved by Miles before activation)

Proposed custom properties (create if not exist):
- `meddpicc_metrics` — text
- `meddpicc_economic_buyer` — text (name + title)
- `meddpicc_decision_criteria` — text
- `meddpicc_decision_process` — text
- `meddpicc_paper_process` — text
- `meddpicc_identify_pain` — text
- `meddpicc_champion` — text (name + role + strength score 1-5)
- `meddpicc_competition` — text

## Blast radius

**High.** This is the only autonomy mechanism that writes to HubSpot beyond the autonomy-matrix-approved contact-create + activity-log. Any bug writes wrong data to the CRM. Deal-stage changes are NOT in scope.

## Rollback criteria

- ANY incorrect write → immediate kill, `active: false`, full audit.
- HubSpot schema mismatch → kill, update property mapping, Miles re-approves.
- Vault state reverted but sync already fired → manual HubSpot correction required.

## Measurement precondition

1. Field-by-field mapping signed off by Miles in writing (vault note with his ✅).
2. HubSpot custom properties created and schema-locked.
3. 5 accounts manually synced as a shadow run (vault → Miles types into HubSpot → auditor diffs) to verify mapping correctness.
4. Rollback script written and tested: `revert-hubspot-sync.sh` that can restore from the last-sync snapshot.

## Kill switch

Frontmatter flip + immediate EOD shift skip. Miles can also manually null the custom property values in HubSpot if a bad write lands.

## Cross-references

- [[../00_Index/CLAUDE]] — autonomy matrix (currently prohibits this category, will need explicit unlock)
- [[../.claude/agents/onyxia-auditor]]
- [[./quarterly-self-audit]]
