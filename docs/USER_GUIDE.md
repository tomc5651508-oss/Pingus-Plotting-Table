# Pingu's Plotting Table: A Mapper's Toolkit: user guide

*Dedicated to Pat Wilson's legacy.*

Lift a real place onto an existing IL-2 Great Battles map. Pick a **starting map** (every map in your install is
listed), drag its true-size extent over the place you want on an OpenStreetMap map, set a few options, place airfield
strips and press **Lift off**: the Jungle Hawks terrain pipeline bakes the real heights, coast, sea floor, rivers,
trees and airfields onto that map and stages a **JSGME pack** that hot-swaps the terrain.

**What ships today:** terrain, coast, rivers, trees, airfield strips, the in-game map, the starting map's towns and bridges swapped for
buildings at the real places, quick missions, and the **dynamic campaign**: the career and Advanced Quick Missions fly from the same strips the terrain baked, with your
squadrons, fronts and map art. PWCG flies from them too: the pack goes over your PWCG folder while it's enabled. Roads, railways and bridges come from OpenStreetMap: every class down to suburban streets, wider classes drawn wider, a bridge on every crossing, stations on the line. Buildings stand along those streets at the setback, facing and spacing measured from the pack's stock map. Broad rivers and lakes take their real outline from OpenStreetMap.

**Nothing from the game ships with the tool.** It finds your install (Steam, the Windows install list, the usual folders; or paste the folder), reads what it needs into
`%LOCALAPPDATA%\LocationLiftoff`.

**OpenStreetMap comes from files, not servers.** The box's regions download once from Geofabrik (resumed, checksum-checked) and stay on disk, so the same box gives the
same map on every build, offline too. A build that can't get them stops and says why. Sizes: Malta's box 723 MB, Moscow 885 MB, the Rheinland box 5 GB.

**Layout:** a toolbar across the top, side panes that open from it (click again to close), the map gets the rest. **Documentation** on the toolbar opens the development release report, this guide and the reports in their own window (A+ / A− or Ctrl +/− size the text). **Templates** on the toolbar opens your two squadron files
(`Documents\Pingu's Plotting Table\Templates`): edit and share them; any other template file dropped in shows up too. **Jungle Hawks** switch (with a JH release in MODS): the JH
planes, countries, skins, preset squadrons, Pacific buildings and jungle tiles, and the green look, all read from your installed mod.

**Start:** `ToolBox.bat`. The app runs on Python 3.13 only (3.14 or newer as the PC's main Python is fine and stays as it is).
The bat takes an installed Python 3.13 (through the `py` launcher) or, with none, downloads a private copy: python.org's Windows
build of 3.13.17 from nuget.org, SHA-256 checked, unpacked into `.python\` (nothing is installed, no registry change). A `.venv` on any
other version is thrown away and rebuilt. If no 3.13 can be found or fetched it stops with the fixes (`py install 3.13`, or the newest
3.13 Windows installer from python.org). The first start builds its own Python 3.13 environment (`.venv`, everything in
`requirements.txt`, a few hundred MB) and asks to read your IL-2 install once (maps, icons, planes, skins; nothing in
the game changes). "Re-read my game files" in the hot-key list (?) does it again after a game update. Data lives in
`%LOCALAPPDATA%\LocationLiftoff` (`LIFTOFF_HOME` moves it).

## Four tabs (+ Build)
- **1 Map Maker** - starting map (13 listed; Prokhorovka's 12.5 m grid is not supported yet), place it, look (any map's tiles / trees, building pack), land and water,
  airfields + towns (strips, airfield EXTENTS, towns, OSM auto populate). Finishing it starts the background
  download + quick stages (heights, land cover, rivers, forest) and the pre-bake preview layers.
- **2 Campaign Time Line** - periods (dates, countries, who holds each airfield), fronts + battles (PWCG time line,
  snap to rivers / roads, major-battle wizard, auto AI units), squadrons (existing PWCG / game squadrons or new:
  airframes, service / custom skins, emblem, name, period of service, base).
- **3 In-game Map** - the career / QMB map: the JH GUI-map look (relief, hillshade, sea, 10 km grid + square
  numbers, airfield and town names) and per-stage career map art in the JH tactics vocabulary (front bands, arrows,
  air routes, landings, labels, patrol orbits; red / blue / grey).
- **4 QMB Screen Builder** - one setting per period, missions placed from the tray.
- Map Maker's **Buildings** step: zoning (ESA WorldCover built-up land, OSM land use, piers and quays, your own painted zones), or one
  stock layout per town; each town can have its own method (footprints pulled from OSM, layout, or skip). A spread slider cuts modern
  sprawl back to the old centres. The Layers panel shows the estimated coverage.
  **Best practice:** take the building types and settlement footprints from the same map set as the starting map (Kuban to Kuban).
  Each set's buildings are made for its own ground and town layouts, so mixing sets gives towns that fit their ground less well.
- **6 Refine** - load a finished project and rebake only the ticked parts (quick missions, factions, buildings, trees, tile set, map, PWCG,
  airfields). Anything changed but not ticked stays unbaked and stays marked as changed. The box or terrain options need a full Lift off.
- **5 Factions** - what the career shows for each country the map uses, read from your own game: rename it, change its flag and
  badge, rename ranks and swap their insignia (or copy a whole rank set), replace event card photos, rename and re-picture
  awards. Applies to the whole game while the pack is enabled. Pilot portraits and newspapers are listed, not editable yet.
- **Bake** (top tab, Ctrl+B) - opens once Map Maker is complete; carries on from the background prefetch.

**Layers (L):** base map (OpenStreetMap / tile-set look / in-game style), live terrain renders with no download
(height heat map, slope, hillshade, contours - AWS Terrain Tiles; the bake uses Copernicus GLO-90), pre-bake layers
from the window's real data once Map Maker is done (heights, slope, contours, what becomes what, forest density,
rivers to carve, DEM coverage), design layers. **Hot keys (?):** Ctrl+S save, Ctrl+O open, Ctrl+Z / Ctrl+Y undo /
redo, Ctrl+1-4 tabs, [ ] steps, 1-9 tray, PageUp / PageDown periods, Delete, Esc, F fit, L layers, Ctrl+B build.

**Time steps on the map:** the box in the map's top-right corner lists the campaign's periods, always in view. Click one to see the map's fronts, zones and strips as they stand in that period; + opens the Time line step on a new period. The very first start asks for the language before anything else.

## Squadrons

Squadrons belong to the whole campaign. Lock the fronts and time line first, because a schedule is set against them. Each new squadron asks its country, airframe, start date and airfield, and any later moves, and warns you if an airfield is in enemy hands on that date. Edit schedule is on each squadron's summary. Period roster then lets you drag badges for one time step: nothing changes until Save period roster, and each move starts on that step's first day. The schedule goes into the career as dated `[period]` entries, which is how stock squadrons change base, and into PWCG's dated `airfields`.

## Top tabs and Ask Pingu

Each section of the job is a tab along the top. Its circle is empty, green when the section is complete, and flashes orange while a build or a
rebake works on it, so a partial rebake shows exactly which sections it touches. Red means a stage failed. **Ask Pingu**, bottom right, has a
Walkthrough of every step and a Helper that puts a ? on each one. Every answer has three views on the rotary switch: Plain English, In the Game
and Under the Hood. Its text is English only so far.

Open the app with `ToolBox.pyw`, or the `Pingu's Plotting Table` shortcut that `ToolBox.bat` writes beside it: no terminal shows.
Use `ToolBox.bat` again after updating, because it installs any new libraries.

## Mission editor

The Missions button on the toolbar builds a single mission on the finished map: fighter and bomber flights (yours or AI; parked, on the
runway or in the air; route points, patrol, escort, intercept, bomb), ground forces (tanks, trucks, artillery, flak, MG positions, static
or on a route, with a target) and objectives (destroy, protect, reach). Write mission saves `Documents\Pingu's Plotting Table\Missions\<map>`:
a `.Mission` the game's own editor opens, and a `.msnbin` the game flies, compiled by your game's `bin\resaver\MissionResaver.exe`.
The next pack build takes them into `data\Missions\ToolBox`; Copy into the pack does it for a disabled pack straight away.
The game's parser reads every mission back after compiling, and a mission that loses an object or a link is refused.

### PEP: Pingus Editor Plugin

Every pack also carries a starter mission and `PEP - Open <map> in Editor.bat`, for mission makers who work in the game's own editor.
Enable the pack, run the file from the game's main folder, and `bin\editor\STEditor.exe` opens on the map with its airfields and
buildings. The editor is not patched: it reads loose files first, so it only needs the pack enabled and a mission that names the map.
File > Import From File brings in your own `.Group` routines; save the result under a new name, because disabling the pack removes the
starter. For multiplayer, see [Multiplayer and dedicated servers](#multiplayer-and-dedicated-servers).

**Inside the app:** Finish > Game's editor runs the same editor in the app's own window, with no pack to enable. It runs from a private
folder (`<game drive>\ToolBox_Editor`, NTFS, same drive as the game): a copy of the editor and of the pack's data, plus links to the
game's archives and folders. Your game and JSGME's list don't change. Saved work stays in `Documents\Pingu's Plotting Table\Editor\<map>`. Remove that
folder only with the button on that step, because a plain delete could follow its links into the game's data. Closing the app leaves an
open editor running as its own window, so unsaved work isn't lost.

## Settings and languages

The Settings button on the toolbar holds what belongs to this PC, not to a map (`config.json`): language, GUI size, install paths, where
packs, missions and templates go, what new packs include, hot keys, and the maps and planes you own. Toolbar and panes grow with the
window (full size at 1920 wide, double at 3840) unless you pick a size. The GUI comes in German, French, Italian, Polish, Russian, Turkish,
Simplified Chinese and Japanese. Those translations are machine-written, so corrections are welcome: `static\i18n\<lang>.txt`, one
`<id>|<text>` per line, ids from `source.txt`.

## Using it (Map Maker)
1. **Starting map** - any listed map, for example Kuban (460.8 x 358.4 km, the Jungle Hawks slot) or Normandy
   (371.2 x 396.8 km, the Guadalcanal slot). You need that map in your game to fly the result. The copper box is the
   whole map grid at its real size; the dashed box is the play area.
2. **Move it** - drag the box, search a place (Enter), "Box to view", or "Stock position". North stays up: the
   game's map grids are north-aligned and so is every pipeline stage.
3. **Options** - map name; tile set (Jungle Hawks jungle, used in place from JH enabled below the pack, or the stock
   map tiles without JH); trees (JH 1.18 jungle look or real forests from ESA WorldCover) and density; real land
   cover (grass plains, swamps, mangroves); OpenStreetMap river courses and how many rivers get carved; date
   (shows the season folder) and factions (country slots, as Jungle Hawks uses them).
4. **Airfields** - "+ Allied strip" / "+ Axis strip", click the map, drag to move, set name / length / heading /
   width. Strips are flattened, cleared of trees and get runway smoothing (+ Marston mat on Normandy). A strip that
   lands on water or a cliff is nudged to the nearest dry, flat ground.
5. **Build** - each stage shows its own progress bar; stages whose inputs did not change are reused (tick "rebuild
   every stage" to force). The pack lands in `<game>\MODS\Pingu's ToolBox - <name> <n>` as a NEW, DISABLED
   folder (never over an existing or enabled one, always real copies). Enable it in JSGME last: above Jungle Hawks
   for the jungle set, with Jungle Hawks disabled for any other tile set (the pack then carries the map loader).

## What a pack contains (Kuban)
`data\graphics\LANDSCAPE_Kuban_{s,a,sp}`: height.dat / height_w.dat (real DEM, smooth coast, ETOPO sea floor,
flattened strips, carved rivers), height.hini (window corners, stock play box), water.wtr, forest_map.wtr,
texturemap.bmp, distlod (far horizon from ETOPO), surface.dat (stock fields / towns removed, runway lines),
empty roads / cities / nature meshes; `data\swf\il2\maps\kuban-*\info.txt` (the window's latitudes for the sun);
`data\swf\il2\mapstiles\kuban` (the in-game briefing / QMB map redrawn: relief, coast, strips, OSM city names).
`data\scg\12`: new base + trunk scenes (no stock object left), airfield blocks and the 8 wind location files for your
strips; every AQM and career scene on this landscape swapped too. `data\swf\il2\qmb\setting10-12`: dates, sun, names and
missions. Plus README / JOB / SHA256 files with unique root names.

**Roads:** the stage takes OpenStreetMap's main roads and railways, so the network is today's, not 1942's. The game's editor builds the road caches once during the build, so close IL-2 and its editor while building: if either is open, the roads still work, but the game rebuilds them on every load, which adds minutes.

**PWCG limits:** map area, front dates, date range and ground troops are fixed in PWCG's own program, so a pack can't change them; bridges and stations are
objects PWCG places in its missions, with no trains or convoys. The build checks the pack's files, not the game
itself, so fly each new map once to confirm it.

## Multiplayer and dedicated servers

Every pack carries GB Mod Loader 1.4.2 with one plugin, loosemaps, and a dedicated-server kit at its root, `ToolBox server - <name> <n>\`.
It is not yet tried on a real dedicated server, so please report what `bin\game\gbml_server_log.txt` says the first time.

**How the map gets in online:** loosemaps is the map half of the old scriptcrc plugin (scriptcrc no longer exists in GB Mod Loader 1.4.2).
It lets a mission start on the pack's loose landscape only when the game's own map list unlocks that exact map for your account; a locked
map keeps the game's own decision, in single player and in multiplayer. In multiplayer it also acts only inside a session that GB Mod Loader's
own handshake has verified: the host or dedicated server runs the same loader and the same mod set. Loader 1.4.2 handshakes by itself
(`[multiplayer] handshake=1`, `strict=1`, `kick=1`): a player whose loader, plugins or plugin settings differ is kicked by a server running it,
and refuses to join a host that doesn't. loosemaps declares itself client-only, so it is left out of that match.

| File | What it is |
|---|---|
| `bin\game\winmm.dll` | GB Mod Loader 1.4.2, the same file as the pack's own. Since loader 1.3.0 it also starts under `DServer.exe` (`[server] enabled=1`). There it runs only the plugins under `[server_plugins]` in `gbml.ini`, which is empty: the server needs no plugin for the map. As the host it runs the handshake. |
| `bin\game\gbml.ini` | The pack's own `gbml.ini`: Dusty's template with `[multiplayer]`, `[server]` and an empty `[server_plugins]`. |
| `map_sha256.txt` | The SHA-256 of every map file the pack lays down: `data\graphics\LANDSCAPE_*` and `data\scg\*`. |
| `Check map files.bat` | Compares an install's map files with that list and says OK or NOT OK. With the pack enabled it sits in the game's main folder, so it checks that install. You can also drag a game folder onto it. |
| `README - server.txt` | The steps below, for whoever runs the server. |

**Server** (the IL-2 install that runs `DServer.exe`):
1. Put the pack in that install's `MODS` folder and enable it with JSGME, as on a player's PC. This puts the map files where DServer reads them, and the pack's own `bin\game` already holds the right `winmm.dll` and `gbml.ini`. Without JSGME, copy the pack's `data` folder into the server install's main folder, and the kit's `bin\game` files into the server's `bin\game`.
2. Turn Mods ON in the server's `startup.cfg`: a session hosted with GB Mod Loader must be a Mods ON session (`host_mods_on=1`).
3. Run `Check map files.bat`. It must say OK.
4. Start DServer and open `bin\game\gbml_server_log.txt` (or `gbml_log.txt`). You want `GB Mod Loader 1.4.2 starting ... - DEDICATED SERVER`, `build guard passed`, `handshake installed`, and `server: no plugin listed under [server_plugins] - the server runs no plugin`.

DServer needs no plugin for the map. It has no map ownership check and reads the loose heightmap as it finds it.

**Every player:**
1. Enable the same pack (same name and number) with JSGME, with its GB Mod Loader in place.
2. Have the same GB Mod Loader plugins as the server and nothing else in `bin\game\gbml`: another mod's plugins (Jungle Hawks', for one) change the match and the server kicks you. In `gbml_log.txt` you want `joining: the host runs the same GB Mod Loader and mod set - verified` and then `loose map ownership exception applied ... GUI unlock confirmed`.
3. Own the base map on your own account: loosemaps lets the loose heightmap in only when your own map list unlocks that map.
4. Run `Check map files.bat`. It must say OK.

The server and every player must have byte-identical map files, or they fly over different ground. Build the pack once and share that one folder: a rebuild on another PC is a different pack.

**Removing:** on the server, disable the pack (without JSGME, delete `bin\game\winmm.dll`, `gbml.ini`, `gbml\` and the log). Players only need to disable the pack.

**Checks:** the pack stage writes the kit and then checks it before the pack is finished. The kit's map list must equal the pack's map files byte for byte, its `winmm.dll` must be the bundled 1.4.2 file and the pack's own, and its `gbml.ini` must be the pack's, with `[server_plugins]`, `[server] enabled=1` and the handshake on. Any mismatch stops the pack.

**common.dll:** no plugin in a pack may hook, patch or read through the game's `common.dll`. Neither `winmm.dll` 1.4.2 nor `loosemaps.dll` names it. A plugin of your own whose DLL names `common.dll` is left out of the pack, and the build log says why; your own copy of Formation Tweaks (`gbai`) goes in with `[Flight] briefing_titles = 0`, because that feature hooks `fopen` in every game module's import table, `common.dll`'s included.

## Licence

Pingu's Plotting Table: A Mapper's Toolkit is closed-source software in open beta, © 2026 Off Shell Instruments Pty Ltd, all rights reserved: free for personal, non-commercial beta testing, with no redistribution, modification, reverse engineering or commercial use, and no warranty. Full terms: `LICENSE` (also in the Documentation window). Third-party components and data keep their own licences: `NOTICE.md` (Leaflet, GB Mod Loader, data sources).
