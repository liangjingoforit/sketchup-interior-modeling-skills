# Interior construction decisions

Read the section relevant to the requested geometry.

## Spaces: rooms, apartments, homes, and building shells

- Establish a local origin and floor datum. Preserve an existing coordinate
  system; for imported survey geometry, record any working offset rather than
  silently moving georeferenced or coordinated source data.
- Calibrate reference drawings and keep them separate from authored geometry.
  Build from explicit coordinates and dimensions where possible. Trace a raster
  only at justified precision; do not silently square irregular existing walls.
- Distinguish structural and finish faces, floor-to-floor and clear heights, and
  rough versus finished opening sizes. Build thickness and reveals that matter
  to the requested model.
- Model openings as geometry through the relevant wall assembly. A dark rectangle
  on a wall is not a door opening. Check both sides and the wall returns.
- Separate stories, floors, ceilings, and major wall assemblies so designers can
  inspect interiors. Organize repeated apartments as components only if their
  repeated design should remain linked.
- Place fixed cabinetry and main furniture before accessories. Verify orientation,
  sightlines, intended circulation, and specified door swings in plan. A camera
  chosen for presentation must not conceal a layout mismatch.
- For stairs, roofs, or complex envelopes, obtain the controlling section and
  level information needed for the task. Clearly label conceptual geometry;
  visual plausibility does not establish building or structural compliance.

## Furniture and joinery

- Build in local width/depth/height coordinates with a meaningful placement
  origin, usually a floor contact or installation corner. Separate the placement
  transform from the construction dimensions.
- Use an assembly containing editable carcass, doors/drawers, shelves, countertop,
  legs/plinth, and handles as appropriate. Avoid fusing independently revised
  materials or moving parts into one mesh.
- Derive internal clear dimensions from overall dimensions and material
  thicknesses. Preserve those thicknesses when changing width or height;
  nonuniform scaling of a complete cabinet can distort doors and hardware.
- Make repeated identical panels or handles components. Use a unique definition
  for genuinely different sizes or variants. Ordinary components are not
  automatically parametric; expose dimensions in a generator when repeatable
  resizing is part of the task.
- Represent specified reveals, overhangs, toe kicks, and supports. Use manufacturer
  dimensions for exact appliances or fittings. Do not invent hardware clearances
  and call them installation-ready.
- Check door/drawer movement envelopes when relevant, including handles and nearby
  walls or furniture. Test feet, plinth, and wall contact.
- Model cushion envelopes and useful seams at presentation resolution. Smooth
  shading does not repair an incorrect curved silhouette. Use a dedicated surface
  workflow for complex upholstery only when the task warrants it; preserve the
  user's tool preference and label approximation.

## Panels, moldings, screens, and trim

- Define installation bounds, backing, thickness, profile, module width, gaps,
  and edge treatment before creating arrays.
- For n equal panels of width w separated by gap g, the occupied run is
  n*w + (n-1)*g. Add explicit end margins; do not silently stretch profiles to
  consume a leftover strip. Resolve remainder with the specified centered,
  trimmed, or fixed-module layout.
- Distinguish clear spacing from center-to-center pitch. For slats, state which
  value the input represents and derive the other from the slat width.
- Handle corners, returns, skirtings, sockets, doors, and other interruptions.
  Keep cut modules unique while preserving the common full-module definition.
- Use a true swept/extruded profile where depth affects silhouette, light, or
  section. Use a material for distant fine detail where actual relief is not
  needed. Curved runs require a local frame along the path, not only translation
  of a straight array.
- Check seam alignment, terminal pieces, backing contact, and grain direction
  from plan/elevation and an oblique close-up.

## Accessories and curved objects

- Choose construction from the shape: revolved profiles for vessels, sweeps for
  frames/tubes, extrusions for planar objects, and controlled surfaces for
  freeform pieces. Do not force every object into boxes or a dense imported mesh.
- Set curve segmentation by visible curvature, object size, and final view.
  Inspect silhouettes and edge flow before increasing density.
- Model lips, thickness, bases, recesses, and openings visible in the intended
  view. A decorative vessel can be a closed solid including its inner wall;
  an intentionally open surface need not pass a solid test.
- Distinguish softened/smoothed display edges from geometric continuity. Inspect
  monochrome and hidden-geometry views for reversed faces or unintended folds.
- If tiny features fail at SketchUp's modeling tolerance, use a documented
  temporary construction scale for the isolated object and restore its true
  dimensions. Never rescale the entire user scene to hide failures.
- Keep a lighter component for repeated placement when a highly detailed source
  would make a room model cumbersome. Preserve the detailed original separately
  when it is part of the requested deliverable.
