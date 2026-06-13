# QuadRemesher 1.3 Blender Bridge — Blender 5.0–5.2 Compatibility Patch

This is a small compatibility update of the official **QuadRemesher 1.3 Blender Bridge**
(originally developed by Maxime Rouca / Exoside, GPL-licensed) so it can be
registered and loaded correctly in **Blender 5.0, 5.1, and 5.2**.

## What changed
- `__init__.py`: the unused imports `rna_keymap_ui` and `bl_operators.presets`
  are now wrapped in `try/except`, so the add-on does not fail to load if
  these internal Blender modules change in 5.x.
- Bumped the internal add-on version to `1.3.1` to mark this build.
- Core logic (FBX export/import, the remeshing engine launcher, UI panel,
  Face Sets → Materials for Blender 4/5) was left unchanged — it relies on
  stable APIs that are still valid in Blender 5.0–5.2.

## Installation (Blender 5.0–5.2)
Blender 5.x still supports old-style ("legacy") add-ons:

1. `Edit > Preferences > Add-ons`
2. Click the small ▾ arrow next to **Install** → **Install Legacy Add-on...**
3. Select `quad_remesher_1_3_addon_Blender5.zip`
4. Enable **Quad Remesher 1.3 Bridge**

## QuadRemesher Engine
This add-on requires the **QuadRemesher Engine** (the actual remeshing
algorithm), which is a separate closed-source component owned by Exoside
and is **not included in this repository**.

- The add-on will **automatically download and install** the engine the
  first time you click "Remesh It" in Blender (requires an internet
  connection).
- Alternatively, you can get it manually from the official source:
  https://exoside.com/quadremesher/

You will also need a QuadRemesher license (trial or paid) from Exoside to
use the remeshing functionality.

## Requirements
- Blender's built-in **FBX Import/Export** add-on must be enabled, as this
  bridge uses FBX to exchange meshes with the engine.

## Credits / License
- Original add-on: © Maxime Rouca / Exoside — https://exoside.com/quadremesher/
- Licensed under GPL v2 (or later), see license headers in the source files.
- This repository only contains a small compatibility patch on top of the
  original GPL-licensed code; it is **not** an official Exoside release.
  Please check Exoside's website for the latest official version.

## Disclaimer
This is an unofficial, community-made compatibility patch, provided "as
is" with no warranty. Use at your own risk.
