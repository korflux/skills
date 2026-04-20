# Caramelo Theme Validation

Use this reference when validating a Caramelo WordPress-side change.

## Minimum Checks

1. Verify the unchanged WordPress path.
   - A page in normal WordPress or Elementor mode should keep the expected template flow.

2. Verify the affected Astro path.
   - The target content should resolve the expected release, entry, and HTML file.
   - If the release or entry is invalid, the request should fall back safely.

3. Verify access and routing guards when relevant.
   - Admin, JSON, embed, and password-protected requests should not be intercepted accidentally.
   - Preview behavior for non-public content should still follow WordPress capability rules.

4. Verify the owning admin or import surface when relevant.
   - Settings screens, release actions, imported item actions, and nonces or capabilities touched by the change should still behave as intended.

5. Verify project-specific bootstrapping when relevant.
   - If a MU-plugin or local custom file path is involved, confirm it initializes from `caramelo_theme_child_loaded` without breaking the parent or child theme setup.

## Escalate Only If Needed

- Add broader regression checks only when the touched surface crosses routing, import, and admin behavior together.