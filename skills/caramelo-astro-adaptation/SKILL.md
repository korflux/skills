---
name: caramelo-astro-adaptation
description: 'Use when adapting an Astro source project or build artifact so it can be published through Caramelo Theme Child. Triggers: Astro site to WordPress via Caramelo, adapt Astro project for Caramelo, generate manifest.json for Caramelo, Caramelo release contract, dist-to-manifest-builder, _astro assets, static export for Caramelo, release ZIP for Caramelo, map Astro pages to WordPress pages, build Astro for Caramelo, transformar site Astro para WordPress com Caramelo, adaptar projeto Astro para o Caramelo, gerar manifest.json para o Caramelo, contrato de release do Caramelo, export estatico para o Caramelo, ZIP de release para o Caramelo, mapear paginas Astro para paginas do WordPress, preparar build Astro para o Caramelo, corrigir assets _astro para o Caramelo, scripts/dist-to-manifest-builder.mjs. Do not use for WordPress-side runtime changes inside caramelotheme-main.'
argument-hint: 'What Astro project, build output, manifest, or release artifact needs to be adapted so Caramelo can publish it through WordPress?'
---

# Caramelo Astro Adaptation

Use this skill when working on the Astro source project or release artifact that will be published through Caramelo Theme Child.

This skill is for adapting an existing Astro site, or building a new Astro output, so it can enter WordPress through Caramelo's static release contract. It focuses on static export compatibility, manifest generation, page entry mapping, asset rules, ZIP or folder packaging, and publish-ready release output.

## What This Skill Produces

- Minimal, maintainable Caramelo-compatible Astro output.
- Clear mapping between public URLs, manifest entries, HTML files, and WordPress pages.
- A targeted validation plan for static build output and release packaging.
- Clear boundaries between Astro source-project changes and WordPress-side Caramelo runtime changes.

## When To Use

- An existing Astro site must be adapted to publish through Caramelo.
- The build needs a `manifest.json` that matches Caramelo's release contract.
- Route names, nested pages, trailing slash behavior, or front page output must line up with WordPress page mapping.
- Assets need to work with Caramelo's `asset_prefixes` and uploads-based release serving.
- The team needs a ZIP or release folder that Caramelo can import or publish via FTP or SFTP.
- You need to decide how WordPress pages should map to manifest entries like `index`, `evento`, or `campanha/verao`.

## Discovery Phrases

### English

- adapt this Astro site for Caramelo Theme Child
- generate a Caramelo manifest.json from an Astro build
- make this Astro export compatible with WordPress via Caramelo
- package an Astro release ZIP for Caramelo import
- map Astro pages to Caramelo WordPress entries
- fix Caramelo asset paths in an Astro build
- update scripts/dist-to-manifest-builder.mjs for Caramelo
- prepare a static Astro build for Caramelo publishing

### Portuguese

- adapte este site Astro para entrar no Caramelo Theme Child
- adapte este projeto Astro para o Caramelo
- gere um manifest.json do Caramelo a partir do build Astro
- torne este export estatico do Astro compativel com WordPress via Caramelo
- empacote um ZIP de release Astro para importacao no Caramelo
- mapeie paginas Astro para paginas do WordPress no Caramelo
- corrija os assets _astro ou os paths do build para o Caramelo
- ajuste o scripts/dist-to-manifest-builder.mjs para o Caramelo
- prepare um build estatico do Astro para publicacao via Caramelo

## Do Not Use

- WordPress-side changes to render mode, router, admin screens, importer behavior, or release state inside `caramelotheme-main`.
- Generic Astro work that is not targeting Caramelo publishing.
- Generic WordPress theme or plugin changes unrelated to Caramelo.

## Load These References As Needed

- For the default adaptation flow, load [workflow](./references/caramelo-astro-workflow.md).
- For choosing the right Astro-side surface, load [routing](./references/caramelo-astro-routing.md).
- For focused release checks, load [validation](./references/validation.md).
- For Astro-project versus theme-runtime boundaries, load [boundaries](./references/caramelo-astro-boundaries.md).

## Procedure

1. Confirm the owner is the Astro source project or release artifact.
   - If the change belongs inside `caramelotheme-main`, prefer `caramelo-theme-development`.
   - If the task is generic Astro work with no Caramelo publishing requirement, prefer the generic Astro skill.

2. Start from the public URL map.
   - Identify which WordPress pages must be served by Astro.
   - Name the manifest entries those pages should resolve, such as `index`, `evento`, or `campanha/verao`.

3. Enforce Caramelo's release contract.
   - Produce a static build only for V1.
   - Generate `manifest.json` before upload.
   - Keep entry keys exact and values relative to HTML files inside the release.
   - Do not rely on SSR, a Node runtime, or source-project execution inside WordPress.

4. Keep assets Caramelo-compatible.
   - Prefer imported build assets that end up in `/_astro/`.
   - Avoid unsupported root-absolute public asset URLs unless WordPress also serves them at that root.
   - Do not ship a `<base>` tag in the built HTML.

5. Package the release artifact.
   - Include `manifest.json`, HTML files, and `_astro/` assets.
   - Preserve relative paths.
   - Exclude server-executable and server-configuration files from the ZIP or folder.

6. Map the release back to WordPress.
   - Prefer one WordPress page per public URL.
   - Leave the Astro entry blank when the WordPress slug already matches the manifest entry.
   - Use `index` for the site front page when the build root maps to `index.html`.
   - Remember that nested entries do not implicitly create their parent entries.

7. Validate narrowly.
   - Run the narrowest available Astro build or check command.
   - Inspect the built release artifact.
   - When possible, verify one target page after upload or import through Caramelo.

## Decision Points

### What Kind Of Adaptation Problem Is This?

- Route structure and entry naming.
- Asset path compatibility.
- Manifest generation.
- Release packaging and publish flow.
- WordPress page mapping.

### Theme Contract Or Astro Adaptation?

- If the current Caramelo contract is correct and the Astro project must adapt to it, stay here.
- If the importer, router, admin flow, or shipped Caramelo contract inside the theme must change, use `caramelo-theme-development`.

### When Is The Change Complete?

- The built output matches Caramelo's release contract.
- Entry names, HTML files, and assets are internally consistent.
- The release is ready for import or upload.
- At least one real WordPress mapping path was considered.