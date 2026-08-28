# NH3.skill

[简体中文](../README.md) | **English**

NH3.skill is a personally maintained, cross-project, multi-framework frontend skill. It does not belong to any business project and contains no private project source, directory tree, routes, assets, configuration, or business naming.

NH3 provides two isolated capabilities:

- `frontend-engineering`: multi-framework frontend engineering, application architecture, refactoring, operational UI, environments, security, validation, and release readiness.
- `reference-site-design`: visual, layout, motion, and interaction systems abstracted from references for public marketing, launch, campaign, and product sites.

The modes run together only when the caller explicitly selects `combined`. This keeps dashboard engineering rules out of marketing sites and campaign-style visual rules out of operational applications.

## Contents

```text
NH3-skills/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── zh-CN.md
│   ├── frontend-engineering.md
│   ├── framework-adapters.md
│   ├── code-style.md
│   └── reference-design/
│       ├── mode.md
│       ├── system.md
│       ├── motion.md
│       └── review.md
├── docs/
│   └── README.en.md
├── .editorconfig
├── LICENSE
└── README.md
```

## Modes and use

Copy or install this directory into the skill location used by an AI coding tool. Name the mode when invoking it.

Engineering mode:

```text
Use $nh3 in frontend-engineering mode to review this React dashboard and fix the issues you find.
```

Reference-design mode:

```text
Use $nh3 in reference-site-design mode to redesign this public product site from the supplied references.
```

When both are explicitly needed:

```text
Use $nh3 in combined mode for this full-stack framework's public product surface.
```

If the mode is omitted and the surface is ambiguous, the skill asks the caller to choose instead of silently blending modes.

## Framework scope

NH3 supports browser frontends and frontend surfaces in full-stack frameworks, including:

- React, Next, and Remix-style stacks;
- Vue and Nuxt;
- Svelte and SvelteKit;
- Angular;
- Solid and SolidStart;
- Astro and multi-framework islands;
- native HTML, CSS, JavaScript, TypeScript, and comparable web toolchains.

The skill first detects the target repository's framework, router, rendering model, state, styling, tests, and deployment boundary, then maps portable responsibilities onto that stack. It never copies Vue, React, or a real project's directory structure into another framework.

Backend-only services, infrastructure-only work, native Android/iOS applications, native desktop apps, and unrelated data pipelines are outside scope.

## Code format

Repository formatter, lint, and EditorConfig rules take precedence. Without local rules, NH3 uses:

- UTF-8;
- LF line endings;
- one final newline;
- no trailing whitespace in code or configuration;
- two-space indentation for common web formats;
- a 100-column soft limit for authored code;
- semantic wrapping by argument, property, or prop;
- no manual formatting of generated code, lockfiles, snapshots, or unrelated files.

See [references/code-style.md](../references/code-style.md) for the complete standard.

## Confidentiality boundary

This repository may contain only portable frontend principles, responsibility boundaries, decision criteria, and neutral examples.

Do not include or distribute:

- private project source;
- real project directory trees or module names;
- internal routes, business copy, role names, or permission names;
- brand assets, screenshots, configuration values, or infrastructure details;
- components, styles, or interactions copied directly from one project.

Real projects may inform framework-level relationships only after every identifiable implementation detail is removed.

## Maintenance

Keep `SKILL.md` as a concise mode router and shared baseline. Detailed rules stay in the relevant references so the two modes remain separate.

`references/zh-CN.md` mirrors `SKILL.md` in Chinese. Framework guidance belongs in `framework-adapters.md`, engineering rules in `frontend-engineering.md`, and reference-driven design rules under `reference-design/`.

Use UTF-8 and LF for all text. After changes, run skill validation, Markdown link checks, `git diff --check`, and a private-information scan.

## License

Apache-2.0
