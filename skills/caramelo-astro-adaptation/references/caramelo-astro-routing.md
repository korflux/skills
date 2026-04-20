# Caramelo Astro Routing

Use this reference to choose the correct adaptation surface in an Astro project or release artifact.

## Route To Astro Pages And Routes When

- The public URL map, `src/pages`, trailing slash behavior, or nested page output is wrong.
- The generated HTML files do not line up with the WordPress page model.

## Route To Asset Strategy When

- The build produces asset URLs that Caramelo cannot rewrite safely.
- The project relies on unsupported root-absolute public assets instead of build assets in `/_astro/`.

## Route To Manifest Generation When

- The release is missing `manifest.json`.
- Entry keys, relative HTML paths, or release metadata are wrong.
- You need to use or adapt `scripts/dist-to-manifest-builder.mjs` to emit the contract Caramelo expects.

## Route To Release Packaging When

- The dist output is correct but the folder or ZIP does not match Caramelo's import or FTP or SFTP publishing flow.
- The release contains unsupported files, missing HTML files, or broken relative paths.

## Route To WordPress Mapping Decisions When

- You need to decide how WordPress pages map to manifest entries.
- The front page should resolve `index`.
- Nested entries require explicit parent handling or placeholder page expectations.

## Route Outside This Skill When

- The change is inside `caramelotheme-main` and concerns the Caramelo importer, router, admin screens, or theme runtime. Use `caramelo-theme-development`.
- The task is generic Astro work not targeting Caramelo publishing.