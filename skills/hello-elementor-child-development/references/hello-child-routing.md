# Hello Elementor Child Routing

Use this reference to choose the correct child theme file before editing.

## By Concern

- Hook and filter overrides, small PHP customizations, and asset enqueueing: `functions.php`.
- Site-specific CSS overrides: `style.css`.
- Additional child assets: the child asset file plus its enqueue path in `functions.php`.

## Heuristics

- If the task is a parent hook override, start in child `functions.php`.
- If the task is purely styling, start in child `style.css`.
- If the task should become general parent theme behavior, route to the Hello parent theme skill.
- If the task needs reusable Elementor addon behavior, route out of the child theme skill.