# Plugin Routing

Use this reference to choose the correct file before editing.

## By Concern

- Plugin bootstrap, constants, loader setup, dependency checks, and lifecycle hooks: main plugin file or bootstrap module.
- Activation, deactivation, uninstall, and upgrade routines: lifecycle or migration files.
- Settings pages, admin menus, permissions, admin notices, and forms: admin-facing modules.
- Hooks and filters that alter WordPress behavior at runtime: the nearest feature module or integration layer.
- REST routes, AJAX actions, WP-CLI commands, and cron tasks: the matching transport or execution handler.
- Custom post types, taxonomies, and metadata registration: the feature module that owns the content model.
- Options, custom tables, migrations, or persistence code: the owning data layer.

## Routing Heuristics

- If the bug happens during plugin activation or update, start with lifecycle and migration code.
- If the bug appears in wp-admin, start with the admin page, form handler, permission check, or notice renderer.
- If the bug appears through an API or asynchronous path, start with the matching REST, AJAX, cron, or CLI handler.
- If the behavior should remain available after switching themes, keep it in the plugin.
- If the change is only about visual presentation tied to a theme, do not force it into the plugin.