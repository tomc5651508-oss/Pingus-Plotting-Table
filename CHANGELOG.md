# Changelog

## Release1.1 (2026-11-11)

- Every pack carries GB Mod Loader 1.5.0 (`winmm.dll` + `GBML.dll`) with loosemaps, in the pack and in its dedicated-server kit.
- Pack folders are named after the map and the app's version: `<Map Name> [Pingu'sPTv1.1]`, `<Map Name> 2 [Pingu'sPTv1.1]` for the next build of the same map, and the server kit `<Map Name> server [Pingu'sPTv1.1]`.
- The installer is now `installer.bat`, and its shortcut is **Pingu's PT Installer**. Old `ToolBox.bat` copies and shortcuts are removed.
- In-game map: the tile layout is read from your game's own map files at bake time and checked against the terrain. Every airfield square is then found again in the written tiles, so a map drawn off its ground stops the build. Prokhorovka's 12.5 m terrain is now drawn at the right scale.

## Release1.0 (2026-11-11)

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
