---
name: wordpress-plugin-development
description: 'Use when fixing, building, customizing, testing, or reviewing WordPress plugins, mu-plugins, and network plugins. Triggers: WordPress plugin, plugin bug, plugin regression, custom plugin, mu-plugin, must-use plugin, network plugin, multisite-aware plugin, plugin bootstrap, plugin header, activation hook, deactivation hook, uninstall.php, Settings API, admin menu, admin page, shortcode, widget, custom post type, taxonomy, metabox, plugin REST route, admin-ajax handler, WP-CLI command, cron job, hooks, filters, custom database table, data migration, plugin security, plugin performance, plugin review. Do not use for WordPress Core or theme development.'
argument-hint: 'What WordPress plugin change, bug, architecture, or workflow do you need help with?'
---

# WordPress Plugin Development

Use this skill for WordPress plugin work only.

This skill is for building, fixing, reviewing, and maintaining WordPress plugins, including standard plugins, must-use plugins, network plugins, and feature plugins. It is not for WordPress Core changes, theme development, or general site administration unrelated to plugin code.

## What This Skill Produces

- Minimal, maintainable WordPress plugin changes.
- Clear routing between bootstrap, admin, front-end integration, data, and integration surfaces.
- A targeted validation plan for plugin behavior, security, compatibility, and project-defined quality checks.
- Clear boundaries between plugin responsibilities and logic that belongs in themes or WordPress Core.

## When To Use

- Fixing a WordPress plugin bug or regression in the main plugin file, includes, admin pages, REST endpoints, hooks, shortcodes, widgets, or integration code.
- Building or reviewing plugin architecture, file layout, activation and deactivation behavior, uninstall flow, or bootstrap logic.
- Implementing or reviewing custom post types, taxonomies, settings pages, metaboxes, admin menus, cron jobs, WP-CLI commands, or background tasks in a plugin.
- Working on plugin security, capabilities, nonces, sanitization, escaping, SQL preparation, or performance.
- Checking compatibility with multisite, must-use plugins, network activation, or plugin-specific upgrade paths.
- Deciding whether a change belongs in the plugin, the active theme, or WordPress Core.

## Discovery Phrases

- fix a WordPress plugin bug
- review this plugin architecture
- investigate a plugin regression after activation
- add a settings page to a plugin
- debug a plugin REST route
- should this feature survive a theme switch
- harden this plugin form with nonce and capability checks

## Do Not Use

- WordPress Core patches, Core regressions, or contributor workflow as the main task.
- Theme templates, `theme.json`, theme layout, or theme-specific rendering as the main task.
- General site support that does not require editing plugin code.

## Load These References As Needed

- For common plugin workflow and structure, load [plugin workflow](./references/plugin-workflow.md).
- For choosing the correct file or subsystem, load [plugin routing](./references/plugin-routing.md).
- For plugin-focused validation, load [validation](./references/validation.md).
- For deciding between plugin, theme, and Core responsibilities, load [plugin boundaries](./references/plugin-boundaries.md).

## Procedure

1. Confirm that the task belongs to a plugin.
   - If the change is mainly reusable functionality, integrations, backend features, admin workflows, data models, or behavior that should survive a theme switch, continue here.
   - If it is mainly presentation, layout, templates, or theme-owned rendering, prefer a theme.
   - If it changes WordPress platform behavior itself, prefer WordPress Core.

2. Identify the plugin surface first.
   - Determine whether the owning area is the main plugin bootstrap file, an include or service class, an admin page, a REST route, an AJAX handler, an activation or uninstall routine, a CLI command, a cron task, or a data layer.
   - Check whether the plugin is a standard plugin, must-use plugin, network plugin, or multisite-aware plugin.

3. Start from the most concrete anchor.
   - Prefer a named hook, endpoint, command, admin screen, function, class, file, user-visible regression, or failing validation result.
   - Read the nearest owning implementation before exploring broadly.
   - Prefer the code that directly computes behavior, handles input, or integrates with WordPress over generic wiring layers.

4. Preserve plugin constraints.
   - Keep plugin logic reusable and independent from the active theme when appropriate.
   - Match the existing plugin architecture and nearby naming conventions.
   - Use WordPress plugin APIs, hooks, options, metadata, REST, cron, and admin patterns before inventing custom systems.
   - Apply capabilities, nonces, sanitization, escaping, SQL preparation, internationalization, and safe upgrade paths where relevant.

5. Choose the smallest realistic validation.
   - If behavior changes in PHP, run the narrowest available plugin tests or syntax and standards checks.
   - If the change affects admin flows, verify the relevant screen and permissions.
   - If the change affects REST, AJAX, cron, CLI, or activation paths, verify the owning execution surface directly.
   - If the project has automated tests, run the smallest slice that can disprove the change quickly.

6. Validate narrowly first.
   - Run the smallest command or manual check that can falsify the change.
   - Repair the same slice before widening scope.
   - Escalate to broader validation only when the touched surface warrants it.

7. Finish with plugin-ready hygiene.
   - Confirm that activation, deactivation, upgrade, or uninstall behavior remains safe when relevant.
   - Ensure strings are translatable and output is escaped.
   - Summarize the functional impact, validation performed, and any remaining compatibility or migration risks.

## Decision Points

### What Kind Of Plugin Surface Is This?

- Bootstrap and lifecycle: main plugin file, activation, deactivation, uninstall, dependency checks.
- Admin and settings: admin menus, settings pages, metaboxes, permissions, forms, and notices.
- Runtime integrations: hooks, filters, shortcodes, widgets, blocks, REST routes, AJAX handlers, cron jobs, and CLI commands.
- Data and persistence: options, post meta, term meta, custom tables, upgrade routines, and migrations.

### Plugin, Theme, Or Core?

- Reusable functionality that should survive a theme switch: plugin.
- Presentation, templates, layout, and theme-owned rendering: theme.
- Platform behavior inside WordPress itself: Core.

### When Is The Change Complete?

- The code lives in the correct plugin surface.
- The implementation matches nearby plugin patterns.
- The narrowest relevant validation has been run.
- Security, capability, and data-handling concerns were checked.
- Activation, upgrade, or uninstall edge cases were considered when relevant.