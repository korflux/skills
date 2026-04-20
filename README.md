# skills

WordPress-focused agent skills for the open agent skills ecosystem.

This repository publishes three separate skills with intentionally different discovery surfaces so agents can route requests more accurately between WordPress Core, theme development, and plugin development.

## Available Skills

- `wordpress-core-development`: for WordPress Core internals, `wordpress-develop`, `wp-admin`, `wp-includes`, Trac, Core tests, and contributor workflow.
- `wordpress-theme-development`: for block themes, classic themes, child themes, `theme.json`, templates, template hierarchy, global styles, and theme accessibility.
- `wordpress-plugin-development`: for plugin architecture, activation and uninstall flows, Settings API, REST routes, admin pages, WP-CLI, cron jobs, and reusable WordPress features.

## Install

List available skills:

```bash
npx skills add korflux/skills --list
```

Install one skill globally:

```bash
npx skills add korflux/skills --skill wordpress-core-development -g -y
```

```bash
npx skills add korflux/skills --skill wordpress-theme-development -g -y
```

```bash
npx skills add korflux/skills --skill wordpress-plugin-development -g -y
```

Install all skills:

```bash
npx skills add korflux/skills --skill '*' -g -y
```

## Repository Layout

```text
skills/
  wordpress-core-development/
  wordpress-theme-development/
  wordpress-plugin-development/
```

Each skill contains its own `SKILL.md` plus focused reference files for workflow, routing, validation, and boundaries.

## Goals

- Keep WordPress Core, theme, and plugin work separate.
- Improve auto-discovery by using stronger, domain-specific triggers.
- Reduce ambiguous routing between presentation, reusable functionality, and WordPress internals.