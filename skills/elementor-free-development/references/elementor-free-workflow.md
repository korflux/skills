# Elementor Free Workflow

Use this reference when creating or modifying an Elementor Free addon surface.

## Default Flow

1. Confirm reusable addon ownership.
   - The change should live in addon or plugin code and should survive a theme switch.
   - If the request really belongs in `hello-theme-main` or a Hello child theme, route out before editing.

2. Establish the addon entry point.
   - Start with the main plugin file, compatibility headers, namespaces, constants, and the main loader class.

3. Register Elementor Free surfaces from one place.
   - Wire widgets, controls, editor modules, Finder integrations, context menu integrations, and assets through explicit registration callbacks.

4. Implement the owning component.
   - Keep identity, controls, rendering, dependencies, selectors, and output in the component that owns the behavior.

5. Scope assets correctly.
   - Separate frontend, editor, preview, widget, and control assets.

6. Validate in the same surface the user will touch.
   - Check editor registration first, then preview or frontend behavior.

## Red Flags

- Loading editor assets globally.
- Editing Hello parent or child theme files for a reusable Elementor Free feature.
- Putting reusable addon logic into a Hello theme or child theme.
- Solving site-specific theme overrides in addon code.
- Using undocumented internals when a documented manager or hook exists.