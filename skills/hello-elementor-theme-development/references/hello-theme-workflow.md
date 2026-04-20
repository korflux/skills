# Hello Elementor Theme Workflow

Use this reference when modifying the Hello Elementor parent theme.

## Default Flow

1. Start with the parent theme anchor.
   - Prefer the named Hello hook, integration include, or specific parent theme file.

2. Confirm parent package ownership.
   - The change should ship as parent theme behavior for all users of the package.
   - Avoid site-specific customizations that belong in a child theme.
   - Avoid reusable addon features that belong in Elementor addon code.

3. Respect Elementor integration boundaries.
   - Guard Elementor-dependent behavior.
   - Use documented Hello hooks and includes before inventing new layers.

4. Keep the change parent-safe.
   - Preserve generic behavior that should work across many sites.
   - Preserve backward compatibility where practical.

5. Validate on the affected theme surface.
   - Check the theme behavior, then the Elementor interaction if relevant.

## Red Flags

- Putting site-specific logic into the parent theme.
- Copying reusable addon behavior into theme files.
- Adding new widgets, controls, dynamic tags, form actions, or other addon features to the theme.
- Changing parent theme behavior when a child theme filter override would be enough.