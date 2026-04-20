# Elementor Ecosystem Workflow

Use this reference when routing a broad Elementor request to the correct specialized skill.

## Default Flow

1. Name the owner before the feature type.
   - Reusable addon or plugin behavior usually belongs in Elementor Free or Elementor Pro.
   - Package-wide Hello behavior belongs in the Hello Elementor parent theme.
   - Site-specific overrides belong in the Hello Elementor child theme.

2. Check the dependency boundary.
   - If the request depends on widgets, controls, editor extensions, Finder, context menu, managers, or assets with no Pro-only dependency, prefer Elementor Free.
   - If it depends on dynamic tags, form actions, form fields, forms hooks, or Theme Builder conditions, prefer Elementor Pro.
   - If it is about theme location registration or display inside Hello theme code, prefer the Hello parent or child theme skill instead of the Pro skill.

3. Choose one primary owner.
   - If multiple surfaces are involved, pick the package that should keep owning the change after implementation.
   - Note secondary dependencies, but do not split ownership prematurely.

4. Name the first concrete anchor.
   - Prefer a hook, manager, widget class, form class, parent theme file, child theme file, or visible regression.

5. Hand off to the specialized skill.
   - Route with the chosen owner, the anchor, and the main dependency assumptions.

## Red Flags

- Treating any Elementor request as an addon plugin task by default.
- Routing theme location registration or display inside Hello theme files to the Pro skill.
- Putting site-specific behavior into the Hello parent theme.
- Putting reusable addon logic into a child theme.
- Using Pro-only extension points without checking whether Pro is required.