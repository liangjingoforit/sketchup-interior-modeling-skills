# SketchUp interior modeling skills

Dimension-first agent skills for interior designers creating editable SketchUp
models: rooms, apartments, homes, furniture, cabinetry, wall panels, and decor.

| Skill | Purpose |
| --- | --- |
| [sketchup-interior-modeling](skills/sketchup-interior-modeling/SKILL.md) | Build and revise native SketchUp geometry with useful components, physical dimensions, materials, and model verification. |
| [prepare-3d-reference](skills/prepare-3d-reference/SKILL.md) | Resolve dimensions and construction from plans, elevations, specifications, and photos before modeling. |

## What is included

The main skill routes to focused references for architectural spaces, furniture
and joinery, panel systems, curved objects, SketchUp Ruby authoring, and delivery.
The preparation skill is useful when sources need interpretation; the main skill
can start directly from a sufficiently specified brief.

The workflow prioritizes:
- Supplied dimensions and approved layouts over guessed image proportions.
- Editable groups and reusable components, with raw geometry kept Untagged.
- Actual wall openings, panel thickness, joinery parts, and intentional contact.
- Correct material scale, grain direction, and proportionate model detail.
- Inspection of actual geometry and a saved/reopened SKP when SketchUp is available.
- Clear separation between a prepared script and a verified model.

## Requirements and limits

This repository contains instructions and supporting references. It does not
include a SketchUp connector, model generator, or example SKP files.

To execute native Ruby authoring, the agent needs access to a supported SketchUp
desktop session and a way to run code there. Desktop Ruby is not assumed available
in SketchUp for Web. Without execution access, the skill can guide preparation
of a Ruby script, but must label it unexecuted and the model unverified.

Revit and Rhino handoffs are optional. Imported geometry is not automatically a
native Revit family or clean Rhino NURBS model. Native authoring workflows for
those applications are outside this skill's primary scope.

## Install or update

Copy the two complete folders under `skills/` into the skill directory supported
by your agent host. Include their `references/` and `agents/` subfolders where
present. The repository retains its Claude plugin manifest and includes optional
OpenAI UI metadata in each skill folder.

Version 0.2 replaces `match-3d-reference` with `sketchup-interior-modeling`.
When updating an existing installation, replace the old installed
`match-3d-reference` folder with the new folder and refresh
`prepare-3d-reference`; update any explicit invocations of the old name.
Updating this repository does not update an already installed copy automatically.

## Example requests

- "Build this measured apartment plan in SketchUp; keep walls, ceilings, and furniture separately editable."
- "Create a 2400 mm cabinet from this elevation, with separate doors, shelves, and countertop."
- "Add a fluted wall panel system within these dimensions, keeping the module width and gaps fixed."
- "Model this lamp from its product dimensions and reference photos."
- "Change only this cabinet's depth and preserve the room layout and the other cabinet instances."

## Provenance

Adapted from the reference-led modeling skills in
[jwang47/3d-modelling-skills](https://github.com/jwang47/3d-modelling-skills).
The original comparison and verification discipline is retained; vehicle and
game-rig procedures have been replaced with SketchUp interior-design workflows.
The original MIT license is retained.
