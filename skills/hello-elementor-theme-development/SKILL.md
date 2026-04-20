name: hello-elementor-theme-development
description: 'Use when building, fixing, customizing, testing, or reviewing the Hello Elementor parent theme itself. Triggers: Hello Elementor theme, tema Hello Elementor, hello_elementor_* hooks, hooks hello_elementor_, hello-theme-main, Hello parent theme, tema pai Hello, elementor-functions.php in Hello Theme, theme supports, menu registration, content width, largura do conteudo, page title, titulo da pagina, kit integration, parent theme compatibility. Do not use for site-specific child theme overrides or reusable addon plugin work such as widgets, controls, dynamic tags, or form actions.'
argument-hint: 'What Hello Elementor parent theme change, hook, integration, or theme-owned behavior do you need help with?'
---

# Hello Elementor Theme Development

Use this skill for the Hello Elementor parent theme codebase.

This skill is for building, fixing, reviewing, and maintaining the Hello Elementor parent theme itself. It focuses on theme-owned hooks, integration files, settings, assets, and compatibility behavior inside the parent theme package.

## What This Skill Produces

- Minimal, maintainable Hello Elementor parent theme changes.
- Clear routing between `functions.php`, includes, settings, Elementor integration files, and theme-owned hooks.
- A targeted validation plan for theme behavior, Elementor compatibility, and backward compatibility.
- Clear boundaries between parent theme development, child theme customization, and reusable addon plugin work.

## When To Use

- Editing `hello-theme-main` directly.
- The change should ship as parent theme behavior for all users of the package.
- Changing Hello Elementor filter hooks or theme supports.
- Changing Hello Elementor theme-owned Elementor integration such as kit tabs, title behavior, or theme compatibility.
- Reviewing theme settings, asset loading, menus, content width, or other parent theme behavior.

## Discovery Phrases

### English

- fix a Hello Elementor theme bug
- customize a Hello Elementor hook
- update hello_elementor_page_title behavior
- change Hello Elementor parent theme integration
- review hello-theme-main functions.php

### Portuguese

- corrija um bug no tema Hello Elementor
- personalize um hook do Hello Elementor
- ajuste o comportamento de hello_elementor_page_title
- altere a integracao do tema pai Hello Elementor
- revise o functions.php do hello-theme-main

## Do Not Use

- Site-specific customizations better handled in a child theme.
- Reusable addon plugin work that should survive theme switches.
- New widgets, controls, dynamic tags, form actions, or other reusable addon features.
- Generic WordPress Core work.

## Load These References As Needed

- For parent theme implementation flow, load [workflow](./references/hello-theme-workflow.md).
- For choosing the correct parent theme file, load [routing](./references/hello-theme-routing.md).
- For focused checks, load [validation](./references/validation.md).
- For ownership boundaries, load [boundaries](./references/hello-theme-boundaries.md).

## Procedure

1. Confirm the task belongs to the parent theme package.
   - If the task edits `hello-theme-main` or a Hello parent theme hook or include, continue here.
   - If it is site-specific and can live in a child theme, prefer the child theme skill.
   - If it is a reusable Elementor addon feature, prefer the relevant Elementor addon skill.

2. Identify the owning parent theme surface.
   - Determine whether the change lives in `functions.php`, an `includes/` integration file, a settings module, assets, or template parts.

3. Start from the most concrete anchor.
   - Prefer a named `hello_elementor_*` hook, a specific include, or a visible theme behavior regression.

4. Preserve parent theme constraints.
   - Keep the parent theme lean and generic.
   - Preserve backward compatibility where practical.
   - Guard Elementor-dependent code paths safely.
   - Do not absorb site-specific overrides that belong in the child theme.

5. Validate narrowly.
   - Verify the affected theme behavior.
   - Verify Elementor compatibility still works where relevant.
   - Run the smallest available syntax or standards check when available.

## Decision Points

### What Kind Of Hello Parent Theme Surface Is This?

- Core theme setup and hooks.
- Elementor integration includes.
- Settings and customizer behavior.
- Assets and template behavior.

If a child theme override is enough for one site, it probably does not belong here.

### When Is The Change Complete?

- The code lives in the correct parent theme surface.
- The change preserves parent theme ownership and compatibility.
- The affected theme behavior was checked.