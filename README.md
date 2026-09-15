# 3D modelling skills

Two agent skills for reference-led 3D modeling, in any host that reads Claude
skills. They are tool-agnostic in wording but written from Blender practice.

| Skill | Use it for |
| --- | --- |
| [`prepare-3d-reference`](skills/prepare-3d-reference/SKILL.md) | Turning a pile of concept images into a modeling brief: view coverage, component construction, scale anchors, and the choices still unresolved. Run it before modeling, or when a missing view blocks it. |
| [`match-3d-reference`](skills/match-3d-reference/SKILL.md) | Building and iteratively refining the mesh against those references: component comparison, control-cage construction, intersection and seam checks, review sheets, and honest checkpoints. |

`match-3d-reference` hands back to `prepare-3d-reference` when the references
contradict each other or a needed view is missing, so install both.

## What they enforce

- **Geometry before decoration.** Decals, lettering, final livery colors and
  weathering wait until the silhouette is accepted, so a texture cannot disguise
  a bad shape.
- **Fixed cameras.** Baseline and candidate are compared under identical framing,
  lighting and material treatment; camera and geometry never move together.
- **Sparse control cages.** Broad curvature is resolved on a deliberately laid
  out low-control surface before density is added. Decimating a scan is not a
  substitute for designing topology.
- **Fit as a blockout decision.** For anything carrying a figure, the real rig at
  its real scale is seated before the cockpit is detailed — never a mannequin,
  never by shrinking the character.
- **Mechanical checks, not vibes.** Evaluated-mesh intersection tests against
  named neighbors, stated seam tolerances, and export/reimport checkpoints, with
  their coverage reported rather than implied.
- **Honest checkpoints.** Rejected variants stay labeled rejected; passing mesh
  checks never stand in for the user's visual target.

## Install

Pick whichever your host supports.

Copy the skills into your personal skills directory:

```bash
cp -r skills/* ~/.claude/skills/
```

Or into a single project:

```bash
cp -r skills/* .claude/skills/
```

Or add this repository as a plugin marketplace entry — it carries a
`.claude-plugin/plugin.json` and exposes both skills under `skills/`.

## Adapting them to a project

The skills defer to the project rather than hard-coding one. Where they say "the
project's own visual-verification and measurement procedures", "a documented
dimension contract", or "the target application's actual character asset", point
those at your own docs, contracts and pipeline — either by editing the SKILL.md
or by keeping that detail in the project's own always-on instructions.

## Provenance

Extracted from a game repository's internal agent skills and generalized: the
repository-specific handbook paths, dimension contracts, pull-request case
histories and sibling skill names were replaced with project-neutral wording. The
substance — the iteration discipline and the failure modes it exists to prevent —
is unchanged.
