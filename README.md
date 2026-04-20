# skills

WordPress, Elementor, and Caramelo-focused agent skills for the open agent skills ecosystem.

This repository publishes ten separate skills with intentionally different discovery surfaces so agents can route requests more accurately between WordPress Core, WordPress themes, WordPress plugins, Elementor Free, Elementor Pro, Hello Elementor theme work, Hello Elementor child theme work, Caramelo theme runtime work inside WordPress, Caramelo-targeted Astro adaptation work, and broad Elementor routing.

## Available Skills

- `wordpress-core-development`: for WordPress Core internals, `wordpress-develop`, `wp-admin`, `wp-includes`, Trac, Core tests, and contributor workflow.
- `wordpress-theme-development`: for block themes, classic themes, child themes, `theme.json`, templates, template hierarchy, global styles, and theme accessibility.
- `wordpress-plugin-development`: for plugin architecture, activation and uninstall flows, Settings API, REST routes, admin pages, WP-CLI, cron jobs, and reusable WordPress features.
- `elementor-development`: for broad or ambiguous Elementor requests that still need routing across Elementor Free, Elementor Pro, Hello Elementor parent theme, and Hello Elementor child theme surfaces.
- `elementor-free-development`: for reusable Elementor Free addon or plugin code such as widgets, controls, editor extensions, Finder, context menu, managers, and assets.
- `elementor-pro-development`: for reusable Elementor Pro addon or plugin code such as dynamic tags, form actions, form fields, forms hooks, and Theme Builder conditions.
- `hello-elementor-theme-development`: for the Hello Elementor parent theme package itself, including `hello-theme-main`, parent hooks, Elementor integration files, settings, and theme-owned behavior.
- `hello-elementor-child-development`: for site-specific customization in a Hello Elementor child theme, including `functions.php`, `style.css`, asset loading, and filter-based overrides.
- `caramelo-theme-development`: for Caramelo Theme Child runtime work inside WordPress, including render mode, Astro entry mapping, release resolution, router behavior, import flows, admin screens, and project customizations that depend on Caramelo being loaded.
- `caramelo-astro-adaptation`: for adapting an Astro source project or build artifact so it can be published through Caramelo Theme Child with the expected `manifest.json`, entry mapping, asset strategy, and release packaging.

## Install

List available skills:

```bash
npx skills add korflux/skills --list
```

Install one skill globally:

- WordPress Core:

```bash
npx skills add korflux/skills --skill wordpress-core-development -g -y
```

- WordPress Theme:

```bash
npx skills add korflux/skills --skill wordpress-theme-development -g -y
```

- WordPress Plugin:

```bash
npx skills add korflux/skills --skill wordpress-plugin-development -g -y
```

- Elementor Router:

```bash
npx skills add korflux/skills --skill elementor-development -g -y
```

- Elementor Free:

```bash
npx skills add korflux/skills --skill elementor-free-development -g -y
```

- Elementor Pro:

```bash
npx skills add korflux/skills --skill elementor-pro-development -g -y
```

- Hello Elementor Theme:

```bash
npx skills add korflux/skills --skill hello-elementor-theme-development -g -y
```

- Hello Elementor Child Theme:

```bash
npx skills add korflux/skills --skill hello-elementor-child-development -g -y
```

- Caramelo Theme:

```bash
npx skills add korflux/skills --skill caramelo-theme-development -g -y
```

- Caramelo Astro Adaptation:

```bash
npx skills add korflux/skills --skill caramelo-astro-adaptation -g -y
```

Install all skills:

```bash
npx skills add korflux/skills --skill '*' -g -y
```

## Repository Layout

```text
skills/
  elementor-development/
  elementor-free-development/
  elementor-pro-development/
  hello-elementor-theme-development/
  hello-elementor-child-development/
  caramelo-theme-development/
  caramelo-astro-adaptation/
  wordpress-core-development/
  wordpress-theme-development/
  wordpress-plugin-development/
```

Each skill contains its own `SKILL.md` plus focused reference files for workflow, routing, validation, and boundaries.

## Routing Guide

- Start with `elementor-development` when the request mentions Elementor broadly, mixes multiple Elementor surfaces, or the package owner is still unclear.
- Use `elementor-free-development` when the owner is reusable addon or plugin code and the surface is widgets, controls, editor extensions, Finder, context menu, or assets.
- Use `elementor-pro-development` when the owner is reusable addon or plugin code and the surface is dynamic tags, forms, or Theme Builder conditions.
- Use `hello-elementor-theme-development` when the change must land in `hello-theme-main` and become parent-theme behavior for all users of the package.
- Use `hello-elementor-child-development` when the change is site-specific and should live in child theme `functions.php`, `style.css`, or child-only assets.
- Use `caramelo-theme-development` when the owner is `caramelotheme-main`, the WordPress-side Caramelo runtime, a Caramelo admin screen, release state, import flow, router behavior, or the project customization layer initialized from `caramelo_theme_child_loaded`.
- Use `caramelo-astro-adaptation` when the owner is the Astro source project or built release artifact that must satisfy Caramelo's static release contract.
- If the existing Caramelo contract is correct and the Astro build needs to adapt to it, use `caramelo-astro-adaptation`. If the importer, router, metabox, admin UI, or shipped contract inside `caramelotheme-main` needs to change, use `caramelo-theme-development`.
- Theme location registration or display inside Hello theme files belongs to the Hello parent or child theme skills, not to `elementor-pro-development`.
- Fall back to the WordPress plugin, theme, or Core skills when the task is not actually owned by Elementor or Hello Elementor.

## Example Prompts

- `wordpress-core-development`: EN: `Investigate a regression in wp-admin after a core update.` PT: `Corrija uma regressao no Core do WordPress em wp-admin ou wp-includes.`
- `wordpress-theme-development`: EN: `Update template hierarchy and theme.json in a WordPress theme.` PT: `Ajuste templates e theme.json em um tema WordPress.`
- `wordpress-plugin-development`: EN: `Add a settings page and a REST endpoint to a plugin.` PT: `Crie uma tela de configuracao e uma rota REST em um plugin WordPress.`
- `elementor-development`: EN: `I need help with Elementor and I do not know if this belongs in Free, Pro, or the Hello child theme.` PT: `Preciso mexer no Elementor e nao sei se isso fica no Free, no Pro, no tema pai ou no child theme.`
- `elementor-free-development`: EN: `Build a custom Elementor widget with editor controls and frontend assets.` PT: `Crie um widget customizado do Elementor com controles no editor e assets no frontend.`
- `elementor-pro-development`: EN: `Register a dynamic tag and a custom form action in Elementor Pro.` PT: `Adicione uma tag dinamica e uma acao depois do envio do formulario no Elementor Pro.`
- `hello-elementor-theme-development`: EN: `Change how Hello Elementor parent theme handles page titles and theme integration.` PT: `Ajuste o tema pai Hello Elementor, incluindo page title e integracao com o Elementor.`
- `hello-elementor-child-development`: EN: `Override a Hello parent hook and enqueue site-specific CSS in the child theme.` PT: `No child theme do Hello, sobrescreva um hook do tema pai e carregue CSS especifico do site.`
- `caramelo-theme-development`: EN: `Add code to Caramelo functions.php, adjust the Caramelo Rendering metabox, or fix Astro routing and release behavior inside WordPress.` PT: `No Caramelo, adicione codigo ao functions.php, ajuste o metabox Caramelo Rendering, ou corrija o roteamento Astro e a validacao de release dentro do WordPress.`
- `caramelo-astro-adaptation`: EN: `Adapt this Astro site for Caramelo Theme Child by generating manifest.json, fixing _astro asset paths, and packaging a release ZIP for import.` PT: `Adapte este projeto Astro para o Caramelo gerando o manifest.json, corrigindo os assets _astro e empacotando um ZIP de release para importacao.`

## Goals

- Keep WordPress Core, theme, and plugin work separate.
- Keep Elementor routing separate from Elementor implementation surfaces.
- Keep Elementor Free, Elementor Pro, Hello Elementor parent theme, and Hello Elementor child theme work separate.
- Keep Caramelo WordPress runtime work separate from Astro release adaptation work.
- Improve auto-discovery by using stronger, domain-specific triggers.
- Reduce ambiguous routing between presentation, reusable functionality, and WordPress internals.

By Marco Kormoczi
