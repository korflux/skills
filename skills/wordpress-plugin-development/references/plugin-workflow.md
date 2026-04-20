# Plugin Workflow

Use this reference for common WordPress plugin structure and day-to-day workflow.

## Typical Plugin Surfaces

- Main plugin file with plugin header and bootstrap logic.
- `includes/`, `src/`, or similar directories for reusable classes, services, hooks, and feature modules.
- `admin/` or admin-facing code for settings pages, notices, permissions, and form handling.
- `public/` or front-end integration code for shortcodes, widgets, blocks, rendering, and assets.
- `uninstall.php` or uninstall routines for cleanup behavior.
- Upgrade or migration logic for versioned schema or option changes.

## Typical Workflow

1. Identify the smallest owning plugin surface for the feature or bug.
2. Change the bootstrap, handler, service, or admin integration that directly controls behavior.
3. Verify the behavior in WordPress through the actual execution path: admin page, REST route, CLI command, AJAX action, shortcode, or front-end integration.
4. Run the narrowest project-defined tests, linting, or standards checks available.
5. Re-check security, capabilities, i18n, and upgrade safety when relevant.

## Working Rules

- Keep plugin logic portable across themes when appropriate.
- Prefer WordPress plugin APIs and hooks over custom infrastructure.
- Isolate activation, upgrade, and uninstall behavior so side effects are explicit.
- Keep data migrations and destructive cleanup routines deliberate and reversible where possible.