# Changelog

## Release1.2.1 (2026-11-14)

- **Update coverage fixed:** in 1.2 the button did nothing and the Campaign tab stayed locked. It now starts the map data download, and the Campaign tab opens when it finishes.
- **A map name used before on another starting map** no longer stops the preparation at Pre-bake preview layers.
- **Map data:** a tick list of the OpenStreetMap extracts the map needs, with each one's share of the map, its size, and whether it is already downloaded. Small corner extracts start unticked. Extracts are chosen by the map's land only, so sea inside a country's outline no longer pulls in a whole country, and a big bundle such as US South gives way to the state extracts.
- **Big extracts** are read for the map's area only.
- **Progress:** each stage shows its latest step, and downloads show MB done, MB/s and the time left.
- **Fronts:** Unlock brings the front tools back at once.

## Release1.2 (2026-11-14)

- **Look step:** pick the ground tiles, farmland, woods, grass, sand, sea, rivers, trees, and the buildings and ground of each kind of town, from the stock maps you own or your own mix.
- **Vanilla and Custom templates:** one click sets every row to a stock map and season. Save your own mix as a template.
- **Test squares:** bake a 1 x 1 km square of the map (up to 5 km) in a few minutes; every Look change after that is redrawn on it in seconds, with no bake. Add more squares as tabs.
- **Mockup town:** a ready-made seaside town with every Look row in it, sea cliff included. It needs no bake.
- **1940s towns:** today's sprawl is cut back by road distance from each town label. Old centres stay whole and the cut suburbs become farmland. No orphan roads, no houses in the sea.
- **In-game map:** outline towns and woods and draw rivers and lakes, smoothed the way the stock maps draw them.
- **Campaign toolbar:** the tools sit under tabs (Frontlines and Periods, Battles, Defence and Assault zones, Arrows, Units). The Allied / Axis switch sits beside them and the whole lower bar takes the side's colour. Arrow tools have icons drawn the way the map draws them.
- **Periods:** a new campaign's first period runs one month; an added period starts the day after the last one ends.
- **Map data:** the app asks before it downloads OpenStreetMap for an area, says how big it is, and shows the progress. Update coverage is the Buildings step's main button.
- **Updates:** at start the app checks for a newer release and can update only the files that changed.
- **Save Logs to Zip:** one button on the bottom bar bundles the map and bake logs for a bug report.
- **Jungle Hawks datapack** in every release.
- **Fixes:** far-view pop-in of small buildings, runway beds on every starting map, land below sea level, ground tiles that join as on the stock maps, an airfield near the map's edge, outlines cut short, and a sketched front let go off the map.

## Release1.1 (2026-11-11)

The first full release of Pingu's Plotting Table: A Mapper's Toolkit, made for IL-2 Sturmovik: Great Battles.

- Real-world terrain from open data: heights, coast and sea floor, rivers and lakes, forests and land cover, roads, railways, bridges, towns and airfields.
- A dynamic campaign on the new map: career, Advanced Quick Missions, quick missions and a PWCG overlay, all on the same strips.
- Factions, squadrons with schedules, front lines and plans, career map art, seasons and weather.
- Settlement labels in tiers, with per-tier switches and a minimum distance between labels.
- Clear the shared download cache or one map's build files from Settings; open the plugins folder.
- Edits to a finished map wait in a notice with **Prepare now**.
- Multiplayer: every pack carries a dedicated-server kit with GB Mod Loader 1.4.2 and loosemaps.
- New boot intro: the map peels away to a dark blue and beige title.
- The installer shows a progress bar and names each step and each file as it downloads; the shortcut is now called **Pingu's Plotting Table**.
- Licence: an end user licence agreement from Off Shell Instruments Pty Ltd. The Plotting Table is made with the full endorsement and support of 1C Game Studios. It isn't affiliated with PWCG.
