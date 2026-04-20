name: hello-elementor-child-development
description: 'Use when building, fixing, customizing, testing, or reviewing a Hello Elementor child theme. Triggers: Hello Elementor child, child theme, tema filho Hello Elementor, hello-theme-child-master, child theme functions.php, functions.php do tema filho, child theme style.css, style.css do tema filho, enqueue child assets, enfileirar assets do child, override Hello hook in child theme, site-specific Hello customization. Do not use for parent theme development or reusable addon plugin work such as widgets, controls, dynamic tags, form actions, or form fields.'
argument-hint: 'What Hello Elementor child theme customization, override, or site-specific tweak do you need help with?'
---

# Hello Elementor Child Development

Use this skill for Hello Elementor child theme customization.

This skill is for building, fixing, reviewing, and maintaining a Hello Elementor child theme. It focuses on site-specific overrides, child theme asset loading, small hook-based customizations, and light behavior changes that should not modify the parent theme package.

## What This Skill Produces

- Minimal, maintainable child theme changes.
- Clear routing between `functions.php`, `style.css`, extra assets, and hook-based overrides.
- A targeted validation plan for child theme behavior and parent-theme compatibility.
- Clear boundaries between child theme customization, parent theme development, and reusable addon plugin work.

## When To Use

- Editing `hello-theme-child-master`.
- The change is specific to one site, one install, or one deployment.
- Adding or fixing child theme asset loading.
- Overriding Hello parent theme filters or behavior in a site-specific way.
- Adding small child-theme logic that should remain local to one site or deployment.

## Discovery Phrases

### English

- customize Hello Elementor child theme
- add code to child theme functions.php
- enqueue styles in Hello child theme
- override Hello Elementor behavior in child theme
- update Hello child theme CSS

### Portuguese

- personalize o child theme do Hello Elementor
- adicione codigo ao functions.php do child theme do Hello
- carregue estilos no child theme do Hello Elementor
- sobrescreva um comportamento do Hello Elementor no child theme
- ajuste o CSS do tema filho Hello Elementor

## Do Not Use

- Parent theme development or fixes that belong in `hello-theme-main`.
- Reusable addon plugin behavior that should survive theme changes.
- New widgets, controls, dynamic tags, form actions, form fields, or other reusable addon features.
- Generic WordPress Core work.

## Load These References As Needed

- For child theme implementation flow, load [workflow](./references/hello-child-workflow.md).
- For choosing the correct child theme file, load [routing](./references/hello-child-routing.md).
- For focused checks, load [validation](./references/validation.md).
- For ownership boundaries, load [boundaries](./references/hello-child-boundaries.md).

## Procedure

1. Confirm the task belongs to the child theme.
   - If the task is site-specific and can be solved through child theme assets, filters, or small overrides, continue here.
   - If the task should change the parent package for everyone, prefer the parent theme skill.
   - If the task is reusable Elementor addon behavior, prefer the relevant Elementor addon skill.
   - If the task should survive a theme switch, it probably does not belong here.

2. Identify the owning child theme surface.
   - Determine whether the change lives in `functions.php`, `style.css`, or a small asset or include added by the child theme.

3. Start from the most concrete anchor.
   - Prefer the specific filter, hook, CSS target, or child-theme behavior regression.

4. Preserve child theme constraints.
   - Prefer additive overrides over copying parent theme logic.
   - Keep the customization small and local.
   - Respect parent theme handles and hooks when enqueueing assets.
   - Do not turn the child theme into a reusable addon package.

5. Validate narrowly.
   - Verify the child-theme behavior works.
   - Verify the parent theme still loads correctly.
   - Verify asset dependencies still load in the intended order.

## Decision Points

### What Kind Of Child Theme Surface Is This?

- `functions.php` hooks and filters.
- `style.css` and additive styling.
- Child-theme asset loading.

### When Is The Change Complete?

- The change remains child-theme scoped.
- The parent theme still behaves correctly.
- The affected site-specific behavior was checked.