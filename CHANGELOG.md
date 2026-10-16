# Changes

What is new in each version of vEditor. Downloads are on the [releases page](https://github.com/vEditor-cmyk/vEditor/releases);
vEditor tells you when a newer version is out (*Help → Check for Updates* looks at once).

## 1.1.0 — 2026-10-16

Maps and interiors, edited where they are — see the [README](README.md#world-and-map-editor).

- **Interiors (MLO) edited inside** — the doors, furniture and walls of an interior are in its `.ytyp`, not in the
  ymap. *Edit Interior (ytyp)…* (on an interior picked in a map, or on any object of one clicked in the World) opens
  it in the World: move, turn, delete, copy or place its entities with the gizmo, listed by room — doors are most
  often on the portals. *Save* writes the `.ytyp` in place, by CodeWalker's rules for an interior's lists.
- **`.ytyp` files** — double-click one: its archetypes, and an interior's rooms, portals, entity sets and timecycle
  modifiers with every entity in them; what you pick is a form in the Details panel (names, distances, flags as
  named boxes, a time archetype's hours, an entity's place, turn, room …). Delete, copy, add an entity to a room,
  undo.
- **Map Files** in the World's Details panel — open a map and everything its resource is made of is beside the
  selection: its ymaps (with how many objects each holds), its `.ytyp` files edited right there, its collision,
  models and textures. Double-click an interior or a door to edit it in the World, a ymap to list its objects.
- **The objects of a map, by ymap** — the Outliner lists a map's objects by the ymap they are kept in (or an
  interior's by room), sorts them, and its right-click menu goes to, moves, turns, scales, drops, copies or deletes
  them.
- **Code (XML)** — right-click a `.ymap`, `.ytyp`, `.ymt` … → *Edit Code (XML)*: CodeWalker's XML of the file in a
  tab, to read and change; *Save* turns it back into the file (a mistake is shown at its line, nothing is written).
- **Collision viewer** — double-click a `.ybn`: its collision in 3D by material or by part, materials and parts to
  hide, *Show in World*.
- **Props and your game build** — the prop list leaves out (or marks) props that came with a game build newer than
  your server's (`sv_enforceGameBuild`, or the build chosen under *Map ▾*); placing one or saving a map with one
  tells you that players on that build will not see it.
- **Make a Model of This Size…** — the game draws an interior's entity at its model's own size, whatever scale it is
  given. This makes a copy of the model at the size you set — its collision too — adds it to the `.ytyp` and gives
  the entity that model.
- **Reload Map** — right-click a resource: its files read again from the disk and shown as they are now, without
  loading the whole world again. The folders of the path above the Content Browser's list have the same right-click
  menu as the folders themselves.
- Every file these tools write keeps a copy of itself as it came, the first time, in the resource's
  `.veditor_backup` folder (not streamed to players).
- Not tried in game by vEditor itself: the files were read back by CodeWalker's library.

## 1.0.0 — 2026-10-15

The first version published here. What it has — see the [README](README.md#tools) for each tool:

- **Content Browser and RPF Explorer** — the game's archives, your server's resources and your own folders in one
  place; files read from the game directly, edited in archives and on disk.
- **XML, as CodeWalker makes it** — Export / Import XML for every type CodeWalker handles, through the CodeWalker
  installed on your computer.
- **Textures** — `.ytd` and the textures embedded in `.ydr` / `.yft`: import, replace, export, optimize, batch
  conversion of whole folders, models saved smaller.
- **Image Editor** — a Photoshop-like editor with layers, layer styles, filters and AI on a selection.
- **Models** — a model viewer with Blender-style controls, bones you can hide, vehicles with their liveries, UV
  pages for any texture.
- **World and Map Editor** — the game's map with your server's resources (only those `server.cfg` starts), new
  ymaps, your server's maps edited in place, interiors moved as a whole.
- **Traffic paths and walkways** — the roads the traffic drives on (`.ynd`) drawn and edited, sidewalks painted on
  the navmesh, saved as a resource.
- **Timecycle Editor** — the game's light, sky and fog for every weather and time, exported as a FiveM resource
  or sent to a running game.
- **Animations** — Animation Library (play, edit, import `.fbx` / `.bvh`, replace), Animation Capture, Attach Prop.
- **Cloth Tool** — clothing packs with their in-game numbers, edited in place; clothes taken from the game;
  tattoos.
- **Weapon Tool** — add-on weapons from any game weapon, saved as a ready resource.
- **Vehicle Tool** — sirens on any vehicle, siren sets, mods and upgrades, liveries and livery mods.
- **Scaleform (GFx) viewer**.
- **AI (optional)** — textures, tattoos, parts of pictures and animations, with the AI model you choose.
- **Update check** — tells you when a newer version is out; nothing is downloaded or installed by itself.
