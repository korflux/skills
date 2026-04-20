# Elementor Free Routing

Use this reference to choose the correct Elementor Free file or subsystem before editing.

## By Concern

- Addon bootstrap, compatibility checks, namespaces, constants, and initialization: main plugin file or main addon class.
- Widget registration, controls, rendering, dependencies, caching, and DOM behavior: widget class and its registration callback.
- Injected controls into existing elements: the targeting hook callback for the relevant element or section.
- Custom control types, templates, and control assets: control class and control registration path.
- Editor panels, tabs, menu entries, preview hooks, and settings: editor integration module.
- Finder categories or items: Finder integration module and its registration hook.
- Context menu groups or actions: context menu integration module for the relevant element type.
- Asset loading issues: the specific frontend, editor, preview, widget, or control asset registration path.

## Route Out Immediately When

- The request depends on dynamic tags, form actions, form fields, forms hooks, or Theme Builder conditions.
- The request requires editing `hello-theme-main` or `hello-theme-child-master`.
- The request is theme-owned, local to one site, or a Hello-specific override.

## Heuristics

- If the problem is editor-only, start with the editor integration or asset path.
- If the widget appears but renders incorrectly, start with the widget render methods, dependencies, or selectors.
- If the issue is registration, start with managers, hooks, and addon initialization.
- If the request mentions a Hello theme file, route to the Hello parent or child theme skill instead of staying here.