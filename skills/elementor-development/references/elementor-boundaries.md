# Elementor Ecosystem Boundaries

Use this reference when deciding whether a task belongs in Elementor Free, Elementor Pro, Hello Elementor parent theme, Hello Elementor child theme, or outside the Elementor skill family.

## Elementor Free

- Reusable addon or plugin code for addon bootstrap, widgets, controls, editor extensions, Finder, context menu, managers, and core Elementor scripts or styles.

## Elementor Pro

- Reusable addon or plugin code for dynamic tags, form actions, form fields, forms hooks, and Pro-only Theme Builder condition APIs.

## Hello Elementor Parent Theme

- Parent theme hooks, theme supports, menu registration, settings, kit integration, title handling, content width, theme location registration, theme location display wrappers, and theme-owned Elementor compatibility.

## Hello Elementor Child Theme

- Site-specific filter overrides, style overrides, asset loading, and light custom behavior that should not modify the parent package and should not become reusable addon code.

## Outside Elementor

- Generic WordPress plugin logic, generic theme rendering, and WordPress Core behavior remain outside this skill family.