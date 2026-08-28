# Reference-Site-Design Mode

Use this mode for public marketing, launch, campaign, and product websites whose identity depends on visual composition, media scale, motion, navigation, and responsive transformation.

Do not use this mode for ordinary admin dashboards, internal tools, or native application screens. Do not import compact operational-UI defaults from `frontend-engineering` unless the public surface genuinely needs them.

## Abstraction boundary

References may influence:

- composition and visual balance;
- image-to-type relationships;
- contrast hierarchy and accent allocation;
- texture density and edge treatment;
- scale jumps, overlap, cropping, and depth;
- navigation, scene rhythm, motion, and responsive transformation.

Do not retain scene-specific output such as recognizable subjects, named motifs, exact colors, literal props, brand copy, asset-specific component branches, or the reference's technology stack.

Classify observations as:

- **defining mechanism**: removing it changes the experience category;
- **reusable relationship**: scale, rhythm, crop, density, timing, or interaction hierarchy;
- **scene-specific output**: literal imagery, wording, color, motif, or prop;
- **incidental implementation**: framework classes or technical details that do not determine the experience.

Preserve defining mechanisms, generalize reusable relationships, replace scene-specific output, and ignore incidental implementation.

## Workflow

1. Inspect the target product surface, content ownership, routes, interactions, supplied assets, framework, and responsive requirements.
2. Inspect references at equivalent states: loaded desktop, early and middle transition, settled scene, content-heavy scene, navigation overlay, compact hero, compact transition, and compact navigation.
3. Record a same-state comparison covering type mass, media occupation, boundary crossing, simultaneous layers, motion roles, text settling, quiet-space tension, navigation, and scene handoff.
4. Define the story spine, scene inventory, title treatments, media slots, theme roles, motion graph, navigation model, and responsive transformations before implementation.
5. Build semantic structure first. Keep essential text in the DOM and separate content, media, motion, theme, and presentation ownership.
6. Implement real defining interactions. A static storyboard, written motion plan, or manual slider does not replace required scroll choreography.
7. Review with [review.md](review.md) and provide rendered evidence unless the caller explicitly waives it.

## Navigation integrity

Classify each navigation item as a route, in-page anchor, stateful directory control, or primary action. Preserve that classification unless the task explicitly changes information architecture. A route directory must not become section navigation merely because an immersive page has chapters.

## Scene density

List each scene's narrative job, dominant media, primary transformation, title treatment, proof state, and handoff. Do not let distinct chapters collapse into one repeated mechanism under different copy. Long scroll distance without state change is not scene richness.

## Copy and ornament discipline

Do not invent unexplained short English kickers, status abbreviations, badge copy, or tiny-label-plus-accent-rule decoration to simulate detail. Microcopy and annotations need a real information role.

Avoid generic glass panels, repetitive rounded cards, arbitrary bento grids, blurred decorative blobs, excessive shadows, empty outline boxes, and the standard split hero unless the reference, content, or product structure supports them.

## Confidentiality

Extract only portable relationships. Do not copy private source code, internal directory trees, business names, routes, assets, configuration, or organization-specific implementation into this mode or its examples.
