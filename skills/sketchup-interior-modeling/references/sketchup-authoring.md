# Native SketchUp authoring

Use these rules when generating Ruby or editing through a SketchUp connection.
Consult the installed version's API for version-sensitive methods. These are
authoring conventions, not a bundled connector or a tested model generator.

## Execution and units

SketchUp Ruby runs inside supported SketchUp desktop installations. A standalone
Ruby interpreter can check syntax but cannot validate SketchUp API behavior.

Use explicit units on numeric dimensions, for example `600.mm`, `2.4.m`, or
`24.inch`, and convert once at the input boundary. SketchUp stores lengths
internally in inches; display-unit settings do not convert raw numeric literals.
Retain numeric lengths for calculations rather than parsing formatted UI labels.

Validate positive dimensions and viable thickness/opening relationships before
creating geometry. Keep adjustable dimensions together in a parameter structure.
Record estimated inputs and do not present input parameters alone as measured
output.

## Context, components, and edits

- Establish the intended model and edit context before mutation. Root
  `model.entities` and `model.active_entities` are different when editing a
  nested instance. Do not insert world-coordinate geometry into a nested context
  without the correct transform.
- Create new geometry in a named task-owned group or definition. Namespace Ruby
  code to avoid collisions with installed extensions. Do not clear the active
  model to make a script reproducible.
- Prefer faces, extrusions, and components for straightforward construction.
  Verify extrusion direction from the face normal and inspect face orientation.
- Reuse component definitions deliberately. When changing only one occurrence,
  make shared definitions unique along the affected nesting path before editing.
  Inspect other instances to verify the intended scope.
- Measure local construction dimensions separately from transformed placement.
  A world-axis-aligned bounding box of a rotated cabinet is not its true local
  width/depth. Include parent transforms in world contact and fit checks.
- Keep raw geometry on Untagged (the default API layer); place tags on groups or
  instances. Preserve the user's active tag and restore any temporary UI state.
- For generated content, use a stable task-specific attribute identifier or
  tracked entity mapping. A rerun should update only its own assembly or create
  a clearly named new candidate. Never delete by a broad name match.

## Transactions and output

Wrap a coherent model change in a named, non-transparent undo operation. Commit
on success; abort that operation on an exception and surface the error. Avoid
nested operations and avoid catching an error only to return apparent success.
A model undo operation does not undo files written on disk.

Check optional API availability in the actual version. Do not assume newer solid
inspection, export, or scene APIs exist. When unavailable, use an applicable
alternative and report its coverage. Successful face creation is not a complete
manifoldness or collision check.

Save the requested output through supported SketchUp save methods and inspect
the result. Use a new path for a candidate unless replacing the original is
authorized. Do not silently discard unsaved user work to reopen a file for QA.
Do not merely rename a mesh export with an `.skp` extension.

When execution is unavailable, supply a self-contained `.rb` file with input
dimensions and a specific SketchUp desktop invocation. State it has not been
executed. Avoid instructions that require installing unrelated packages or
running application code in an ordinary system Ruby console.

## Official references

- [Geometry creation](https://ruby.sketchup.com/file.generating_geometry.html)
- [Length and units](https://ruby.sketchup.com/Length.html)
- [Model context, transactions, and saving](https://ruby.sketchup.com/Sketchup/Model.html)
- [Component instances and uniqueness](https://ruby.sketchup.com/Sketchup/ComponentInstance.html)
- [Tags and visibility](https://help.sketchup.com/en/sketchup/controlling-visibility-tags)
