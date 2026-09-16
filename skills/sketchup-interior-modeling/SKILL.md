---
name: sketchup-interior-modeling
description: Create or revise editable SketchUp models of rooms, homes, apartments, furniture, cabinetry, wall panels, and interior accessories from dimensions, drawings, or references. Use for actual 3D geometry and SketchUp authoring scripts; not raster-only rendering or native Revit family authoring.
---

# SketchUp interior modeling

Produce dimensionally grounded, editable SketchUp geometry at the detail level
needed for the user's design task. Preserve supplied layouts, chosen products,
and approved geometry. Match the requested scope: a single object does not
require a room, and a room does not require a whole building.

## Establish the brief and execution path

Read the retained model and project instructions before changing geometry.
Identify the source revision, requested changes, protected objects, target
SketchUp version, units, and expected deliverables. Use known information first;
ask only for missing facts that materially affect the result.

For ambiguous references or uncalibrated plans, use the companion
`prepare-3d-reference` skill when available. Otherwise establish the same minimum
brief here: authoritative dimensions, reference priority, required views,
component inventory, and clearly labeled assumptions. Preparation need not
delay an adequately specified blockout.

Treat dimensions in supplied drawings or specifications as controlling over
apparent proportions in photographs. Clarify consequential contradictions.
Distinguish finished-face measurements from structural dimensions and record
the datum. Never silently resize an approved room or product to make a layout fit.

Check what authoring tools are actually callable:
- Prefer native SketchUp desktop geometry and components through an available
  connection or Ruby API workflow.
- Read [SketchUp authoring](references/sketchup-authoring.md) when writing Ruby,
  changing nested components, or saving model output.
- If SketchUp execution is unavailable, prepare a scoped Ruby script and concise
  run instructions where useful. Label it unexecuted; ask for execution access
  or the resulting model for verification. Do not claim an SKP exists.
- Do not assume SketchUp for Web supports desktop Ruby, that ordinary Ruby
  provides the SketchUp API, or that this skill installs an application connector.
- Respect a requested alternative authoring tool. Explain the handoff implications
  using [delivery and interoperability](references/delivery.md).

## Choose construction appropriate to the task

Read only the relevant section of
[interior construction](references/interior-construction.md):
- **Spaces:** rooms, apartments, homes, and architectural shells from plans,
  elevations, and measured openings.
- **Furniture and joinery:** separate editable parts with meaningful dimensions
  and attachment relationships.
- **Panels and trim:** profiles, module spacing, corner returns, and opening edges.
- **Accessories and curved objects:** suitable profiles and surface resolution
  without excessive geometry.

Set an explicit level of detail: space-planning blockout, presentation model,
or detailed assembly. Do not model hidden hardware for a distant room view.
Do not describe a visual model as fabrication-ready without the construction
information and checks that claim requires.

## Preserve SketchUp editability

Organize geometry by things a designer needs to move, hide, replace, or revise.
Keep walls, floors, ceilings, doors/windows, and furnishings separate where
useful; use stable names rather than one undifferentiated mesh.

Use components for repeated items, with meaningful insertion points and local
axes. Reuse definitions only when instances should update together. Make the
necessary instance and shared parent definitions unique before a one-off edit;
do not accidentally alter every cabinet or apartment.

Keep raw edges and faces Untagged; assign visibility tags to containing groups
or component instances. Match an existing project's organization. Tags do not
isolate geometry; groups and components do.

Model thickness where visible or needed for sections and contact. Check face
orientation in monochrome mode. Avoid duplicate coplanar faces, stray edges,
and tiny details that add weight without improving the requested view. Require
closed solids for parts intended to be solid, not every curtain or open shell.

Use physical material scale and grain direction. Apply materials so adjacent
finishes remain independently editable. Retain important supplied textures and
artwork without inventing replacements or distorting their proportions.

## Build and review in useful increments

Start with the controlling envelope, openings, and largest objects. Check
dimensions, orientation, and furniture relationships before detailed geometry.
A plausible perspective image is not proof of correct layout.

For a revision, retain a baseline and work on the smallest relevant assembly.
Keep cameras and material treatment consistent for before/after comparisons.
Inspect a plan or elevation plus an opposite/oblique view when a perspective
hides depth, intersections, or a changed outline.

Use simple materials for geometry review, then refine approved finishes.
For scoped material-only edits, preserve geometry and cameras. For complete
modeling tasks, proceed through required finish work within existing authorization;
do not introduce a separate approval gate unless a material design choice remains.

Check actual contact as well as collisions: cabinets should meet their intended
walls and supports; furniture should sit on its intended floor. Test requested
door and drawer movement against nearby items. Use supplied clearance criteria;
record any provisional design assumptions instead of claiming code compliance.

If repeated local fixes fail, revisit the profile, component boundary, or
dimensional assumption. Keep rejected variants distinct from the retained model.

## Verify the deliverable

Scale verification to the change:
- Measure controlling dimensions in the appropriate local and world contexts;
  account for nested transforms, rotation, and mirroring. Compare with the brief
  using a stated tolerance appropriate to the task.
- Inspect openings, surface direction, intended solid parts, contact, and the
  changed objects' neighbors. Bounding-box overlap is only a screening check,
  not proof of a geometric collision; sparse samples do not certify clearance.
- Inspect actual SketchUp views: a useful overall view, plan/elevations for
  dimensions and orientation, and close-ups or sections of changed interfaces.
  Save scenes when they help ongoing design work; no fixed view count is required.
- For an SKP handoff, save and reopen the retained file when execution is
  available. Check dimensions, component organization, materials, and key views.
  Test exported files in their target application only when that delivery is in
  scope; otherwise mark that compatibility unverified.

Read [delivery and interoperability](references/delivery.md) before final handoff.
Report the actual files, what was checked, and unresolved assumptions. Distinguish
a prepared script, an executed model, a reopened SKP, and a tested target import.
Raster image generation can illustrate an idea; it cannot prove a geometry edit.
