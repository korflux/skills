# Caramelo Theme Workflow

Use this reference when modifying the Caramelo child theme runtime inside WordPress.

## Default Flow

1. Decide core versus project customization first.
   - Prefer Caramelo core only for reusable theme runtime.
   - Prefer a MU-plugin for site-specific code.
   - Use `caramelo-site-custom.php` only as a local fallback.

2. Choose the owning runtime surface.
   - `inc/caramelo-settings.php` for global settings, releases, and admin state.
   - `inc/caramelo-page-meta.php` for render mode, Astro entry, release override, and supported post type UI.
   - `inc/caramelo-router.php` for `template_include` interception rules.
   - `templates/astro-page.php` for document output and fallback template loading.
   - `inc/caramelo-import.php` for ZIP import, staging, page creation, conflicts, and release lifecycle.
   - `inc/caramelo-astro.php` for manifest resolution, HTML preparation, and asset rewriting.

3. Preserve the runtime contract.
   - WordPress remains canonical for URL, status, SEO, permissions, and editorial governance.
   - Astro mode only takes over configured singular content inside the supported post type allowlist.
   - On resolution failure, fall back to the normal WordPress template.

4. Keep project hooks stable.
   - Initialize project-specific integrations from `caramelo_theme_child_loaded`.
   - Do not turn `functions.php` or `inc/caramelo-*.php` into a catch-all for client snippets.

5. Validate the affected flow.
   - Check both the normal WordPress path and the Astro path when the change can affect both.
   - If admin screens changed, verify the specific screen and action only.
   - If import behavior changed, verify the impacted release state and imported item behavior only.

## Red Flags

- Putting client-specific snippets directly into `functions.php`.
- Editing Caramelo core when a MU-plugin is enough.
- Breaking WordPress fallback when Astro resolution fails.
- Treating the Astro source project as if it lived inside the theme runtime.