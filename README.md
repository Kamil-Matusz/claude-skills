# claude-skills

Personal [Claude Code](https://claude.com/claude-code) plugin marketplace by Kamil Matusz: coding conventions and workflow skills grouped into plugins by technology.

## Plugins

| Plugin | Description | Skills |
|---|---|---|
| `spring` | Conventions for Spring Boot projects: testing, code style, JPA, REST. | `given-when-then-tests`, `prefer-final-variables` |
| `react` | Conventions for React and Next.js projects: performance, rendering, data fetching. | `vercel-react-best-practices` |
| `security` | Security checks for the agent toolchain: auditing third-party skills, plugins and MCP servers. | `skill-audit` |

### spring
- **given-when-then-tests** - structures Java tests (JUnit, Mockito, AssertJ, Spring test slices, Testcontainers) with `//given` / `//when` / `//then` sections.
- **prefer-final-variables** - marks locals, parameters and constructor-injected fields `final`, skipping the cases where it breaks Hibernate, Jackson or Spring proxies.

### react
- **vercel-react-best-practices** - 70 React and Next.js performance rules across 8 categories (async, bundle, rendering, re-renders, server, client, JS), prioritized by impact. From Vercel Engineering, MIT license.

### security
- **skill-audit** - security audit of a third-party skill, plugin or MCP server before installing it: hijacking descriptions, hidden instructions, network calls, download-and-execute, secret reads, obfuscation, persistence, writes to agent config and symlinks escaping the directory.

## Installation

Add the marketplace in Claude Code:

```
/plugin marketplace add Kamil-Matusz/claude-skills
```

Install the plugins you need:

```
/plugin install spring@claude-skills
/plugin install react@claude-skills
/plugin install security@claude-skills
```

Skills trigger automatically when the task matches their description. You can also invoke one directly as `/<plugin>:<skill>`, e.g. `/spring:given-when-then-tests` or `/security:skill-audit`.

## Repository layout

```
.claude-plugin/marketplace.json        # marketplace manifest listing the plugins
plugins/<plugin>/.claude-plugin/plugin.json
plugins/<plugin>/skills/<skill>/SKILL.md
CHANGELOG.md
```

## Contributing

- Put a new skill under the plugin that owns it: `plugins/<plugin>/skills/<name>/SKILL.md`. The invocation prefix comes from the plugin directory.
- Skills are auto-discovered; don't list them in `plugin.json` and don't bump its `version` when adding a skill.
- Add an entry under `## [Unreleased]` in [CHANGELOG.md](CHANGELOG.md) for every change.
- Run `/reload-plugins` to pick up changes in the current Claude Code session.
