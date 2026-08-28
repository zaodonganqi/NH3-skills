# Frontend Engineering Mode

Use this mode for application code, admin systems, dashboards, portals, internal tools, component libraries, and product-facing frontend workflows. Read the framework adapter separately; this document owns framework-neutral engineering decisions.

## Inspect before editing

Identify the actual runtime and boundaries from manifests, lockfiles, framework configuration, route definitions, entrypoints, data clients, state ownership, styling, tests, and deployment scripts.

Preserve existing capabilities. Refactoring, navigation cleanup, page merging, or layout changes must not make a route, permission, action, or deep link unreachable unless the task explicitly removes it.

Keep diffs narrow. Do not replace dependencies, restyle unrelated pages, reorganize the whole tree, or reformat untouched code to make a local change appear consistent.

## Architecture responsibilities

Use responsibility boundaries rather than framework-specific folder names:

- bootstrap and providers compose the application;
- routes or pages own navigation entrypoints and route-level data boundaries;
- features own cohesive user workflows;
- reusable components own stable UI or domain fragments;
- state modules own cross-view client state, not arbitrary local values;
- services or data modules own requests, DTO mapping, persistence, and external effects;
- shared utilities stay pure and do not import feature UI;
- configuration maps environment and runtime inputs;
- styles and theme modules own semantic tokens and global presentation rules.

Page or route components orchestrate. Extract components, hooks, composables, directives, services, stores, or utilities only for real reuse, testability, effect isolation, or material complexity reduction.

Avoid vague abstractions such as `common`, `misc`, `helpers`, `manager`, or `handleProcess` when a precise domain or responsibility name exists.

## Operational UI and information architecture

Admin, dashboard, portal, and tool interfaces should be compact, clear, and scannable:

1. Put real controls, data, task state, filters, forms, or primary actions in the first screen.
2. Use stable workspace regions: navigation, optional list or filter context, and a flexible primary pane.
3. Give flexible panes `min-width: 0`; define deliberate min/max widths for persistent navigation and secondary panes.
4. Align titles, tabs, filters, and actions to shared bars, heights, and baselines.
5. Use cards only for meaningful grouping, repeated objects, or temporary/modal surfaces.
6. Keep loading, empty, stale, and error states inside the region they affect while preserving recovery actions.
7. Collapse secondary panes deliberately on narrow screens; do not merely shrink the desktop layout.
8. Preserve route, permission, and workflow semantics during visual cleanup.

Do not import public-site hero composition, campaign motion, decorative metrics, or editorial slogans into an operational interface without a product reason.

## Visual system

- Define semantic roles for page, raised surface, navigation, border, primary action, muted text, success, warning, and error.
- Follow the repository's spacing, typography, radius, icon, and elevation system. If absent, establish a small coherent set rather than scattered literals.
- Use borders, contrast, and spacing for most hierarchy. Reserve shadows, blur, glow, and gradients for meaningful elevation or brand context.
- Do not introduce Tailwind or another utility-first system into a semantic or component-scoped codebase merely for convenience. If the repository already uses one, follow its established conventions instead of replacing it.
- Avoid text overflow, control collisions, clipped actions, layout-shifting hover effects, and nested scroll areas without clear ownership.

## Copy and i18n

Use the repository's localization or copy system for new and changed user-facing text. Keep locale keys aligned across supported languages.

Menus, buttons, dialogs, empty states, validation, and errors must describe real behavior. Copy should state status, result, or next action; do not explain obvious layout or unfinished design intent.

Internal logs, tests, and developer comments do not require localization when users cannot see them.

## JavaScript and TypeScript

- Do not use `var`; prefer `const`, and use `let` only for reassignment.
- Follow modern module syntax and the target project's language level.
- In TypeScript, model external DTOs, domain objects, public component inputs, route metadata, and shared state explicitly.
- Do not use `any`, unchecked casts, or untyped object pass-through to silence errors. Isolate and explain unavoidable boundary escapes.
- Async workflows must expose failure, cancellation, stale-result, and loading behavior when relevant.
- Public exports need deliberate ownership; do not expose internal helpers casually.

## Function and comment boundaries

Extract a function when logic is reused, branching becomes difficult to read, business meaning is stable, direct testing matters, or a side effect needs isolation. Do not wrap one line, create a thin handler for every tiny control, or split a short flow into generic steps.

Comments must explain purpose, domain meaning, side effects, constraints, or non-obvious behavior rather than restating syntax. For new or materially changed functions, shared/module constants, reactive or store state, and utility modules, add current comments when the repository does not already provide a stronger documentation convention.

Match the surrounding comment language. Multiline documentation comments span multiple lines. `TODO`, `FIXME`, and `HACK` include a scope and next action.

## Environments and browser exposure

- Separate development, test, staging, and production only as much as the product needs.
- Document supported values in an example environment file or project docs.
- Never expose secrets through browser-prefixed environment variables, client bundles, source maps, logs, storage, or public configuration.
- Production must not silently fall back to development endpoints.
- Use framework-appropriate public-variable conventions discovered from the target repository; do not assume a Vite prefix in every framework.

## Security, accessibility, and reliability

- Real authorization is enforced server-side; frontend guards are user-experience boundaries, not security proof.
- Avoid raw HTML. Sanitize trusted rich-text boundaries.
- Validate upload/import type, size, progress, cancellation, and errors.
- Give controls accessible names, visible focus, keyboard operation, and usable contrast.
- Keep user-visible failures concise and actionable; do not expose stack traces or internal links.
- Evaluate bundle and runtime cost before adding large dependencies.
- Respect reduced motion and avoid unnecessary full-page rerenders or blocking initial work.

## Validation and release

Default to static inspection unless the caller requests execution. Static checks cover syntax, links, imports/exports, route reachability, environment names, config fields, and documentation consistency.

When requested, use the repository's own package manager and scripts for lint, formatting checks, type checks, unit tests, integration/e2e tests, production build, preview, or release smoke checks. Do not invent framework commands when scripts already exist.

Report every command actually run, its result, and validation that remains outstanding.
