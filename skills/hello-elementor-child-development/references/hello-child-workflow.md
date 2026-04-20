# Hello Elementor Child Workflow

Use this reference when modifying a Hello Elementor child theme.

## Default Flow

1. Start with the smallest additive override.
   - Prefer a filter, action, or asset override before copying parent theme logic.

2. Keep the change site-scoped.
   - The change should be local to one site, one install, or one deployment.
   - If the behavior should travel across sites or survive theme switches, stop and reconsider addon ownership.

3. Respect parent theme loading.
   - Reuse parent handles and keep asset order explicit.

4. Validate the child path.
   - Check the override itself and verify the parent still loads correctly.

## Red Flags

- Copying large parent files into the child theme without a clear need.
- Putting reusable addon behavior into the child theme.
- Turning a local child-theme override into package-wide behavior.
- Changing the parent theme when a child override would be enough.