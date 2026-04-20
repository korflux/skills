name: elementor-free-development
description: 'Use when building, fixing, customizing, testing, or reviewing reusable Elementor Free addon code such as widgets, controls, editor extensions, Finder items, context menu entries, managers, and scripts or styles. Triggers: Elementor addon, custom Elementor widget, widget do Elementor, Elementor control, controle do Elementor, inject controls, injetar controles, editor panel, painel do editor, Finder, context menu, Elementor manager, widget scripts, scripts do widget, control styles, estilos do controle. Do not use for Elementor Pro-only features such as dynamic tags, form actions, form fields, Theme Builder conditions, or for Hello parent theme or child theme code.'
argument-hint: 'What reusable Elementor Free addon, widget, control, editor extension, or asset change do you need help with?'
---

# Elementor Free Development

Use this skill for Elementor Free addon and extension work.

This skill is for building, fixing, reviewing, and maintaining Elementor Free integrations that live in addon plugins or similar reusable packages. It focuses on Elementor core APIs that do not require Pro-specific extension points.

## What This Skill Produces

- Minimal, maintainable Elementor Free addon changes.
- Clear routing between addon bootstrap, widgets, controls, editor extensions, Finder, context menu, managers, and assets.
- A targeted validation plan for editor behavior, preview behavior, frontend output, and compatibility.
- Clear boundaries between reusable Elementor Free addon code and Hello Theme or child theme customization.

## When To Use

- The change belongs in reusable addon or plugin code that should survive a theme switch.
- Building or fixing Elementor addon bootstrap, compatibility checks, namespaces, main class, and initialization flow.
- Implementing or reviewing custom widgets, custom controls, injected controls, editor panels, editor tabs, Finder categories or items, or context menu actions and groups.
- Working on Elementor Free scripts and styles for frontend, editor, preview, widgets, or controls.
- Reviewing manager registration, hook usage, selectors, dependencies, output caching, or DOM optimization in Elementor Free surfaces.

## Discovery Phrases

### English

- build a custom Elementor widget
- add a new Elementor control
- inject controls into an existing element
- extend the Elementor editor panel
- add a Finder item in Elementor
- add a context menu action in Elementor
- register widget scripts or styles

### Portuguese

- crie um widget customizado do Elementor
- adicione um novo controle do Elementor
- injete controles em um elemento existente do Elementor
- estenda o painel do editor do Elementor
- adicione um item ao Finder do Elementor
- adicione uma acao ao menu de contexto do Elementor
- registre scripts e estilos de um widget do Elementor

## Do Not Use

- Elementor Pro form actions, form fields, dynamic tags, or Theme Builder conditions.
- Theme location registration or display inside `hello-theme-main` or a Hello child theme.
- Hello Elementor parent theme development.
- Hello Elementor child theme customization.
- Generic WordPress plugin or theme work with no Elementor API dependency.

## Load These References As Needed

- For addon structure and implementation flow, load [workflow](./references/elementor-free-workflow.md).
- For choosing the correct Elementor Free subsystem, load [routing](./references/elementor-free-routing.md).
- For focused checks, load [validation](./references/validation.md).
- For ownership and dependency boundaries, load [boundaries](./references/elementor-free-boundaries.md).

## Procedure

1. Confirm the task belongs to Elementor Free.
   - If the task depends on widgets, controls, editor extensions, Finder, context menu, managers, or assets in Elementor core, continue here.
   - If it depends on forms, dynamic tags, or conditions, prefer Elementor Pro.
   - If it edits `hello-theme-main` or `hello-theme-child-master`, prefer the Hello Elementor theme skills.

2. Identify the owning Elementor Free surface.
   - Determine whether the change lives in addon bootstrap, a widget class, a control class, an editor integration module, a Finder or context menu integration, or an asset registration path.

3. Start from the most concrete anchor.
   - Prefer a named hook, widget class, control type, panel, tab, Finder item, context menu action, or failing output path.

4. Preserve addon constraints.
   - Keep reusable behavior in the addon package.
   - Use documented Elementor hooks, managers, selectors, and registration callbacks.
   - Keep editor-only assets scoped to the editor.
   - Do not solve site-specific theme overrides here.

5. Validate narrowly.
   - Verify registration in the editor.
   - Verify preview or frontend output where relevant.
   - Run the smallest available syntax, lint, or test check when available.

## Decision Points

### What Kind Of Elementor Free Surface Is This?

- Addon bootstrap and lifecycle.
- Widgets and controls.
- Editor panels, tabs, Finder, and context menu.
- Scripts, styles, output, and performance.

If the change requires editing a Hello theme file, it probably does not belong here.

### When Is The Change Complete?

- The code lives in the correct addon surface.
- The change matches nearby Elementor Free patterns.
- The affected editor and or frontend behavior was checked.