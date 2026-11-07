# CLAUDE.md

Claude Code plugin marketplace. Each plugin lives in `plugins/<plugin>/`,
its skills in `plugins/<plugin>/skills/<name>/SKILL.md`.

## Adding a skill
- Put the skill under the plugin that owns it. The invocation name
  (`/spring:<name>`) comes from the plugin directory.
- Skills are auto-discovered; never list them in `plugin.json`.

## Versioning
Installed copies update only when `version` in the plugin's `plugin.json`
changes, so bump it in every commit that changes a plugin (semver):
- patch: fixes and wording changes in existing skills,
- minor: a new skill,
- major: a skill removed or renamed.

## Testing
`/reload-plugins` picks up changes in the current session.