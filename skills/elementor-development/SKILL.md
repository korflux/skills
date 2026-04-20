name: elementor-development
description: 'Use when a request mentions Elementor or Hello Elementor broadly and the owning surface is still unclear. Routes ambiguous requests to elementor-free-development, elementor-pro-development, hello-elementor-theme-development, or hello-elementor-child-development. Triggers: Elementor broadly, Hello Elementor broadly, not sure if this is Free or Pro, not sure if this belongs in an addon or child theme, Elementor em geral, Hello Elementor em geral, nao sei se isso vai no Free ou Pro, nao sei se isso vai no plugin, tema pai ou child theme. Do not use when the request already clearly belongs to a specialized Elementor skill.'
argument-hint: 'What Elementor or Hello Elementor request needs routing, and where do you think the code lives today?'
---

# Elementor Development Routing

Use this skill when the task is clearly Elementor-related but the correct implementation surface is not yet clear.

This skill is for classification and routing across the Elementor ecosystem. It decides whether the request belongs to Elementor Free addon development, Elementor Pro extension work, Hello Elementor parent theme development, or Hello Elementor child theme customization. It is not the best skill once the target surface is already explicit.

## What This Skill Produces

- A precise route to the right specialized Elementor skill.
- A clear statement of the owning dependency: Free, Pro, Hello parent theme, or Hello child theme.
- The first class, hook, file, or package boundary to inspect.
- Clear escalation when the task actually belongs to generic WordPress plugin, theme, or Core work.

## When To Use

- The request says only `Elementor` and the exact surface is unclear.
- The request mixes widgets, forms, theme builder, Hello Theme, or child theme concerns.
- The request names a concrete feature, but the owning package is still unclear.
- You need to decide whether a feature should live in an addon plugin, Elementor Pro extension, Hello Elementor parent theme, or child theme.
- You need a first-pass routing decision before editing code.

## Discovery Phrases

### English

- help with Elementor but I am not sure where it belongs
- fix this Elementor integration
- I need a new Elementor feature and I do not know if it is Free or Pro
- should this live in an addon, the Hello parent theme, or the child theme
- route this Elementor request to the right skill

### Portuguese

- preciso de ajuda com Elementor, mas nao sei se isso fica no Free, no Pro, no tema pai ou no child theme
- resolva uma integracao com Elementor sem eu saber onde o codigo deve ficar
- preciso de uma feature no Elementor e nao sei se isso entra no plugin ou no tema
- isso deve ficar no plugin do Elementor, no tema pai Hello ou no child theme
- roteie este pedido de Elementor para a skill certa

## Do Not Use

- The request is already clearly about Elementor Free addon work.
- The request is already clearly about Elementor Pro forms, dynamic tags, or theme conditions.
- The request is already clearly about theme location registration or display inside Hello theme code.
- The request is already clearly about Hello Elementor parent theme development.
- The request is already clearly about Hello Elementor child theme customization.

## Load These References As Needed

- For routing workflow, load [elementor workflow](./references/elementor-workflow.md).
- For choosing the right specialized skill, load [elementor routing](./references/elementor-routing.md).
- For confirming the route, load [validation](./references/validation.md).
- For deciding between Elementor surfaces and WordPress surfaces, load [elementor boundaries](./references/elementor-boundaries.md).

## Procedure

1. Classify the dependency first.
   - If the feature depends on Elementor Free addon APIs such as widgets, controls, editor panels, Finder, context menu, or base assets, route to `elementor-free-development`.
   - If the feature depends on Elementor Pro surfaces such as dynamic tags, form actions, form fields, form hooks, or Theme Builder conditions, route to `elementor-pro-development`.
   - If the feature is about theme location registration or display inside Hello theme code, route to the Hello parent or child theme skill instead of the Pro skill.
   - If the task edits the Hello Elementor parent theme itself, route to `hello-elementor-theme-development`.
   - If the task is a site-specific override in a Hello Elementor child theme, route to `hello-elementor-child-development`.

2. Identify the owning codebase.
   - Prefer the package that should continue to own the behavior after the current change.
   - If multiple surfaces are involved, choose the primary owner and note the secondary dependency.

3. Name the first anchor.
   - Prefer a named hook, class, module, theme file, or user-visible failure path.
   - Route to the skill that most directly owns that anchor.

4. Reject false positives.
   - If the task is generic plugin logic with no Elementor API dependency, prefer `wordpress-plugin-development`.
   - If the task is generic theme rendering with no Elementor or Hello Elementor API dependency, prefer `wordpress-theme-development`.
   - If the task changes WordPress platform internals, prefer `wordpress-core-development`.

## Decision Points

### Which Specialized Skill Owns The Task?

- `elementor-free-development`: addon bootstrap, widgets, controls, editor extensions, Finder, context menu, managers, and scripts or styles.
- `elementor-pro-development`: dynamic tags, form actions, form fields, forms hooks, and Pro-only Theme Builder extension points.
- `hello-elementor-theme-development`: parent theme hooks, includes, settings, kit integration, and Hello-owned theme behavior.
- `hello-elementor-child-development`: child theme `functions.php`, `style.css`, asset loading, light overrides, and site-specific Hello customizations.

### When Is Routing Complete?

- The owning dependency is named.
- The specialized skill is explicit.
- The first hook, class, or file to inspect is identified.
- Any fallback to WordPress plugin, theme, or Core skills is explicit.