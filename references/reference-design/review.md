# Reference-Site Review and Handoff

Use this reference before delivering a reference-driven public site.

## Required evidence

Verify the actual rendered result at equivalent states:

- loaded desktop hero;
- early, middle, and settled states of defining transitions;
- representative product-proof and content-heavy scenes;
- desktop navigation overlay or directory interaction;
- compact hero, transition, and navigation;
- reduced-motion output;
- keyboard focus and changed interactions;
- console and runtime health.

If the caller waives visual verification, state that it was not performed. Compilation and static code inspection are not rendered evidence.

## Deliverable contract

Keep these boundaries observable in code or configuration:

- content and chapter order;
- semantic media manifest with ratio, fit, focal points, safe areas, fallbacks, and compact behavior;
- project theme roles;
- named motion phases and physical timing budgets;
- navigation classification;
- responsive preserve/recompose/collapse/remove decisions;
- reduced-motion behavior;
- asset-replacement procedure.

For each important reference behavior, record:

```text
observed evidence -> reusable relationship -> project input -> implementation consequence
```

## Adversarial swap

Test materially different media or temporary non-deliverable substitutes: light/dark, sparse/dense, left/right focal, and wide/tall. Slot metadata and theme values may change; component hierarchy, selectors, and motion phases must not.

## Hard failures

Correct these before handoff:

- reference technology, brand copy, motif, exact color, or recognizable assets were copied instead of abstracted;
- a defining scroll or layered mechanism was downgraded to static stacked sections;
- major media all remain bounded rectangles when the reference depends on boundary participation;
- high variety was requested but scenes reuse one asset, title template, and mechanism;
- a dominant title is inert or settles with overlapping lines;
- large quiet regions have no scale, media, motion, crop, depth, or transition tension;
- route navigation was converted into section navigation without authorization;
- generic cards, glass panels, bento grids, empty frames, or tiny-label-plus-accent-rule filler replaced actual composition;
- unexplained short English kickers, badge copy, or status abbreviations were invented to simulate detail;
- a formulaic marketing copy stack or a disguised variant remains anywhere on the page (see the [shared layout ban](../../SKILL.md#ban-on-formulaic-marketing-copy-layouts));
- the requested website or application page was replaced by an infographic, connection diagram, or poster to evade the layout ban;
- product proof uses the wrong ratio, acts as an empty placeholder, remains materially offscreen, collides at its settled state, or has no useful hold;
- the first viewport subject is accidentally pinned to several edges;
- compact output is only a shrunken desktop composition;
- essential interaction depends only on hover;
- reduced motion removes information or actions;
- user speed or dwell multipliers were not applied to the actual phase budgets;
- private project code, directory structure, business names, routes, assets, or configuration entered reusable guidance or examples;
- the handoff claims visual verification that did not occur.

## Final summary

State what remains stable when media changes, which project-level inputs are editable, what was visually verified, which checks were waived, and any intentionally omitted enhancement.
