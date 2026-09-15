---
name: match-3d-reference
description: Build or iteratively refine a 3D model against concept images using component comparisons, connected surface construction, and fit checks. Use for reference-led Blender or other mesh authoring, including standalone assets; not for raster-only edits.
---

# Match a 3D reference

Use `prepare-3d-reference` when missing or contradictory references block
construction. Preserve the user's tool choices and the stated scope: authoring a
source mesh does not authorize exporting it, integrating it into a runtime, or
running a paid generation service. If the project documents its own rendering
invariants, asset pipeline or dimension contracts, read those before editing;
they outrank anything inferred here.

## Establish the baseline

Identify the actual retained source model, reference hierarchy, units/axes, root
transforms and protected interfaces. Save a reproducible baseline before edits.
Render the source mesh rather than using an image edit as evidence of a geometry
change.

Where the asset has a documented dimension contract — a rig's fixed character
size, a mount interface, an allowed length/width/height range — enforce it during
blockout and again at export and reimport. Record evaluated source dimensions
against the allowed ranges, body-only versus assembly bounds, normalization and
runtime conversion. Fit the actual supported rigs at their fixed sizes before
detailing an enclosing cockpit or interior; a proxy establishes only preliminary
fit. Preserve figure size and limb proportions between assets. Report
out-of-range measurements and explicit exceptions rather than shrinking the
figure, stretching limbs or relying on a loader clamp. Recheck dimensions and fit
after packaging changes; a range pass alone does not establish clearance or
visual acceptance.

Establish that fit during the initial blockout, before refining the body shell,
seat cushions or cockpit details. Use the target application's actual character
asset with its configured scale and rig proportions; a generic adult mannequin
does not establish fit for a stylized character. Fit the intended character
first, then check the other supported sizes before claiming general
compatibility. When the real asset is unavailable, use a proportionate posed
proxy, record its dimensions and assumptions, and label the result preliminary.
Check seated pelvis and back contact, head and shoulder clearance, control reach
with elbow bend, and knee and foot space in side, top and oblique views. Resolve
packaging conflicts before polishing the surrounding surfaces, and never float
the figure to manufacture a fit. Recheck after moving the seat, wheel, pedals,
cage or enclosing panels. Keep this early static fit check distinct from later
animation and runtime-camera verification.

When resuming an asset with rejected attempts, read its recorded outcome before
choosing a baseline. Prefer the user's selected construction over the most recent
saved experiment, and keep a rejected candidate labeled as rejected.

Use the project's own visual-verification and measurement procedures for
inspected evidence and for bounded variants or measured claims. For a standalone
model, render through the authoring tool in hidden/background mode, taking
whatever machine-contention lock the project uses; browser or engine capture is
needed only when that runtime is part of the requested result.

Keep **decals, text/lettering, final livery colors, and scuffs/weathering until
after geometry review**. Use neutral or simple material blocks to distinguish
real panels. Do not spend shape iterations tuning graphics or distressed
textures, or let them disguise a poor silhouette. Preserve existing decoration
when unrelated, but judge the mesh without depending on it.

## Compare components and choose the next change

- Match broad framing using stable landmarks, then hold camera and lighting fixed
  between model variants. Use front, side or top views when a hero camera hides
  the defect. Do not change camera and geometry together and attribute the entire
  improvement to the mesh.
- Inspect corresponding concept/model crops with aspect ratio preserved. Label
  independent framing and perspective differences; do not stretch crops into a
  false match. Distinguish geometry, normals, material and lighting hypotheses.
- For reported ridges, waviness or pinching, reproduce the user's exact close-up
  before editing. Keep a cheap fixed-camera set with reflective shading, flat
  shading and actual vertices/edges, plus an adjoining or opposite view. For
  standalone Blender work, use Workbench or an equivalent fast authoring render
  for this loop; defer expensive path-traced or engine renders until the local
  defect passes these checks.
- Rank discrepancies by silhouette/proportion, connected panel construction,
  functional fit, then small geometric details. Work on a bounded component or
  assembly with an observable stop condition.
- Describe the reference's construction: where a crease starts and ends, which
  surface is inset, how a band turns a corner, what forms an intake wall, and how
  one panel meets the next. "Smoother" is not a sufficient construction plan.

## Build surfaces that explain the reference

For smooth automotive or product body panels, start with a sparse, deliberately
laid-out control mesh and live subdivision (or an equivalently editable
low-control parametric surface). Use dense generated or scanned geometry as a
shape reference. Place controls around silhouette changes, intentional creases,
openings and panel joins; resolve the broad curvature before adding local detail.
Traced feature curves can guide this cage, but do not commit them to dense
editable geometry early. Decimating a noisy mesh is not a substitute for
designing its control layout.

Keep the control cage and subdivision modifier editable in the retained source;
apply or tessellate on an export copy when needed. Add loops only to support an
identified shape requirement, and avoid crowding support loops or poles into a
smooth highlight transition. Inspect both the sparse cage and evaluated surface
from the fixed close-up views before increasing density. Preserve UV seam intent
while refining the cage, then validate the evaluated export separately.

Treat connected parts together: for example bumper, stripe boundary, corner
insert and splitter. Share boundary curves or section parameters where parts must
meet. Define strip width on its surface rather than guessing it from a
perspective crop.

For a replacement assembly, inventory every source contributing to its footprint,
including separately exported surfaces. Remove the superseded geometry there;
adding matching materials or surrounding pieces does not transfer ownership.
Verify the absence of the old construction in a fixed overhead or profile view.

Preserve deliberate creases and use controlled curvature between them. When
repeated local deformations cause pinching, waviness or a scalloped outline,
inspect topology and rebuild cross-sections and shared boundaries instead of
stacking another warp. Check split normals, bevel overlap and nonplanar faces
before using more subdivision or smoothing to conceal the problem.

Isolate the affected shell to rule out overlapping reference geometry, then test
geometry and normals separately on a diagnostic copy. Compare flat/edge views
with reflective shading using regenerated normals. Uneven face spacing can
produce highlight bands through face-averaged normals even on a smoothly fitted
surface; a shading improvement alone does not prove the geometry is sound. When
fitting an analytic or parametric surface, consider deriving normals from that
same surface. Regenerate those normals after shape edits and verify that
export/reimport preserves the result; do not use custom normals to conceal a
kinked silhouette or incompatible join.

Separate the outer silhouette from the protected inner opening. A wheel cover can
have a broad, flattened crown and tapered ends while its wheel-facing lip remains
circular. Model its side wall and return explicitly; changing the crown alone can
leave thin hanging strips. For fused skins, match the join tangent, avoid
coplanar outer walls, evaluate modifier operands before union, and check that
both original crowns survive. Recompute junction normals only after the connected
geometry is sound.

Inspect negative space from both sides early. Distinguish an intentional
through-opening from a recessed intake or missing inner wall. Close unwanted
see-through gaps with real tub or liner panels that meet the floor and shoulder
undersides, remain recessed behind outer skins, and clear the moving-part
envelopes. Apply a shared taper or proportion warp to every mating layer;
unrelated sparse sections can intersect even when their endpoints agree.

For environment assemblies that something walks or drives on, transfer ground and
collision ownership with the visible geometry. Test the replaced boundary as a
negative control, and inspect lowered reverse views for missing ground side
faces.

Apply transforms in a known coordinate space; parent scale and inverse-parent
transforms can make identical local edits produce different world-space results.
Keep protected wheel lips, mounts and figure contacts explicit. Do not change
limb lengths to make a bad cockpit fit.

When repositioning an assembly, inventory its attached trim, lights, lettering
and secondary surfaces and move them with the same pivot and transform. Preserve
fixed mounting anchors and rebuild or deform the connecting supports to meet the
new pose. Measure the actual chord or gap before converting a requested
percentage into model units; distinguish pivot translation from the motion of
pitched edges. Verify intended mounting contact as well as forbidden
intersections: a support floating below its target can pass every clearance
check. Inspect the joint from below and obliquely, and ensure any intentional
keyed overlap does not protrude through the visible skin.

For fit and visibility checks on a figure-carrying asset, use the target
application's actual character mesh and rig, including in standalone Blender
studies. Record the character asset, source revision, standing scale, seated pose
and contact placement. Use the intended character scale and preserve limb
proportions. Seat the evaluated skinned mesh on the cushion using its actual
pelvis and thigh surface, not the hip joint alone. Do not substitute primitive
mannequins or invented head and shoulder volumes for the character. If the asset
is unavailable, report the fit check as blocked; a rough construction guide is
not fit evidence.

For an asset seen from a following or chase camera, package the seat back,
headrest, cage and rear equipment so the head and both shoulders remain
distinguishable from that camera. Adjust occluding bodywork while preserving
seated contacts rather than floating or stretching the figure. Inspect the actual
seated figure from front, side and rear, and check evaluated figure/body
intersections with intentional seat and grip contacts classified separately.
Verify the supported character sizes in the actual runtime camera, including
steering and suspension poses; a front hero render or a single static Blender
pose does not prove rear readability across motion. Keep standalone pose checks
explicitly distinct from runtime verification.

Check seat-to-grip reach before polishing the cockpit. An IK solver reaching its
targets does not prove a comfortable pose: inspect forward torso lean, shoulder
position and elbow bend across supported characters. When several characters
strain toward the same wheel, revise the shared seat and wheel packaging and
update both modeled grips and runtime contact targets together. Keep the steering
column connected to its lower attachment when moving the rim.

For an awkward arm pose, compare neutral and both steering extremes before
changing the cockpit. Inspect wrists, elbows and forearm/knee clearance through
the actual seat or sway solver; do not assume an elbow-pole angle has the same
visual direction on every rig. Keep the wheel hub and rotation axis independent
of hand targets. Moving grips around the rim must preserve its radius and plane
without relocating the hub. Hold accepted seat, pedal and figure dimensions fixed
while testing a bounded grip or elbow adjustment, then check supported characters
and the exported runtime poses. Report interpolation error separately from visual
comfort and collision clearance; a smooth pose stream does not prove either.

Batch comparable variants with an unchanged control; inspect every produced
result, including rejected candidates. Retain only improvements that survive the
relevant close-up and an overall or opposite view. A cleaner hero silhouette can
hide a pinched top outline or tire intrusion.

If the same silhouette or continuity complaint survives two local corrections,
stop stacking local fixes and reassess the construction before a third. Identify
the inherited section, boundary or packaging assumption that prevents the target
shape and rebuild the smallest connected assembly that tests a different
construction. For a continuous sweep across adjoining patches, prefer one
low-control surface or explicitly compatible boundary slopes; include the full
visible transition rather than ending the edit inside it. Carry boundary movement
into mating walls while preserving functional openings and UV seams. Do not
freeze an arbitrary old seam merely because earlier edits preserved it. Passing
topology and clearance checks does not overturn a visual rejection; keep that
candidate labeled as rejected and continue from a justified baseline.

## Verify and record the checkpoint

### Use review sheets throughout iteration

Make a compact labeled contact sheet part of the modeling loop, starting at
blockout. For a local edit, reuse a fixed three- or four-view set: the affected
close-up, an orthographic profile, an opposite or adjoining view, and actual
control edges when topology matters. Compare the accepted baseline and candidate
with identical cameras, framing, lighting and material treatment. Inspect every
tile and open full-resolution crops when the sheet cannot resolve a seam or
highlight defect; use those findings to choose the next edit before retaining the
candidate.

After major silhouette or assembly changes, and before a full-model review,
expand to roughly 8-12 relevant views: front and rear three-quarter, front, rear,
both sides, top, and detail views of the changed interfaces. For vehicles,
include cockpit and figure fit, low aero or underbody, and a sparse control-cage
view where useful. Render the actual retained mesh with neutral or simple
material blocks. Label orientation, source checkpoint, authoring versus runtime
renderer, and any differing view scales; do not imply that independently framed
views are dimensionally comparable.

Keep this cheap: batch views in one reusable script with saved camera presets,
use fast authoring renders, inspect one assembled sheet first, and rerender only
changed views during local work. Do not regenerate a full sheet or launch an
engine build after every vertex edit. Preserve the source snapshot or revision,
individual images and render settings; provide a readable preview and
full-resolution sheet, with PDF when useful. A review sheet complements the
required intersection, export and runtime checks; it does not replace them.

For an asset intended for a runtime, periodically render a usable checkpoint
through the actual target engine as well as the authoring tool. Check after major
silhouette or proportion changes, when export and material translation is
uncertain, and before handoff; every small mesh edit need not trigger an engine
build. Use the normal in-application camera and representative environment
lighting, with a closer inspection view when useful. Keep the export isolated
from shipped catalogs and assets until integration is requested. Record temporary
scale, wheel and figure setup, and material approximations so a preview does not
imply animation or production readiness.

Check evaluated geometry where modifiers affect the result: tire/body
intersections, panel gaps, visible overlap, normals and the protected interfaces
touched by the edit. A static mannequin and clearance test prove only that pose;
animation, steering sweep, comfort and runtime export need their own checks when
in scope. Geometry tests do not establish visual fidelity.

For every panel-shape iteration, automatically check the changed pieces against
their named neighbors before rendering or retaining the checkpoint. Use evaluated
meshes with the actual modifier stack in a common world coordinate system (for
example, triangle BVHs in Blender), including mirrored sides. Report intersecting
triangle pairs and their locations, and compare with the pre-edit control. Mesh
manifoldness and successful export do not establish clearance between separate
objects. Classify intentional joins or hidden underlaps explicitly; do not
silently exempt an entire neighbor pair or move the protected neighbor to clear a
bad fit.

Also check near-contact at the affected seam using a stated tolerance in model
units. Report sampling coverage and distinguish sampled nearest-surface distances
from a certified minimum; sparse vertex samples can miss edge/face proximity.
Triangle crossings alone can miss containment, coplanar overlap, and a visually
doubled border. Use suitable additional tests for those cases and retain close-up
side or oblique and cage inspection. Unexpected intersections or inadequate seam
clearance must be corrected or reported as unresolved, never described as passing
because individual meshes are valid.

Before an expensive full render matrix, export and reimport a cheap geometry
checkpoint and check the named interfaces affected by the edit. Expand those
checks when broader cover ends or new inner panels introduce new neighbors.
Inspect neutral close-ups plus an overall or opposite view before retaining the
change; do not spend another full matrix reproducing an already detected overlap.
Preserve a pre-edit capture for identical-camera before/after comparisons.

Save the retained source, reproduction script and settings, inspected renders and
concise rejected-variant notes. Record the exact next discrepancy and where the
source can be resumed. Keep in-flight task state wherever the project tracks it
(an issue or pull request for shared repository work); keep reusable domain
lessons in the project's documentation, not in an agent-private memory store.

If the user requests an image series, preserve checkpoints and label before/after
views honestly. Report hands-on time only when tracked; exclude pauses and
distinguish render and queue time. Otherwise mark the checkpoint untimed. Do not
invent a percentage match from an impression or substitute passing mesh checks
for the user's visual target.

After geometry is accepted for the task, proceed to the separately scoped surface
pass: final livery colors, decals and text, then scuffs and weathering, with UV,
bake and export checks as needed. Standalone source completion does not imply
runtime integration or production readiness.

If a continuous painted band fragments at a fused seam, inspect the UV domains
before changing geometry or adding decal meshes. Use one continuous surface
coordinate system across the joined shell and reserve enough atlas resolution for
oblique edges. Keep dark inner-return faces distinct from painted outer lips.
Recheck the exported texture at normal viewing size; a material fix does not
repair a jagged silhouette.
