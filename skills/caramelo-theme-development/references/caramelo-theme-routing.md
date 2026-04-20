# Caramelo Theme Routing

Use this reference to choose the correct Caramelo WordPress-side surface.

## Route To Bootstrap And Custom Loading When

- The change concerns boot order, constants, child theme asset loading, optional local custom file loading, or the `caramelo_theme_child_loaded` action.
- Primary files: `functions.php`, `inc/caramelo-custom.php`.

## Route To Page Meta When

- The change concerns render mode, Astro entry, release override, supported post types, or the `Caramelo Rendering` metabox.
- Primary file: `inc/caramelo-page-meta.php`.

## Route To Router And Takeover Template When

- The change concerns `template_include`, preview rules, JSON, admin, embed, or password bypasses, fallback template handling, or final HTML output.
- Primary files: `inc/caramelo-router.php`, `templates/astro-page.php`.

## Route To Release Resolution When

- The change concerns release discovery, manifest parsing, entry resolution, HTML lookup, HTML preparation, `<base>` handling, or asset prefix rewriting.
- Primary file: `inc/caramelo-astro.php`.

## Route To Settings And Admin Screens When

- The change concerns global release settings, the `Caramelo` admin area, release validation state, or operational UI around releases.
- Primary file: `inc/caramelo-settings.php`.

## Route To Import And Imported Item Lifecycle When

- The change concerns ZIP preflight, staging, draft page creation, imported item history, conflict handling, activation, or release deletion behavior.
- Primary file: `inc/caramelo-import.php`.

## Route To Shipped Guidance When

- The change concerns the published Caramelo contract, team workflow docs, fixtures, or helper tooling that ships with the theme.
- Primary files: `docs/custom-code.md`, `docs/astro-release-contract.md`, `docs/ftp-sftp-publish.md`, `examples/`, `scripts/dist-to-manifest-builder.mjs`.

## Route Outside This Skill When

- The owner is the external Astro source project or release artifact that must adapt to the existing Caramelo contract. Use `caramelo-astro-adaptation`.
- The task is generic WordPress theme work unrelated to Caramelo. Use `wordpress-theme-development`.