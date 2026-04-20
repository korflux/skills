# Elementor Pro Routing

Use this reference to choose the correct Elementor Pro file or subsystem before editing.

## By Concern

- Dynamic tag groups, categories, controls, data methods, and rendering: dynamic tag class and its registration path.
- Form action controls, run logic, and export behavior: form action class and its registration path.
- Form field controls, render flow, validation, dependencies, and content template: form field class and its registration path.
- Forms lifecycle hooks: the specific forms hook callback for validation, processing, submission, or mail filters.
- Theme Builder conditions: condition class, group definition, and condition registration path.

## Route Out Immediately When

- The request requires editing `hello-theme-main` or `hello-theme-child-master`.
- The task is really theme-side location registration or display inside Hello theme code.
- The task is a site-specific override rather than reusable addon behavior.

## Heuristics

- If the bug happens during submission, start with the form action, field validation, or forms hook lifecycle.
- If the UI config looks right but output is wrong, start with render, data, or condition check methods.
- If the feature disappears when Pro is inactive, verify that the dependency guard is intentional and graceful.
- If the task names Hello theme files or theme-side wrappers, route to the Hello parent or child theme skill instead of staying here.