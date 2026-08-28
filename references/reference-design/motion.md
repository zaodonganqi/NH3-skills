# Motion, Media, and Typography

Use this reference when the source or caller requests scroll choreography, experimental launch behavior, animated display type, pointer response, product walkthroughs, or deliberately high variety.

## Variety matrix

For every major scene, record:

| Scene | Narrative job | Primary media | Dominant mechanism | Secondary interaction | Title treatment | Settled text strategy |
|---|---|---|---|---|---|---|

Adjacent scenes should differ materially in mechanism, media composition, and typography role. Changing only direction, distance, scale, rotation, duration, or easing does not create a new mechanism.

Possible mechanisms include layered choreography, object convergence, clip or mask transitions, kinetic typography, pinned product walkthroughs, horizontal snap sequences, media activation, ribbons or paths, pointer/tilt response, and state replacement. Choose only mechanisms that serve the scene's narrative job.

## Motion graph

Define named states before transforms:

```text
approach -> enter -> settle -> hold -> handoff -> exit
```

Inventory camera/background, primary subject, secondary props, typography fragments, navigation, line or particle fields, product proof, and transition masks separately. Give layers distinct responsibilities and timing.

Keep phase thresholds in a motion model rather than scattering unrelated progress decimals through components.

## Physical timing budgets

Convert user timing requests into physical budgets:

- time animation: `new duration = base duration / requested speed`;
- scroll entry or exit: multiply its physical travel by the requested duration factor;
- visual dwell: multiply the physical distance of the fully settled hold;
- title hold and product-proof insertion: budget independently from general scene dwell.

Derive total sticky travel from transition and hold budgets, then derive section height. Do not multiply section height alone and assume all phases received the requested factor.

For pinned scenes, progress should complete while the canvas is still pinned, normally through an equivalent of `start start` to `end end` in the selected motion library.

## Title treatments

Every dominant display title in an experimental public site has an observable animated role. Vary family category, weight, width, slant, fill/outline, orientation, alignment, line composition, or animation mechanism where the reference supports it.

Text lines may cross during transitions. At every settled or hold state, line boxes must not overlap and must have at least one CSS pixel of clear separation. Check actual settled geometry after localization and compact recomposition; a nominal `line-height` alone is not proof.

## Product handoff

When illustrative choreography precedes product proof:

```text
title enters
-> illustration establishes and holds
-> conflicting foreground layers yield
-> product proof enters
-> proof settles and holds
-> scene exits
```

Temporary overlap is allowed. At proof hold, remove accidental collisions and keep the important product surface inside the viewport. If insertion has a multiplier, enlarge entry duration or travel itself; a longer static hold is not a slower insertion.

## Performance and fallback

- Prefer transforms, opacity, masks, and controlled playback.
- Keep one dominant scroll-linked transformation per viewport.
- Stop offscreen loops and observers.
- Clamp scale and translation to protect crops.
- Keep semantic content outside canvas-only rendering.
- Reduced motion removes long scrubbing, parallax, and auto-moving sequences while preserving settled information and actions.

Compact screens may use shorter ordered states, but they preserve narrative order and a genuine readable hold rather than blindly shrinking desktop progress ranges.
