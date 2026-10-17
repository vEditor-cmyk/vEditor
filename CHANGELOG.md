# Changes

What is new in each version of vEditor. Downloads are on the [releases page](https://github.com/vEditor-cmyk/vEditor/releases);
vEditor tells you when a newer version is out (*Help → Check for Updates* looks at once).

## 1.2.0 — 2026-10-17

Weapon skins — see the [README](README.md#weapon-tool) and the [video](README.md#showcase).

- **Add Skin** (Weapon Tool → *Components*, or *Add Weapon ▾ → Skin for a Game Weapon…*) — a finish made the way
  the game makes its own (the Pistol .50's Platinum Pearl Deluxe): while it is on, the weapon and the clips,
  suppressors, flashlights and scopes you tick show copies of their models with textures of their own. No polygons
  added, no new weapon: the skin is one of the weapon's components.
- **A pattern, a colour, or a skin pack's texture as it is** — a picture repeated over the weapon or laid once over
  each side, keeping as much of the weapon's own shading as you like; or a texture made for the weapon put in
  unchanged (a `.dds` keeps its own data; several files at once, each on the texture it is named after).
- **Every texture its own choice** — the skin's, a file of yours (a clip can have its own), or unchanged; a 3D
  preview, the texture flat with its UV lines, *Save UV Layout…*.
- **Edit Skin** shows the skin as it is — its textures, kept unless you change one, and the choices it was made with
  (saved in the resource's `.veditor` folder).
- **Folders** — each skin's files in `stream/skin01`, `skin02` …, the weapon's own in `stream/default`.
- **One set of skins for several weapons** — select components (Ctrl / Shift), *Copy* / *Paste* them on another
  weapon or *Copy to Weapons…*: weapons of the same model wear the same skins, nothing is copied on disk.
  *Add Components…* lists the resource's own components beside the game's and takes several at once.
- **Ten skins to an attach point** — seen in game: from the 11th skin of one attach point on, the gun changed but
  its clip and suppressor did not. More skins go on further `gun_root` points; saving a resource that has more on
  one point lays them out again.
- **Attach points that share a bone stay apart** — saving a weapon used to merge them into one (the game's AP pistol
  has two on `gun_root`).
- **Textures the game can load** — Direct3D 11 refuses a compressed texture whose sides are not multiples of 4 (a
  2844 texture halved to 1422 — in game the model flickers). Optimize, imports and the Weapon Tool now put every
  compressed texture on the 4-pixel grid (1422 → 1424); the Weapon Tool's check marks such textures in a resource.
- **`.ytd` files in smaller pieces of memory** — textures packed into pages the way CodeWalker packs them, instead of
  one block rounded up to the next power of two (a 11 MB skin dictionary went from one 16 MiB piece to 10–12 MiB).
- **Weapon Tool check** — also marks more than ten skins on one attach point, and a component another resource
  defines (that resource has to start first).
- **Test command** — `/give_<resource> COMPONENT_…` gives you the skin's weapon with that skin on; `INSTALL.md` lists
  the skins with their files.
- Skins made with this version were seen in game on one server (a Kriss Vector, a Combat Pistol); the files were
  also read back by CodeWalker's library.

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
