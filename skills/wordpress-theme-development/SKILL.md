---
name: wordpress-theme-development
description: 'Use when fixing, building, customizing, testing, or reviewing WordPress themes and child themes. Triggers: WordPress theme, theme bug, theme regression, block theme, classic theme, child theme, theme.json, templates, template parts, patterns, template hierarchy, Site Editor, full site editing, FSE, global styles, editor styles, header.php, footer.php, functions.php in a theme, style.css in a theme, Customizer, responsive layout, accessibility, semantic markup, theme review. Do not use for WordPress Core or plugin development.'
argument-hint: 'What WordPress theme change, bug, template, or workflow do you need help with?'
---

# WordPress Theme Development

Use this skill for WordPress theme work only.

This skill is for building, fixing, reviewing, and maintaining WordPress themes, including block themes, classic themes, and child themes. It is not for WordPress Core changes, plugin development, or general site support unrelated to theme code.

## What This Skill Produces

- Minimal, maintainable WordPress theme changes.
- Clear routing between block themes, classic themes, and child themes.
- A targeted validation plan for templates, styles, editor behavior, accessibility, and responsive output.
- Clear boundaries between theme responsibilities and logic that belongs in plugins or Core.

## When To Use

- Fixing a WordPress theme bug or regression in templates, template parts, `functions.php`, `style.css`, `theme.json`, patterns, or front-end assets.
- Building or reviewing block theme, classic theme, or child theme behavior.
- Working on template hierarchy, archive and singular templates, navigation, headers, footers, sidebars, or global styles.
- Implementing theme supports, asset loading, menus, widget areas, patterns, or theme-level editor integration.
- Checking accessibility, responsive behavior, semantics, i18n, and front-end rendering quality for a theme.
- Deciding whether a change belongs in the theme, a plugin, or WordPress Core.

## Discovery Phrases

- fix a WordPress theme bug
- review this block theme change
- investigate a theme regression in template hierarchy
- update theme.json for global styles
- debug a child theme override
- build a template part for a block theme
- improve accessibility in a WordPress theme template

## Do Not Use

- WordPress Core patches, Core regressions, or contributor workflow as the main task.
- Plugin architecture, plugin settings screens, custom post type business logic, or reusable backend features as the main task.
- General site administration that does not require editing theme code.

## Load These References As Needed

- For common theme workflow and structure, load [theme workflow](./references/theme-workflow.md).
- For choosing the correct file or theme type, load [theme routing](./references/theme-routing.md).
- For theme-focused validation, load [validation](./references/validation.md).
- For deciding between theme, plugin, and Core responsibilities, load [theme boundaries](./references/theme-boundaries.md).

## Procedure

1. Confirm that the task belongs to a theme.
   - If the change is mainly presentation, templates, layout, styles, theme supports, editor styles, or theme configuration, continue here.
   - If it is mainly reusable business logic, settings screens, data models, or site-wide features independent of the active theme, prefer a plugin.
   - If it changes platform behavior in WordPress itself, prefer WordPress Core.

2. Identify the theme type first.
   - Determine whether the task is in a block theme, classic theme, or child theme.
   - Check whether the owning surface is `theme.json`, a template, a template part, a PHP template file, a pattern, a stylesheet, or `functions.php`.

3. Start from the most concrete anchor.
   - Prefer a named template, file, selector, hook, user-visible regression, or failing validation result.
   - Read the nearest owning template or config file before exploring broadly.
   - Prefer the file that directly controls rendering or asset loading over general bootstrap code.

4. Preserve theme constraints.
   - Keep theme logic focused on presentation and theme integration.
   - Match the existing theme architecture and nearby naming conventions.
   - Use template hierarchy, `theme.json`, template parts, patterns, and theme supports before inventing custom systems.
   - Apply accessibility, responsive design, semantic HTML, escaping, sanitization, and internationalization where relevant.

5. Choose the smallest realistic validation.
   - If markup or layout changes, verify the relevant front-end and editor views.
   - If styles change, verify responsive behavior and visual regressions at the affected breakpoints.
   - If configuration changes in `theme.json`, verify that global styles and editor output reflect the change.
   - If PHP templates or setup code change, run the narrowest syntax or standards validation available in the project.

6. Validate narrowly first.
   - Run the smallest command or manual check that can disprove the change quickly.
   - Repair the same slice before widening scope.
   - Escalate to broader checks only when the touched surface warrants it.

7. Finish with theme-ready hygiene.
   - Confirm the change behaves correctly across the affected templates and breakpoints.
   - Ensure strings are translatable and output is escaped.
   - Summarize the rendering impact, validation performed, and any remaining edge cases.

## Decision Points

### Block Theme, Classic Theme, Or Child Theme?

- Block theme: prioritize `theme.json`, HTML templates, template parts, patterns, and editor-facing global styles.
- Classic theme: prioritize PHP templates, template hierarchy, `functions.php`, stylesheets, menus, and widget areas.
- Child theme: prefer overrides and additive customization instead of copying unnecessary parent theme logic.

### Theme, Plugin, Or Core?

- Presentation, layout, front-end rendering, theme styles, and theme-specific editor output: theme.
- Reusable features, business logic, data management, or admin behavior independent of the active theme: plugin.
- Platform behavior in WordPress itself: Core.

### When Is The Change Complete?

- The code lives in the correct theme surface.
- The implementation matches the theme type and nearby patterns.
- The narrowest relevant validation has been run.
- The affected front-end or editor output was checked.
- Accessibility, responsive behavior, i18n, and output safety were considered.