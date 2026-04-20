# Validation

Use the smallest command that can falsify the change.

## PHP Validation

- Run the PHP test suite: `npm run test:php`
- Run a targeted PHPUnit filter: `npm run test:php -- --filter <test name>`
- Run a PHPUnit group: `npm run test:php -- --group <group name or ticket number>`
- Run PHPStan: `npm run typecheck:php`
- Run PHPCS: `npm run env:composer -- lint`
- Auto-fix PHPCS issues when appropriate: `npm run env:composer -- format`
- Run PHP compatibility checks: `npm run env:composer -- compat`

## JavaScript And Browser Validation

- Run JS type checks: `npm run typecheck:js`
- Run JSDoc linting: `npm run lint:jsdoc`
- Fix JSDoc lint issues: `npm run lint:jsdoc:fix`
- Run end-to-end tests: `npm run test:e2e`
- Run visual regression tests: `npm run test:visual`
- Run performance tests: `npm run test:performance`

## Build And Environment Validation

- Build development assets: `npm run build:dev`
- Watch and rebuild while editing: `npm run dev`
- Inspect environment logs: `npm run env:logs`

## Selection Rules

- PHP behavior change: start with the nearest PHPUnit coverage.
- Static-analysis-sensitive PHP change: include PHPStan.
- Admin UI or user flow change: use Playwright.
- JS-only typing or build change: use JS typecheck and the build workflow.
- Standards cleanup: use PHPCS and the formatter when appropriate.

## Completion Standard

- At least one relevant post-edit validation command was run.
- The chosen command directly matches the changed behavior or changed surface.
- Broader validation only follows after the narrowest useful check passes or proves insufficient.