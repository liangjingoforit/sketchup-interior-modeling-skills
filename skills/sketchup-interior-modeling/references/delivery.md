# Delivery and interoperability

## SketchUp handoff

Prefer the retained editable SKP when SketchUp is the target and saving has been
executed. Include supporting scripts or textures when needed to reproduce or use
it. Keep supplied assets linked or packaged as appropriate to the actual workflow.

For ordinary model delivery, report:
- Output path and actual authoring/target version.
- Controlling dimensions checked, with tolerance and unresolved estimates.
- Useful organization, scenes, and any intentionally simplified geometry.
- Whether the file was saved, reopened, and visually inspected.

For a script-only handoff, give its path, editable input parameters, and how to
run it in the supported SketchUp desktop version. State which checks remain
pending. Do not imply that the script is itself a native SKP.

A neutral geometry preview should precede a claim about shape accuracy. Rendered
images may supplement the model, but neither an AI image nor an attractive
render proves the retained source matches the measurements.

## Revit, only when requested

Clarify whether the user needs a visual reference object, a categorized imported
shape, or a native parameter-driven family/building model. These are different
deliverables. Do not automatically add a Revit workflow to a SketchUp task.

A SketchUp or other shape import does not automatically reconstruct native walls,
doors, constraints, or family parameters. Assigning a category alone does not
provide that behavior. Native Revit deliverables need a separate authoring path.

Choose a supported exchange format for the actual installed versions and test
units, orientation, geometry, materials, category behavior, and relevant section
appearance. If Revit is unavailable, label the import unverified instead of
claiming compatibility from the file extension.

## Rhino, only when requested

Clarify whether a mesh reference is sufficient or the user needs editable curves,
NURBS, solids, or SubD. Converting a polygon mesh to NURBS does not recover the
original smooth design surfaces; it can create one surface per polygon.

Preserve a suitable curved source when Rhino is used for a complex object and
check the tessellated SketchUp handoff separately. Do not introduce Rhino as a
mandatory dependency for ordinary SketchUp rooms or cabinets.

## Exchange checks

Use the actual application's supported import/export options, version, and
license. Keep the editable source and export a copy where conversion loses
structure. Verify a known dimension after import, plus material scale, axes,
component separation, and the affected details. Never promise a universal
lossless conversion or rename a file to imply a different format.

Official references:
- [SketchUp exchange formats](https://help.sketchup.com/en/sketchup/using-sketchup-data-other-modeling-programs-or-tools)
- [Revit imported shape behavior](https://help.autodesk.com/cloudhelp/2026/ENU/Revit-Model/files/GUID-AD4862C9-F714-4FF0-8C7F-351BB679D0C2.htm)
- [Rhino mesh-to-NURBS conversion](https://docs.mcneel.com/rhino/8/help/en-us/commands/meshtonurb.htm)
