---
name: caramelo-theme-development
description: 'Use when building, fixing, customizing, testing, or reviewing the Caramelo Theme Child runtime inside WordPress. Triggers: Caramelo Theme Child, Caramelo child theme, caramelotheme-main, Caramelo Dashboard, Caramelo Releases, Caramelo Import, Caramelo Imported Items, Caramelo Logs, Caramelo Rendering metabox, render engine Astro, Astro entry, release override, astro-page.php, caramelo_theme_child_loaded, caramelo-site-custom.php, Caramelo MU-plugin customization, tema filho Caramelo, tema child Caramelo, Dashboard do Caramelo, Releases do Caramelo, Import do Caramelo, Imported Items do Caramelo, Logs do Caramelo, metabox Caramelo Rendering, entrada Astro, override de release, functions.php do Caramelo, caramelo-page-meta.php, caramelo-router.php, caramelo-import.php, caramelo-astro.php, customizacao via MU-plugin do Caramelo. Do not use for adapting an external Astro project to the Caramelo release contract or for generic WordPress themes unrelated to Caramelo.'
argument-hint: 'What Caramelo page flow, runtime behavior, admin screen, release mapping, or project customization do you need help with inside WordPress?'
---

# Caramelo Theme Development

Use this skill for WordPress-side development on top of Caramelo Theme Child.

This skill is for building, fixing, reviewing, and maintaining the Caramelo child theme runtime inside WordPress. It focuses on page-level render mode selection, release resolution, routing, admin flows, import behavior, fallback handling, and project-specific customizations that depend on Caramelo being loaded.

## What This Skill Produces

- Minimal, maintainable Caramelo theme changes.
- Clear routing between Caramelo core files and the project-specific customization layer.
- A targeted validation plan for WordPress-side render mode, routing, import, admin, and fallback behavior.
- Clear boundaries between Caramelo runtime work and Astro source-project adaptation.

## When To Use

- Editing `caramelotheme-main`.
- Changing `functions.php`, `inc/caramelo-*.php`, `templates/astro-page.php`, or Caramelo docs and examples that ship with the theme.
- Adjusting the `Caramelo` admin area, including `Dashboard`, `Releases`, `Import`, `Imported Items`, or `Logs`.
- Changing page meta, supported post types, release settings, release validation, route resolution, import behavior, or fallback behavior.
- Adding project-specific behavior that should initialize from `caramelo_theme_child_loaded`.
- Choosing whether a project-specific integration belongs in a MU-plugin, the local custom file, or Caramelo core.

## Discovery Phrases

### English

- customize Caramelo Theme Child
- add code to Caramelo functions.php
- fix Caramelo Astro routing inside WordPress
- change the Caramelo Rendering metabox
- update Caramelo release validation or import behavior
- add a Caramelo project integration with caramelo_theme_child_loaded
- debug templates/astro-page.php in Caramelo
- change Caramelo admin screens like Dashboard, Releases, Import, Imported Items, or Logs
- update inc/caramelo-page-meta.php, inc/caramelo-router.php, or inc/caramelo-import.php

### Portuguese

- personalize o tema filho Caramelo
- adicione codigo ao functions.php do Caramelo
- corrija o roteamento Astro do Caramelo no WordPress
- ajuste o metabox Caramelo Rendering
- atualize a validacao de release ou a importacao do Caramelo
- adicione uma integracao de projeto com caramelo_theme_child_loaded
- depure o templates/astro-page.php do Caramelo
- ajuste as telas Dashboard, Releases, Import, Imported Items ou Logs do Caramelo
- altere o inc/caramelo-page-meta.php, inc/caramelo-router.php ou inc/caramelo-import.php

## Do Not Use

- Adapting an external Astro source project or build pipeline to the Caramelo release contract.
- Generic Astro component or layout work that is not targeting Caramelo publishing.
- Generic WordPress theme work unrelated to Caramelo.
- Reusable plugin logic that should not depend on Caramelo being the active theme.

## Load These References As Needed

- For the default Caramelo theme workflow, load [workflow](./references/caramelo-theme-workflow.md).
- For choosing the correct Caramelo file or customization surface, load [routing](./references/caramelo-theme-routing.md).
- For focused runtime checks, load [validation](./references/validation.md).
- For theme, customization-layer, and Astro-project ownership boundaries, load [boundaries](./references/caramelo-theme-boundaries.md).

## Procedure

1. Confirm the task belongs to Caramelo's WordPress runtime.
   - If the owner is the active Caramelo theme, continue here.
   - If the owner is an external Astro source project or build artifact, prefer `caramelo-astro-adaptation`.
   - If the change is generic WordPress theme work unrelated to Caramelo, prefer `wordpress-theme-development`.

2. Decide whether the change belongs in Caramelo core or the project customization layer.
   - If the behavior should ship as part of the Caramelo theme package for every install, keep it in theme core.
   - If it is site-specific or client-specific, prefer `wp-content/mu-plugins/caramelo-site-customizations.php`.
   - Use `caramelo-site-custom.php` only as a local fallback when the deployment flow accepts that tradeoff.

3. Identify the owning Caramelo surface first.
   - `inc/caramelo-settings.php` for global settings and admin release configuration.
   - `inc/caramelo-page-meta.php` for render mode, Astro entry, release override, and supported post type metadata.
   - `inc/caramelo-router.php` for `template_include` takeover rules.
   - `templates/astro-page.php` for final document output and WordPress fallback handling.
   - `inc/caramelo-import.php` for ZIP import, staging, draft page creation, conflict handling, and release lifecycle.
   - `inc/caramelo-astro.php` for release discovery, manifest resolution, HTML preparation, and asset rewriting.
   - `docs/` and `examples/` for shipped team guidance that belongs to the Caramelo package.

4. Start from the most concrete anchor.
   - Prefer a named admin screen, metabox field, hook, query condition, release validation error, imported item behavior, or fallback mismatch.
   - Read the owning file before exploring neighboring surfaces.

5. Preserve Caramelo constraints.
   - WordPress stays canonical for URLs, status, SEO, permissions, and editorial governance.
   - Astro mode only applies to supported singular content explicitly configured for Caramelo.
   - If Astro resolution fails, the request should fall back to the normal WordPress template flow.
   - Keep project-specific snippets outside Caramelo core when possible.

6. Validate narrowly.
   - Check the normal WordPress path still works.
   - Check the Astro path resolves the expected release, entry, and HTML file.
   - Check admin, JSON, embed, password-protected, and preview behavior for the touched slice when relevant.
   - If import behavior changed, verify the release and imported item state that the change directly affects.

## Decision Points

### Caramelo Core Or Project Customization?

- Caramelo core: reusable runtime, admin UX, release contract enforcement, routing, import lifecycle, shipped docs, and examples.
- Project customization layer: site-specific webhooks, CRM wiring, custom tracking, additional hooks, or local business logic.

### Which Caramelo Surface Owns The Change?

- Bootstrap and custom loading: `functions.php`, `inc/caramelo-custom.php`, `caramelo_theme_child_loaded`.
- Page-level behavior: `inc/caramelo-page-meta.php`.
- Routing and fallback: `inc/caramelo-router.php`, `templates/astro-page.php`.
- Release and HTML resolution: `inc/caramelo-astro.php`.
- Admin settings and release operations: `inc/caramelo-settings.php`.
- Import and imported-content lifecycle: `inc/caramelo-import.php`.

### When Is The Change Complete?

- The behavior lives in the correct Caramelo surface.
- Site-specific code stayed outside core when appropriate.
- The normal WordPress path and the Astro path were both considered.
- The narrowest relevant validation was run.