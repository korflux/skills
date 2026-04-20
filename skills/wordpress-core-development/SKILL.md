---
name: wordpress-core-development
description: 'Use when fixing, implementing, testing, or reviewing WordPress Core internals in the wordpress-develop codebase. Triggers: WordPress Core, core patch, core bug, core regression, Trac ticket, wp-admin, wp-includes, wp-login.php, wp-settings.php, bootstrap internals, multisite network internals, REST API internals, classic admin screens, PHPUnit, PHPCS, PHPStan, Playwright, QUnit, Gutenberg vs Core, backward compatibility, contributor workflow. Do not use for plugin or theme development.'
argument-hint: 'What WordPress Core change, bug, test, or workflow do you need help with?'
---

# WordPress Core Development

Use this skill for WordPress Core work only.

This skill is for changes in the `wordpress-develop` codebase and the workflows used by WordPress Core contributors. It is not for plugin development, theme development, or general site building.

## What This Skill Produces

- Minimal, contributor-ready WordPress Core changes.
- A tight, repo-aware workflow for locating the owning surface before editing.
- A targeted validation plan using the standard WordPress Core commands and test surfaces.
- Clear routing between WordPress Core and Gutenberg when the ownership boundary matters.

## When To Use

- Fixing a WordPress Core bug or regression in `wp-admin`, `wp-includes`, `src/js`, `wp-login.php`, or other bootstrap and runtime files.
- Implementing or reviewing a Core patch, Core ticket, or Trac-linked change.
- Investigating a failing WordPress Core test or adding the nearest PHPUnit, Playwright, or QUnit coverage.
- Checking backward compatibility, coding standards, validation, and contributor readiness for a Core change.
- Deciding whether a change belongs in WordPress Core or Gutenberg.
- Working with WordPress Core build, Docker environment, PHPUnit, PHPCS, PHPStan, Playwright, or contributor workflow tasks in `wordpress-develop`.

## Discovery Phrases

- fix a WordPress Core bug
- review this core patch
- investigate a core regression in wp-admin
- add a PHPUnit test for wp-includes
- debug a failing Playwright test in wordpress-develop
- is this change Core or Gutenberg
- prepare this Core change for Trac review

## Do Not Use

- Plugin architecture or plugin APIs as the main task.
- Theme templates, theme.json design work, or theme-specific behavior as the main task.
- General WordPress site support unrelated to Core development.

## Load These References As Needed

- For the standard Core repo workflow and daily commands, load [core workflow](./references/core-workflow.md).
- For deciding which source or test area owns the work, load [component routing](./references/component-routing.md).
- For validation commands and completion criteria, load [validation](./references/validation.md).
- For contributor expectations, Trac, and Gutenberg boundaries, load [contribution context](./references/contribution-context.md).

## Procedure

1. Confirm that the task belongs to WordPress Core.
   - If it is mainly Block Editor feature work, prefer Gutenberg.
   - If it touches Core bootstrap, runtime APIs, classic admin, multisite, login, media, upgrade flows, shared JavaScript, REST infrastructure, or Core test/tooling, continue here.

2. Start from the most concrete anchor.
   - Prefer a named file, symbol, failing command, failing test, or user-visible regression.
   - Read the nearest implementation and the nearest relevant test before exploring further.
   - Prefer the code that directly computes or mutates behavior over wiring or registration layers.

3. Route to the owning Core surface.
   - Use the component map to choose the correct `src/` or `tests/` area.
   - Work in source files, not generated output.
   - Reuse existing WordPress Core APIs, hooks, conventions, and data flows before introducing abstractions.

4. Preserve Core constraints.
   - Keep backward compatibility unless the task explicitly requires otherwise.
   - Match nearby style, naming, and architectural patterns.
   - For user input, output, and privileged actions, apply the normal Core expectations: sanitization, escaping, capabilities, nonces, SQL preparation, and internationalization where relevant.
   - Avoid changes that are better expressed as plugin or theme logic.

5. Add or update the nearest realistic test.
   - For PHP behavior, prefer the closest PHPUnit coverage.
   - For admin or user flows, prefer Playwright.
   - For browser-side legacy JavaScript, prefer QUnit where that surface already uses it.
   - For static-analysis-sensitive changes, include the relevant type or lint validation.

6. Validate narrowly first.
   - Run the smallest command that can disprove the change quickly.
   - If it fails, repair the same slice before broadening scope.
   - Escalate to broader validation only when the touched surface warrants it.

7. Finish with contributor-ready hygiene.
   - Update inline documentation when public behavior, hooks, or parameters change.
   - If the patch is meant for upstream contribution, ensure there is a matching Trac ticket and that the full Trac URL can be included in the PR body.
   - Summarize the behavior change, the validation run, and any remaining risks.

## Decision Points

### Core Or Gutenberg?

- Block Editor product work: likely Gutenberg first.
- Core runtime, classic admin, multisite, login, bootstrap, upgrade, shared APIs, or Core infrastructure: WordPress Core.

### Which Validation Surface?

- PHP behavior and shared runtime logic: PHPUnit, PHPCS, and PHPStan as needed.
- JS typing or build changes: JS typecheck and build/watch.
- UI flows and browser behavior: Playwright.
- Existing legacy browser tests: QUnit when that component already uses it.

### When Is The Change Complete?

- The code lives in the correct owning Core surface.
- The implementation matches nearby WordPress Core patterns.
- The narrowest relevant validation has been run.
- Changed public behavior has matching tests or a clear explanation for why not.
- Contributor-facing requirements such as backward compatibility, documentation, and Trac readiness were checked.