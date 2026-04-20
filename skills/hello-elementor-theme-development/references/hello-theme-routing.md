# Hello Elementor Theme Routing

Use this reference to choose the correct parent theme file before editing.

## By Concern

- Theme setup, supports, menus, title behavior, content width, and top-level Hello hooks: `functions.php`.
- Elementor kit integration, theme settings inside Elementor, theme location registration, theme location display wrappers, and other theme-owned Elementor behavior: `includes/elementor-functions.php` and nearby includes.
- Settings and tweak registration: `includes/settings-functions.php` and related modules.
- Theme utilities and dependency checks: `includes/utils.php` and nearby helper files.
- Template behavior and output: template files and template parts.

## Heuristics

- If the request names a `hello_elementor_*` hook, start where that hook is defined or filtered.
- If the request is about Hello behavior inside Elementor, start in the Elementor integration include.
- If the request is about theme-side location registration or display inside Hello code, stay in the Hello theme skill.
- If the request is about site-specific override rather than package behavior, route to the child theme skill.
- If the request is about reusable widgets, controls, dynamic tags, form actions, or editor extensions, route to the relevant Elementor addon skill.