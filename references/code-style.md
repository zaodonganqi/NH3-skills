# Code and Line-Format Standards

Use these standards when the repository does not already define an equivalent rule.

## Precedence

1. Repository-local instructions.
2. Formatter, EditorConfig, lint, compiler, and generated-code configuration.
3. Established conventions in the edited file and neighboring modules.
4. NH3 fallback rules below.

Do not fight an established formatter. Do not reformat unrelated files or change global formatting policy as a side effect of feature work.

## Encoding and line endings

- UTF-8 text.
- LF line endings.
- Exactly one final newline.
- No trailing whitespace in code or configuration.
- Preserve intentional Markdown hard breaks.
- Do not write byte-order marks unless the repository requires them.

## Indentation and width

- Use spaces for authored web code; default to two spaces when no local rule exists.
- Use tabs only where the language or repository requires them, such as a Makefile.
- Treat 100 columns as a soft limit for authored code when no formatter limit exists.
- Long URLs, hashes, generated identifiers, snapshots, tables, and machine-generated files may exceed the limit.

## Wrapping

- Break long function calls, arrays, objects, imports, JSX props, template attributes, and chained expressions at semantic boundaries.
- Put one argument, property, or prop per line when the construct no longer fits cleanly.
- Indent continuation lines consistently and include trailing commas in multiline structures when the language and formatter support them.
- Do not place multiple independent statements on one line.
- Leave one blank line between top-level declarations and between materially different logical blocks.
- Avoid manual alignment with repeated spaces; formatters and proportional fonts make it unstable.

## Imports

- Follow the repository's import sorter when present.
- Otherwise group runtime/platform imports, external packages, internal modules, and relative modules with minimal blank-line separation.
- Remove unused imports and avoid wildcard barrels that hide ownership or create cycles.
- Keep type-only imports explicit when the language and compiler support them.

## Syntax and naming

- Do not use `var` in JavaScript or TypeScript.
- Prefer `const`; use `let` only for reassignment.
- Match local semicolon, quote, filename, component, and test naming conventions.
- Use names that express domain or responsibility. Avoid `data`, `item`, `temp`, `common`, and `helper` when a precise name exists.
- Keep public exports deliberate and internal details unexported.

## Comments

- Explain purpose, domain meaning, side effects, invariants, or non-obvious constraints.
- Do not narrate syntax or preserve stale implementation history.
- Match the surrounding comment language and tone.
- Multiline documentation comments span multiple lines.
- `TODO`, `FIXME`, and `HACK` include scope and next action.

## Framework files

- Format Vue, Svelte, Astro, JSX, and TSX with the repository's parser-aware formatter.
- Preserve framework-required directive placement and script/style block semantics.
- Wrap templates or props without changing rendered whitespace when whitespace is meaningful.
- Keep server/client directives, route exports, metadata, and framework-reserved filenames in their required positions.

## Generated and vendored files

Do not manually reformat generated code, lockfiles, snapshots, compiled output, vendored sources, or framework-generated manifests. Regenerate them with their owning tool only when the task requires it.

## Diff check

Before handoff, inspect for mixed line endings, missing final newlines, trailing whitespace, accidental whole-file rewrites, formatter churn, and unrelated generated changes.
