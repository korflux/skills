# Validation

Use the smallest validation step that can falsify the change.

## Visual And Functional Checks

- Reload the affected front-end template and confirm the expected rendering.
- If the theme supports the Site Editor, verify the affected template or global style inside the editor as well.
- Re-check the affected responsive breakpoints after layout or CSS changes.
- Re-test keyboard navigation, focus visibility, landmark structure, alt text handling, and contrast when accessibility is relevant.

## Theme-Focused Code Checks

- Run project-defined lint or format commands when they exist.
- If the project uses PHP_CodeSniffer, prefer the project command or `phpcs --standard=WordPress`.
- If the project uses PHP_CodeSniffer auto-fixing, prefer the project command or `phpcbf --standard=WordPress` when safe.
- For narrow PHP changes, run `php -l <file>` when no better project command exists.
- For theme JavaScript, CSS, or build pipelines, use the project-defined build or lint commands rather than inventing new ones.

## Selection Rules

- Template or markup change: verify the owning template on the front end first.
- `theme.json` change: verify global styles, editor output, and the affected blocks.
- CSS change: verify the smallest affected set of breakpoints and pages.
- Theme setup change in `functions.php`: run the narrowest available standards or syntax validation and confirm the resulting behavior in WordPress.

## Completion Standard

- At least one relevant post-edit validation step was run.
- The chosen validation directly matched the changed theme surface.
- The affected front-end or editor output was checked.