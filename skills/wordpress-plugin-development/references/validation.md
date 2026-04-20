# Validation

Use the smallest validation step that can falsify the change.

## Functional Checks

- Trigger the exact plugin execution path that changed: activation, admin form save, REST request, AJAX action, cron run, shortcode render, CLI command, or front-end integration.
- Re-test the relevant role or permission boundary after changes to admin, settings, or privileged actions.
- Re-check multisite or network activation behavior when the plugin supports it.

## Plugin-Focused Code Checks

- Run project-defined lint, format, or test commands when they exist.
- If the project uses PHP_CodeSniffer, prefer the project command or `phpcs --standard=WordPress`.
- If the project uses PHP_CodeSniffer auto-fixing, prefer the project command or `phpcbf --standard=WordPress` when safe.
- For narrow PHP changes, run `php -l <file>` when no better project command exists.
- For REST, AJAX, or JavaScript-heavy plugin work, use the project-defined build, test, or lint commands rather than inventing new ones.

## Selection Rules

- Lifecycle change: verify activation, deactivation, uninstall, or upgrade behavior directly.
- Admin page or form change: verify the screen, nonce handling, capability checks, validation, and persistence.
- REST or AJAX change: issue the request through the real endpoint and verify permission and response behavior.
- Data migration or schema change: verify the upgrade path and safe handling of existing installs.

## Completion Standard

- At least one relevant post-edit validation step was run.
- The chosen validation directly matched the changed plugin surface.
- Security, capability, and data-integrity concerns were checked where relevant.