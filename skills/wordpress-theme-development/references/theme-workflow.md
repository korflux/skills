# Theme Workflow

Use this reference for common WordPress theme structure and day-to-day workflow.

## Typical Theme Surfaces

- `style.css`: theme header metadata for classic themes and baseline styles.
- `functions.php`: theme setup, theme supports, asset loading, menus, widget areas, and theme hooks.
- PHP templates such as `index.php`, `single.php`, `page.php`, `archive.php`, `front-page.php`, `home.php`, `header.php`, and `footer.php`.
- `theme.json`: global styles, settings, spacing, typography, color system, and editor-facing configuration for block themes.
- `templates/` and `parts/`: block theme templates and template parts.
- `patterns/`: reusable block patterns packaged with the theme.
- `assets/`: theme scripts, styles, fonts, and images.

## Typical Workflow

1. Identify whether the task belongs to a block theme, classic theme, or child theme.
2. Change the smallest owning file for the affected template, part, style, or setup logic.
3. Reload the affected front-end view and, when relevant, the Site Editor or post editor.
4. Check responsive behavior, accessibility, and rendering regressions.
5. Run project-specific linting or standards checks when available.

## Working Rules

- Keep theme code focused on presentation and theme integration.
- Prefer WordPress theme APIs and conventions over custom infrastructure.
- Use `theme.json` and block theme primitives when working in block themes.
- Use the template hierarchy instead of duplicating logic across many templates.