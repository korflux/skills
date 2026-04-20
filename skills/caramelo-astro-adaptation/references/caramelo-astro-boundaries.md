# Caramelo Astro Boundaries

Use this reference when deciding whether a task belongs in the Astro source project, the Caramelo theme runtime, or generic Astro and WordPress surfaces.

## Caramelo Astro Adaptation Owns

- External Astro source projects that must publish into Caramelo.
- Static build compatibility, entry naming, asset strategy, manifest generation, and release packaging.
- Team workflow that turns a built Astro site into a Caramelo release artifact.

## Route To Caramelo Theme Development When

- The change belongs inside `caramelotheme-main`.
- The owner is the WordPress-side runtime, importer, admin UI, router, metabox, release settings, or fallback behavior.
- You need to change the Caramelo contract itself rather than adapt Astro to the current contract.

## Route To Generic Astro Work When

- The task is only about Astro components, layouts, integrations, or content collections with no Caramelo publishing requirement.

## Route To Generic WordPress Skills When

- The task is generic WordPress theme or plugin work unrelated to Caramelo.
- The task is WordPress Core behavior.