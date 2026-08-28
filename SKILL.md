---
name: nh3
description: Apply NH3's framework-aware frontend engineering standards or its separate reference-driven public-site design workflow. Use for frontend implementation, refactoring, review, architecture, UI, validation, or release work across React, Vue, Svelte, Angular, Solid, Astro, Next, Nuxt, SvelteKit, and comparable web stacks. Select `frontend-engineering`, `reference-site-design`, or explicitly `combined`; do not silently blend the modes. Backend-only, infrastructure-only, and native-app work are out of scope.
---

# NH3 Frontend Standards

NH3 is a multi-framework frontend skill with two intentionally separate modes. It is not a Vue-only skill and it is not a single blended design-and-engineering doctrine.

## Mode selection

The caller should choose one mode:

- `frontend-engineering`: application architecture, implementation, refactoring, operational UI, routes, state, i18n, environments, security, tests, builds, and release readiness.
- `reference-site-design`: public marketing, launch, campaign, and product websites whose visual, layout, motion, and interaction systems are extracted from references.
- `combined`: apply the engineering baseline and reference-driven public-site workflow together. Use only when the caller explicitly requests both.

Do not silently mix the modes. If no mode is named and the requested surface does not make the choice unambiguous, ask the caller to select one. An admin dashboard normally maps to `frontend-engineering`; a visually distinctive public launch site normally maps to `reference-site-design`.

## Shared baseline

These rules apply in every mode:

1. Inspect the target repository before editing. Treat its manifests, lockfile, source, routes, tests, formatter, lint configuration, local instructions, and established conventions as the primary facts.
2. Identify the framework, rendering model, package manager, router, state strategy, styling system, test tools, and deployment boundary. Do not infer architecture from filenames alone.
3. Preserve existing capabilities and information architecture unless the task explicitly changes them. A visual restyle does not authorize route, permission, or workflow changes.
4. Keep changes focused. Do not reformat unrelated files, replace established dependencies without need, or revert unknown worktree changes.
5. Reuse existing project conventions before introducing new abstractions, directories, components, hooks, composables, services, stores, or policy files.
6. Respect accessibility, reduced-motion preferences, error handling, environment separation, secret boundaries, and deterministic package-manager usage.
7. Report changed files, checks actually performed, checks omitted, and known limitations. Never present compilation or static inspection as rendered UI verification.

## Confidentiality and portability boundary

This skill contains framework-neutral standards only. Do not copy private project source, internal directory trees, business names, routes, assets, configuration values, infrastructure details, or organization-specific conventions into this skill or into examples intended for reuse.

When adapting a real project into reusable guidance, retain only responsibility boundaries, decision criteria, and framework-level relationships. Replace project-specific names and structures with neutral examples.

## Framework and directory guidance

Follow the existing repository structure when it is coherent. For new projects or structural repair, organize by responsibility and product domain rather than copying one framework's directory tree into another.

Read [references/framework-adapters.md](references/framework-adapters.md) when choosing or reviewing a directory structure. It provides a framework-neutral responsibility map and adapters for React, Next, Vue, Nuxt, Svelte, SvelteKit, Angular, Solid, Astro, and comparable stacks.

## Code and line-format standards

Read [references/code-style.md](references/code-style.md) for line endings, indentation, wrapping, import layout, multiline syntax, comments, generated-code exceptions, and formatter precedence.

Repository formatter and lint configuration take precedence. When no local rule exists, use UTF-8, LF line endings, a final newline, no trailing whitespace, two-space indentation for common web formats, and a 100-column soft limit for authored code.

## `frontend-engineering` mode

Read [references/frontend-engineering.md](references/frontend-engineering.md) completely before implementing or reviewing application code.

This mode prioritizes:

- route and capability reachability;
- stable component, state, service, and domain boundaries;
- compact and scannable operational UI;
- i18n and truthful user-facing states;
- environment, security, performance, and release safety;
- narrow diffs and validation proportional to the task.

Do not apply public-site hero, campaign motion, or editorial composition rules in this mode unless the product surface genuinely calls for them.

## `reference-site-design` mode

Read these references completely before acting:

1. [references/reference-design/mode.md](references/reference-design/mode.md)
2. [references/reference-design/system.md](references/reference-design/system.md)
3. [references/reference-design/motion.md](references/reference-design/motion.md) when motion, scroll choreography, or experimental typography is relevant
4. [references/reference-design/review.md](references/reference-design/review.md) before handoff

This mode prioritizes reference abstraction, narrative scenes, replaceable media slots, project-level theme inputs, purposeful motion, responsive recomposition, and rendered visual evidence.

Do not apply compact dashboard density, small operational title scales, or neutral admin-card patterns to a public marketing site merely because those rules exist in the engineering mode.

## `combined` mode

Use only when explicitly selected. Apply shared engineering boundaries first, then the reference-driven visual system to the public-facing surface. Resolve conflicts by product purpose:

- engineering owns data, routes, state, accessibility, security, environments, and maintainability;
- reference design owns public-page composition, visual hierarchy, media treatment, narrative motion, and responsive experience;
- existing repository rules and explicit user instructions override both.

## Validation policy

For `frontend-engineering`, default to static inspection unless the caller requests tests, build, browser work, runtime validation, or release checks. Use the repository's own commands when validation is requested.

For implemented `reference-site-design` work, rendered desktop and compact-screen verification is part of the workflow unless the caller explicitly waives it. If waived, state that it was not performed.

## Scope boundary

NH3 applies to browser frontend code and frontend-facing full-stack framework surfaces. It may reason about API contracts and server/client boundaries, but it does not govern backend-only services, infrastructure, native Android/iOS applications, or unrelated data pipelines.

## Final checklist

Before declaring completion:

- the selected mode was explicit or unambiguous;
- framework-specific advice matches the detected stack;
- no private project implementation or naming was copied into reusable guidance;
- routes, permissions, actions, and required content remain reachable;
- code follows repository formatting or NH3 fallback line standards;
- new abstractions have a concrete responsibility;
- environment and browser-exposed values contain no secrets;
- validation claims match checks actually performed.
