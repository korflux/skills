name: elementor-pro-development
description: 'Use when building, fixing, customizing, testing, or reviewing reusable Elementor Pro extension points such as dynamic tags, form actions, form fields, forms hooks, and Theme Builder conditions. Triggers: Elementor Pro, dynamic tag, tag dinamica, form action, acao de formulario, form field, campo de formulario, form validation hook, hook de validacao de formulario, theme condition, condicao do Theme Builder, popup condition, condicao de popup. Do not use for generic Elementor Free widget and control work, theme location registration inside theme files, or Hello Elementor parent or child theme customization.'
argument-hint: 'What reusable Elementor Pro extension point or integration do you need help with?'
---

# Elementor Pro Development

Use this skill for Elementor Pro extension work.

This skill is for building, fixing, reviewing, and maintaining code that depends on Elementor Pro extension points such as dynamic tags, forms, and Theme Builder conditions. It assumes the implementation must guard Pro availability and degrade safely when Pro is absent.

## What This Skill Produces

- Minimal, maintainable Elementor Pro integrations.
- Clear routing between dynamic tags, form actions, form fields, forms hooks, and Theme Builder conditions.
- A targeted validation plan for editor setup, submission or rendering behavior, and Pro dependency checks.
- Clear boundaries between Pro-owned addon work and Hello Theme or child theme ownership.

## When To Use

- The reusable owner is addon or plugin code rather than Hello theme code.
- Building or fixing dynamic tags.
- Building or fixing custom form actions or form fields.
- Integrating with Elementor Pro forms hooks and submission lifecycle.
- Implementing or reviewing custom Theme Builder conditions.
- Guarding or validating Pro-specific behavior and fallbacks.

## Discovery Phrases

### English

- create a dynamic tag in Elementor Pro
- add a custom form action
- register a custom form field
- validate a custom Elementor form field
- add a theme condition in Elementor Pro
- hook into Elementor Pro forms

### Portuguese

- crie uma tag dinamica no Elementor Pro
- adicione uma acao customizada depois do envio do formulario
- adicione um campo customizado ao formulario do Elementor Pro
- crie a validacao de um campo customizado do formulario do Elementor Pro
- adicione uma condicao ao Theme Builder do Elementor Pro
- use os hooks do formulario do Elementor Pro

## Do Not Use

- Generic Elementor Free widgets, controls, Finder, context menu, or editor panel work.
- Theme location registration or display inside `hello-theme-main` or `hello-theme-child-master`.
- Hello Elementor parent theme development.
- Hello Elementor child theme customization.

## Load These References As Needed

- For Pro implementation flow, load [workflow](./references/elementor-pro-workflow.md).
- For choosing the correct Pro subsystem, load [routing](./references/elementor-pro-routing.md).
- For focused checks, load [validation](./references/validation.md).
- For ownership and dependency boundaries, load [boundaries](./references/elementor-pro-boundaries.md).

## Procedure

1. Confirm the task belongs to Elementor Pro.
   - If the task depends on dynamic tags, form actions, form fields, forms hooks, or Theme Builder conditions, continue here.
   - If the task is theme location registration or display inside Hello theme code, prefer the Hello skill that owns that theme code.

2. Identify the owning Pro surface.
   - Determine whether the change lives in a dynamic tag class, a form action or field class, a forms hook callback, or a condition class.

3. Start from the most concrete anchor.
   - Prefer a named hook, condition class, action class, field type, dynamic tag group, or failing form lifecycle step.

4. Preserve Pro constraints.
   - Guard Pro-only code paths.
   - Fail safely when Pro is absent.
   - Keep reusable Pro integrations in addon code rather than theme code.
   - Do not move theme-owned location logic into the Pro addon surface.

5. Validate narrowly.
   - Verify registration in the relevant editor surface.
   - Verify render, validation, or submission behavior.
   - Verify the no-Pro or dependency-missing path when relevant.

## Decision Points

### What Kind Of Elementor Pro Surface Is This?

- Dynamic tags.
- Form actions and form fields.
- Forms hooks and processing lifecycle.
- Theme Builder conditions.

### When Is The Change Complete?

- The code lives in the correct Pro-owned surface.
- The Pro dependency path and fallback path are explicit.
- The affected editor and runtime behavior was checked.