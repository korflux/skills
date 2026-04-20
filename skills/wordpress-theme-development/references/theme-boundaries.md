# Theme Boundaries

Use this reference when deciding whether code belongs in a theme, a plugin, or WordPress Core.

## Theme Responsibilities

- Layout, templates, styling, template parts, patterns, and front-end presentation.
- Theme supports, menus, widget areas, editor styles, and design tokens.
- Theme-specific rendering choices tied to the active theme.

## Plugin Responsibilities

- Reusable business logic that should survive a theme switch.
- Custom post types, taxonomies, settings pages, integrations, data models, and backend workflows.
- Shortcodes, APIs, or features that are not primarily presentation concerns.

## Core Responsibilities

- Platform behavior inside WordPress itself.
- Shared runtime APIs and admin behavior maintained by WordPress Core.
- Bugs or regressions in `wp-admin`, `wp-includes`, or other WordPress Core files.

## Boundary Heuristics

- If the feature should keep working after switching themes, it probably belongs in a plugin.
- If the task changes visual presentation or theme-owned rendering, it belongs in the theme.
- If the task requires modifying WordPress platform internals, it belongs in Core.