# Elementor Pro Workflow

Use this reference when creating or modifying an Elementor Pro extension point.

## Default Flow

1. Confirm reusable addon ownership.
   - The change should live in addon or plugin code rather than in Hello theme files.
   - If the task is really theme-side location registration or display in Hello code, route out before editing.

2. Guard the dependency first.
   - Check that Elementor Pro is active before loading Pro-specific integrations.

3. Register the Pro surface from one place.
   - Wire dynamic tags, form actions, form fields, forms hooks, or conditions through explicit registration callbacks.

4. Implement the owning class.
   - Keep controls, data access, rendering, validation, and lifecycle behavior in the class that owns the surface.

5. Validate the runtime path.
   - Dynamic tags: render in the consuming control path.
   - Form actions and fields: validate editor configuration and submission behavior.
   - Conditions: validate inclusion or exclusion behavior on the affected pages.

6. Check the fallback path.
   - Verify that missing Pro does not fatal the addon.

## Red Flags

- Loading Pro code unconditionally.
- Editing Hello theme files for a reusable Pro integration.
- Putting reusable Pro integrations into a child theme.
- Mixing theme location registration inside addon condition logic.