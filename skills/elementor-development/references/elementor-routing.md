# Elementor Ecosystem Routing

Use this reference to choose the correct specialized skill before editing.

## Route To Elementor Free When

- The owner is reusable addon or plugin code.
- The task is about addon bootstrap, compatibility checks, namespaces, widgets, controls, editor controls, editor panels, Finder, context menu, managers, or scripts and styles.
- The feature should work with Elementor core without depending on Pro-specific extension points.

## Route To Elementor Pro When

- The owner is reusable addon or plugin code.
- The task is about dynamic tags, form actions, form fields, forms hooks, or Theme Builder conditions.
- The request depends on Pro-only runtime behavior or Pro-owned editor surfaces.

## Route To Hello Elementor Theme When

- The task edits the parent theme codebase itself.
- The task changes Hello filters, theme supports, menu registration, Elementor kit integration, content width, title handling, theme location registration, theme location display wrappers, or other theme-owned Elementor compatibility.

## Route To Hello Elementor Child When

- The task is a site-specific override in child theme `functions.php` or `style.css`.
- The task customizes parent theme behavior without changing the parent theme package itself.
- The task is local to one site, one install, or one deployment.

## Route Outside Elementor When

- The feature is generic WordPress plugin logic with no Elementor API dependency.
- The feature is generic theme rendering with no Elementor or Hello-specific API dependency.
- The feature changes WordPress Core behavior.

## Fast Heuristics

- If the request names `hello-theme-main` or a `hello_elementor_*` hook, prefer the Hello parent theme skill.
- If the request names `hello-theme-child-master`, child `functions.php`, or child `style.css`, prefer the Hello child theme skill.
- If the request names dynamic tags, form actions, form fields, forms hooks, or conditions in reusable addon code, prefer Elementor Pro.
- If the request names widgets, controls, Finder, context menu, managers, or editor panels in reusable addon code, prefer Elementor Free.
- If the request mixes feature type and owner ambiguously, stay in the routing skill until the owner is explicit.