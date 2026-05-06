---
type: ops-doc
status: action-required
created: 2026-05-05
owner: miles
---

# Granola Plugin — Setup Steps Miles Must Run

The plugin files are already on disk under `~/ObsidianVault/.obsidian/plugins/granola-meetings-simple-sync/` and the plugin ID has been added to `community-plugins.json`. Two filesystem steps left, plus three GUI steps.

Plugin: `granola-meetings-simple-sync` (philfreo/obsidian-granola-plugin v2.0.3, last release 2026-03-16).

## What's already done (filesystem-side, by The Brain)

- Plugin `main.js` (691KB) and `manifest.json` downloaded to `.obsidian/plugins/granola-meetings-simple-sync/`
- Plugin ID added to `.obsidian/community-plugins.json`

## Steps left for Miles (≈8 minutes total)

### 1. Restart Obsidian

Close Obsidian fully (Cmd-Q), reopen the vault. The plugin won't load otherwise.

### 2. Trust + verify the plugin appears

- Settings → Community plugins
- If Obsidian asks "Trust this third-party plugin?" → click Trust
- You should see "Granola Meetings Simple Sync" in the Installed plugins list with a toggle. Toggle it ON.

### 3. Connect to Granola via OAuth

- In Settings → Community plugins → click the gear icon next to "Granola Meetings Simple Sync" (this opens plugin settings)
- Click **Connect to Granola** button
- Browser opens. Authorize via your existing Granola login (same one you use for Granola desktop)
- You'll be redirected back to Obsidian automatically

### 4. Configure output folder + filename pattern (CRITICAL — match vault convention)

In the plugin's settings panel:

| Setting | Value |
|---|---|
| Output folder | `30_Meetings` |
| Filename template | `{{date:YYYY-MM-DD}}-{{title-slug}}-debrief` |
| Frontmatter template | use the template at `~/ObsidianVault/90_Templates/tpl-meeting-debrief.md` if the plugin supports template paths; otherwise hand-edit the inline template to match Schema convention (see below) |
| Auto-link attendees | ON (creates `[[Person]]` links per attendee) |
| Person folder | `20_Contacts` |
| Sync interval | 15 minutes (or "On Granola event") |

**If the plugin does not support a vault-template path,** paste this inline frontmatter template into the plugin's frontmatter setting:

```yaml
---
type: meeting
subtype: debrief
date: {{date}}
account: 
attendees: {{attendees}}
granola_meeting_id: {{meeting_id}}
duration_min: {{duration}}
tags: [meeting, debrief]
---
```

### 5. Trigger an initial sync

- Click "Sync now" in plugin settings
- Verify a debrief file lands at `~/ObsidianVault/30_Meetings/YYYY-MM-DD-{title}-debrief.md`
- Open it and confirm:
  - Frontmatter matches the schema
  - Body has Granola's summary + transcript link
  - Attendees are wikilinked to `20_Contacts/`

### 6. Check the existing prep files get matched

The plugin pulls Granola meetings by date+title. For the 6 stale prep files below, after the initial sync runs:

- IVISA prep (2026-04-27, 15:00 ET, 30 min, Susan Lloyd) → expect debrief at `30_Meetings/2026-04-27-ivisa-debrief.md`
- Armstrong/TMF prep (2026-04-28, 10:30 ET, 45 min, Justin Armstrong) → expect debrief
- CyberDiligent prep (2026-04-29, 11:00 ET, 30 min, Russell Okoth) → expect debrief
- AKUVO POC prep (2026-04-30, 11:00 ET, 30 min, Dan McNamara) → note: per AKUVO Timeline, Dan punted to May 21; debrief should reflect "punt", not full POC scoping
- Spire Orthopedic prep (2026-04-30, 15:30 ET, 30 min, V. Sardanopoli) → expect debrief
- Encora prep (2026-04-22, with Clifford Vazquez) → expect debrief

If any of these meetings did not actually happen or were not recorded by Granola, the plugin will skip them. Cross-check against your Granola desktop app meeting list.

## Skill-level open question (flag for Miles)

The active Claude Code skill at `~/.claude/skills/fireflies-debrief-pull/SKILL.md` is hard-wired to the Fireflies API (paused per memory `project_fireflies_wired.md`). It does NOT read from Granola. There is no `granola-debrief-pull` skill installed today.

Two paths:

1. **Plugin-only** — let the philfreo plugin handle ingestion. No Claude skill required for the pull. The drafter and operator agents can read the resulting debrief files via filesystem. This is the simplest path.

2. **Claude skill rewrite** — fork `fireflies-debrief-pull` to `granola-debrief-pull`, point it at the Granola MCP (already wired user-scope per `reference_granola_mcp.md`). This gives you on-demand debriefs from Claude Code without waiting for the plugin's sync interval. Worth it if you want shift agents to pull a single specific meeting on demand.

Recommendation: start with path 1. Add path 2 if you find yourself running `granola-debrief-pull <meeting-title>` more than twice a week.

## Sanity check after setup

After the first sync:

```bash
ls ~/ObsidianVault/30_Meetings/ | grep debrief | wc -l
```

Should jump from 1 (the hand-written Elevate Textiles debrief) to 7+ once the historical Granola meetings sync in.
