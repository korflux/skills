# Theme Routing

Use this reference to choose the correct file before editing.

## By Theme Type

- Block theme: `theme.json`, `templates/`, `parts/`, `patterns/`, and theme assets.
- Classic theme: PHP templates, `functions.php`, `style.css`, template hierarchy files, and asset directories.
- Child theme: override only the files or styles that actually need customization, and prefer additive hooks and CSS when possible.

## By Concern

- Global visual system, color palette, spacing, typography, layout tokens, and editor styles: `theme.json`.
- Shared header, footer, sidebar, or repeated layout regions: template parts or classic partial templates.
- Archive, single, page, search, 404, and home rendering: the matching template in the hierarchy.
- Theme setup, menu registration, widget areas, image sizes, theme supports, and asset enqueuing: `functions.php`.
- Reusable design compositions for block themes: `patterns/`.
- Styling fixes: the nearest owning stylesheet or style system used by the theme.

## Routing Heuristics

- If the issue is about which template appears, start with the template hierarchy.
- If the issue is about global design tokens or editor styling, start with `theme.json`.
- If the issue is about repeated sections like headers or footers, start with the relevant template part.
- If the issue is about setup or registration, start with `functions.php`.
- If the issue is only present in a child theme, avoid changing the parent theme unless that is explicitly the target.