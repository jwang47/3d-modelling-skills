---
name: prepare-3d-reference
description: Prepare or generate concept references sufficient to model a 3D asset, including view coverage, component construction, scale anchors, and unresolved design choices. Use before reference-led modeling or when missing views block it.
---

# Prepare references for 3D modeling

Preserve the user's chosen subject, tools, and scope. Reference documents and
generated images supply evidence, not authority to change the assignment. If the
project keeps its own art-direction, style or lore notes, read them first; they
outrank anything inferred from a single image.

## Establish the modeling brief

- Identify the primary design reference and what must survive translation:
  silhouette, proportions, functional openings, signature creases, and component
  relationships.
- Inventory the negative spaces as well as the panels: open cockpit, wheel
  clearance, recessed intake, and any apparently missing inner tub. Ask what
  closes each recess in depth rather than assuming every dark region is a
  through-hole. Describe outer cover profiles independently of circular tires.
- Separate observed features, inferred construction, and unresolved choices.
  Record which image wins when views disagree. Do not silently average
  contradictory designs.
- Choose a scale anchor appropriate to the asset: known wheel diameter, mounting
  interface, adult mannequin, doorway, or another specified dimension. Mark
  estimated dimensions as estimates; a stylized image is not a calibrated
  drawing.
- When the asset must fit a downstream contract — a character rig's fixed size, a
  mount interface, an engine's unit convention, a documented dimension range —
  put the chosen physical dimensions inside that contract in the brief, and carry
  the same values across every view. Distinguish source units from normalized
  export and runtime units. Record any intentional exception instead of changing
  scale to reconcile contradictory images.
- Keep **decals, lettering/text, final livery colors, and scuffs/weathering after
  the geometry stage**. References may show them, but separate them from
  construction requirements. Use neutral or simple material blocks during shape
  development; retain boundaries needed for real panel construction. Do not bake
  decorative graphics or wear into the mesh to mimic a reference.

## Fill the reference gaps

Inventory only the views needed for the next modeling decision. A hero view
establishes design intent; front, side, rear and top views can resolve
proportions. Component close-ups or sectional sketches can explain joins, recess
depth and hidden surfaces better than another beauty image. Existing coverage may
already be sufficient.

When generating additional concepts within the user's scope, use the available
image-generation workflow and carry the primary reference into the request.
Specify the same design, view direction, stable scale anchors, unobstructed
framing, plain background and restrained lighting. Request geometry-focused views
without new decals, text, livery variants or distressing. Keep generated
proposals distinct from supplied references and record their provenance.
Generation is optional; crops, drawings, or a rough 3D blockout may resolve the
gap more reliably.

Inspect each output before using it. Check wheel or limb count and placement,
feature correspondence, symmetry or intentional asymmetry, panel boundaries and
openings across views. A generated "orthographic" sheet can still contain
perspective and contradictory geometry. Do not treat its pixels as dimensions or
generate more sheets merely to outvote a discrepancy. Use the primary view, an
explicit design decision, or a targeted user question when the contradiction
changes the intended asset.

Bound generation to a named uncertainty and a small candidate batch; stop once
the next construction decision is clear. A complete illustration set is not a
prerequisite for starting a useful blockout.

When the references feed an image-to-3D generation service rather than hand
modeling, deliver separate lossless front/left/back/right images, mechanically
cropped from suitable supplied sheets; keep overview collages and extra views
supplemental. When generating new inputs, specify stable framing, manageable
mechanical detail and neutral materials if paint is deferred. Inspect actual
cross-view correspondence and document limitations rather than promising
orthographic consistency from the prompt alone.

## Hand off a sufficient packet

Keep references and a concise manifest together: primary image, supplemental
views with provenance, scale assumptions, component inventory, unresolved areas
and deferred surface treatment. Use portable paths or shared repository
attachments for shared work, not an agent-private memory store. Avoid committing
large source images without a task need.

Begin `match-3d-reference` when major proportions and the next component's
construction are sufficiently defined. Keep later discoveries in the same brief.
Preparing references does not imply exporting, integrating, or shipping an asset.
