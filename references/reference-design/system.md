# Reference-Driven Design System

Use this reference to define public-site structure, composition, media, theme, navigation, and responsive behavior independently of a specific frontend framework.

## Structural modes

Choose structure from content density:

- **immersive stage**: a strong promise and a small number of high-value chapters; full-viewport scenes transform during scroll;
- **indexed narrative**: many chapters or releases; persistent orientation accompanies alternating immersive and editorial surfaces;
- **modular story**: shorter product or company site; two or three composition patterns create rhythm without forcing a long scroll experience.

Modes may combine, but one narrative system must govern the page.

## Composition

- Establish a dominant axis: centered stage, asymmetric spine, or rail plus canvas.
- Give the primary marketing headline visual mass comparable to dominant media.
- Keep body copy within a readable measure even when media breaks boundaries.
- Use overlap for depth or sequence rather than as universal decoration.
- Allow non-text media to overlap and cross containers when the composition benefits.
- Alternate density, proof, breathing room, and transition intentionally.
- Charge large quiet regions through scale, media, motion, cropping, depth, or imminent change.
- Keep ordinary controls subordinate to narrative content.
- Give first-viewport subjects deliberate safe space; accidental contact with several viewport edges is a composition failure.

At least one major media treatment should participate in the page boundary when the reference depends on immersive staging. Do not reduce every image to a neat rectangle inside a grid.

## Semantic media slots

Treat media as data rather than scattering paths through components:

```ts
type MediaSlot = {
  src: string
  compactSrc?: string
  alt: string
  kind: 'image' | 'video' | 'canvas'
  aspectRatio: string
  fit: 'cover' | 'contain'
  focalPoint: { x: number; y: number }
  compactFocalPoint?: { x: number; y: number }
  safeArea?: { top: number; right: number; bottom: number; left: number }
  fallback: string
  treatment?: string
}
```

Common roles include hero backdrop, hero subject, chapter backdrop, product proof, supporting media, and texture overlay. Names express function, not a particular image or motif.

Reserve intrinsic space, define crop and compact focal points, provide fallbacks, and load critical media deliberately. Swapping valid media should require metadata changes, not component hierarchy or selector rewrites.

## Product proof

Product proof is a narrative state, not a placeholder obligation:

- use the required ratio and reserve its space;
- never force an unrelated illustration into a product-screen slot;
- integrate proof into an existing scene when it explains that scene;
- create a standalone proof scene only when it has its own narrative job and content;
- use multiple product states when several scenes demonstrate distinct behavior;
- keep important proof materially visible and at a useful scale during its settled hold;
- yield conflicting foreground choreography before proof settles.

## Theme inputs

Derive project-level roles for surfaces, text, accents, semantic states, lines, media treatment, controls, typography, and optional texture. Components consume semantic roles rather than literal reference colors or asset names.

The system passes an adversarial swap only when light/dark, sparse/dense, left/right focal, and wide/tall media can change through slot metadata and theme inputs without structural code changes.

## Navigation and interaction

- Preserve route, anchor, directory-control, and primary-action semantics.
- Keep the main action available without dominating every scene.
- Use chapter orientation only when long content benefits from it.
- Interactive media needs explicit controls and keyboard/touch access.
- Hover may enrich a state but cannot exclusively reveal essential content.

## Responsive transformation

Define what compact screens preserve, recompose, collapse, remove, or replace:

- preserve narrative order, content meaning, and actions;
- switch to compact focal points and safe areas;
- turn side-by-side proof into an ordered vertical sequence;
- reduce simultaneous layers before shrinking type excessively;
- replace persistent rails or complex navigation with an appropriate compact control;
- test both tall and short compact viewports.

Responsive work is a recomposition, not a scaled-down desktop screenshot.
