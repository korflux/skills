# Caramelo Astro Validation

Use this reference when validating an Astro project or release artifact for Caramelo.

## Minimum Checks

1. Validate the build itself.
   - Run the narrowest available Astro validation such as `astro check` or `astro build`.
   - Confirm the build succeeds without SSR-only assumptions for the targeted pages.

2. Validate the release artifact.
   - The output should include `manifest.json`, one HTML file per target entry, and the `_astro/` asset directory.
   - Manifest values should be relative HTML paths inside the release.

3. Validate entry mapping.
   - `index` should map to `index.html`.
   - Nested entries should use slash-separated keys.
   - No duplicate normalized entries should exist.

4. Validate asset behavior.
   - Asset URLs should be compatible with Caramelo's `asset_prefixes`.
   - Avoid shipping a `<base>` tag in the HTML.
   - Confirm that unsupported root-absolute public asset paths are not required at runtime.

5. Validate packaging and publishability.
   - ZIP or release folders should exclude server-executable or server-configuration files.
   - Relative paths inside the release should remain intact after packaging.

6. Validate one WordPress mapping path when possible.
   - After import or upload, confirm at least one target WordPress page resolves the intended manifest entry and rendered HTML.

## Escalate Only If Needed

- Add broader content or SEO checks only when the task also changed markup, metadata, or multiple route groups.