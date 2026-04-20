# Component Routing

Use this reference to choose the owning surface before editing.

## Main Source Areas

- `src/`: bootstrap files, entrypoints, request handling, and top-level runtime surfaces.
- `src/wp-admin/`: classic admin screens, controllers, admin includes, and admin-facing assets.
- `src/wp-includes/`: shared runtime APIs, classes, REST internals, formatting, query behavior, login helpers, media internals, compatibility layers, and most reusable Core functionality.
- `src/js/`: shared JavaScript source used by Core tooling or runtime behavior.
- `src/wp-admin/js/` and `src/wp-includes/js/`: browser-side JavaScript tied to admin or Core runtime surfaces.

## Main Test Areas

- `tests/phpunit/tests/`: PHP behavior tests.
- `tests/e2e/`: end-to-end browser tests.
- `tests/visual-regression/`: visual regression coverage.
- `tests/performance/`: performance-focused browser tests.
- `tests/qunit/`: legacy browser-side JavaScript tests.
- `tests/phpstan/`: PHPStan bootstrap, stubs, and baseline.

## Routing Heuristics

- Login, bootstrap, multisite, upgrade, feeds, request entrypoints, or shared runtime behavior: start in `src/` or `src/wp-includes/`.
- Admin screen behavior, admin form handling, or admin controllers: start in `src/wp-admin/`.
- Shared APIs, query behavior, database logic, REST, capabilities, formatting, or compatibility work: start in `src/wp-includes/`.
- Browser flows and user journeys: start in `tests/e2e/` or `tests/visual-regression/`.
- Narrow PHP regressions: start in `tests/phpunit/tests/` near the touched component.

## Core Boundary Reminder

- If the task is mainly Block Editor feature work, check whether Gutenberg is the true owning repository.
- If the task is specific to a plugin or theme, do not use this skill.