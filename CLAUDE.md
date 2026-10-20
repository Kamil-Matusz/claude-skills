# CLAUDE.md

Claude Code plugin marketplace. Each plugin lives in `plugins/<plugin>/`,
its skills in `plugins/<plugin>/skills/<name>/SKILL.md`.

## Adding a skill
- Put the skill under the plugin that owns it. The invocation name
  (`/spring:<name>`) comes from the plugin directory.
- Skills are auto-discovered; never list them in `plugin.json`.
- Never bump `version` in `plugin.json` when adding a skill.
- Every change needs a `CHANGELOG.md` entry under `## [Unreleased]`.

## Testing
`/reload-plugins` picks up changes in the current session.