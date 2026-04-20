# Plugin Boundaries

Use this reference when deciding whether code belongs in a plugin, a theme, or WordPress Core.

## Plugin Responsibilities

- Reusable functionality that should continue working after a theme switch.
- Admin settings, business logic, content models, integrations, APIs, data handling, and feature modules.
- REST routes, AJAX handlers, scheduled tasks, WP-CLI commands, and upgrade routines.

## Theme Responsibilities

- Layout, templates, styling, template parts, patterns, and theme-owned presentation.
- Theme supports, theme.json configuration, and theme-specific front-end rendering.

## Core Responsibilities

- Platform behavior inside WordPress itself.
- Shared admin and runtime behavior maintained by WordPress Core.
- Bugs or regressions in WordPress source files rather than in plugin code.

## Boundary Heuristics

- If the functionality should survive a theme switch, it probably belongs in a plugin.
- If the task is primarily presentation or theme-owned rendering, it belongs in a theme.
- If the task requires modifying WordPress internals, it belongs in Core.