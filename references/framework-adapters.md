# Framework and Directory Adapters

Use this reference to map NH3's responsibility boundaries onto the target framework. It is not a template to copy verbatim.

## Precedence

1. Existing coherent repository structure.
2. Framework routing and build conventions.
3. Product-domain boundaries.
4. NH3 fallback structure.

Do not reorganize a mature project solely to match this document. Do not copy a private project's directory tree, names, or module boundaries into reusable guidance.

## Framework-neutral responsibility map

For new projects or justified structural repair, use only the directories the product needs:

```text
project/
├── docs/                 # Maintained architecture and operating notes
├── public/               # Assets served without source transformation
├── src/
│   ├── app/              # Bootstrap, providers, root composition
│   ├── routes/           # Route entrypoints when the framework does not own them elsewhere
│   ├── features/         # Cohesive product workflows grouped by domain
│   ├── components/       # Reusable UI and stable domain components
│   ├── state/            # Cross-view client state
│   ├── services/         # API, persistence, adapters, external effects
│   ├── config/           # Runtime and environment mapping
│   ├── i18n/             # Locale resources and copy boundaries
│   ├── styles/           # Global styles, resets, tokens
│   ├── types/            # Shared public types when needed
│   └── utils/            # Pure framework-independent helpers
├── tests/                # Tests not colocated with source
├── package.json
└── README.md
```

This is a responsibility map, not a mandatory tree. Colocate tests, styles, loaders, actions, hooks, stores, and types with a feature when that makes ownership clearer.

## React

- Keep application bootstrap and providers near the root entry.
- Route ownership follows the selected router.
- Reusable stateful logic usually lives in hooks; pure logic remains outside React.
- Keep component-local state local. Use shared state only when multiple routes or distant branches genuinely coordinate.
- In React Server Component environments, mark client boundaries narrowly and keep server-only values out of client modules.

## Next.js and Remix-style full-stack React

- Respect the framework's route filesystem; do not recreate a parallel `routes` tree.
- Keep route loaders, actions, metadata, and error boundaries near their route owner.
- Separate server-only modules, client components, and shared serializable contracts.
- Do not leak secrets or server dependencies across a client boundary.
- Route groups and layout nesting express composition, not arbitrary taxonomy.

## Vue

- Use components for UI, composables for lifecycle-aware reusable behavior, and plain modules for pure logic.
- Keep router and store conventions aligned with the existing Vue stack.
- Follow local SFC organization and Options/Composition API choices rather than rewriting styles globally.
- Feature-local composables, stores, and components may stay together when they have one owner.

## Nuxt

- Respect Nuxt-owned directories for pages, layouts, middleware, plugins, composables, and server boundaries.
- Keep client-only code explicit and protect runtime configuration exposure.
- Do not add a second manual router or duplicate auto-import ownership.

## Svelte and SvelteKit

- Keep reusable UI and modules under the framework's library boundary.
- In SvelteKit, respect filesystem routes, layouts, server/load boundaries, form actions, and hooks.
- Stores are for genuinely shared reactive state; local component state remains local.
- Do not import server-only modules into browser code.

## Angular

- Organize application code around features, shared UI, and singleton core services.
- Respect standalone-component or NgModule conventions already chosen by the repository.
- Keep route configuration, guards, interceptors, and providers within their intended ownership scope.
- Do not place feature-specific services into a global shared bucket by default.

## Solid and SolidStart

- Keep signals and effects close to their owner; extract shared reactive primitives only for real reuse.
- Respect route and server-function conventions in the selected meta-framework.
- Avoid destructuring patterns that break reactivity when local framework rules warn against them.

## Astro

- Treat `.astro` components as composition boundaries and islands as deliberate interactive opt-ins.
- Keep client hydration directives sparse and purposeful.
- Framework components embedded as islands follow their own local adapter without turning the whole project into that framework.
- Content collections and static assets stay in framework-owned locations.

## Other frontend frameworks

Map the same responsibilities onto the framework's official router, rendering, state, and build conventions. Do not invent a pseudo-React, pseudo-Vue, or pseudo-Next layout for an unfamiliar stack. Inspect its manifest and existing code first; consult authoritative documentation when current framework behavior matters.

## Monorepos and packages

- Each application or package owns its public entrypoints, tests, build configuration, and framework-specific source.
- Shared packages expose deliberate APIs and must not import application internals.
- Avoid a universal `shared` package that becomes a dumping ground.
- Keep browser, server, native, and tooling packages explicit when their runtime boundaries differ.
