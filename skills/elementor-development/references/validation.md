# Routing Validation

Use this reference to verify that the routing decision is correct before handing off.

## Minimum Checks

- Confirm whether the request depends on Elementor Free only, Elementor Pro, Hello parent theme code, or a child theme override.
- Confirm the first owning file, hook, or class is in the routed package.
- Confirm the request is not better served by the generic WordPress plugin, theme, or Core skills.

## Fast Heuristics

- If the request names forms, dynamic tags, or conditions, verify the Pro dependency before routing.
- If the request names `functions.php` or `style.css` in a child theme, verify the child theme route.
- If the request names Hello parent theme files or hooks, verify the parent theme route.
- If the request names widgets, controls, Finder, context menu, or editor extensions without Pro-only features, verify the Free route.

## Completion Signal

- The target specialized skill is explicit.
- The owning dependency is explicit.
- The first code anchor is explicit.