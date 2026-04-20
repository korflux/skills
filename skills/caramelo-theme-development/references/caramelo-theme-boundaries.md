# Caramelo Theme Boundaries

Use this reference when deciding whether a task belongs in Caramelo core, the project customization layer, the Astro source project, or generic WordPress work.

## Caramelo Core Owns

- Reusable theme runtime behavior shipped with the Caramelo package.
- Admin screens, release settings, release validation, routing, import lifecycle, HTML preparation, and fallback behavior.
- Shipped docs, examples, and helper scripts that define or support the Caramelo contract.

## Project Customization Layer Owns

- Site-specific integrations that should not live in Caramelo core.
- MU-plugin code in `wp-content/mu-plugins/caramelo-site-customizations.php`.
- Optional local fallback code in `caramelo-site-custom.php` when the deployment flow accepts that tradeoff.

## Route To Caramelo Astro Adaptation When

- The owner is an external Astro source project or build pipeline.
- The task is to make an Astro build compatible with Caramelo's manifest, asset, and release contract.
- The work mainly lives outside the WordPress theme runtime.

## Route To Generic WordPress Skills When

- The task is generic theme work unrelated to Caramelo.
- The task is reusable plugin logic that should survive theme changes.
- The task is WordPress Core behavior.