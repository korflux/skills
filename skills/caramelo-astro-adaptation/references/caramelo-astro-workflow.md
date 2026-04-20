# Caramelo Astro Workflow

Use this reference when adapting an Astro source project or release artifact for Caramelo.

## Default Flow

1. Start from the public URL map.
   - Identify which WordPress pages must be served by Astro.
   - Decide the exact manifest entries those pages will use.

2. Produce a static build only.
   - Caramelo V1 expects HTML files, `manifest.json`, and build assets.
   - Do not rely on SSR, a Node runtime, or source-project execution inside WordPress.

3. Keep entry mapping exact.
   - `index` maps to `index.html`.
   - Nested entries use slash-separated keys such as `campanha/verao`.
   - A nested entry does not implicitly create its parent entry.

4. Keep assets Caramelo-compatible.
   - Prefer imported build assets in `/_astro/`.
   - Avoid unsupported root-absolute public asset paths unless WordPress also serves them at that root.
   - Do not ship a `<base>` tag in the final HTML.

5. Generate the manifest after build.
   - Use `scripts/dist-to-manifest-builder.mjs` when it matches the project needs.
   - Reject duplicate normalized entries instead of guessing.

6. Package the release artifact.
   - Include `manifest.json`, HTML files, and `_astro/`.
   - Exclude server-executable files and server-configuration files from ZIP or release folders.

7. Map the release back to WordPress.
   - Prefer one WordPress page per public URL.
   - Leave the Astro entry blank when the WordPress slug already matches the manifest entry.
   - Use a manual entry only when the manifest key differs from the WordPress slug.

## Red Flags

- Shipping an Astro source checkout instead of a static release.
- Missing `manifest.json`.
- SSR-only behavior or runtime dependencies that WordPress uploads cannot execute.
- Duplicate entries that normalize to the same manifest key.
- Root-absolute public assets that WordPress will not serve from the same path.