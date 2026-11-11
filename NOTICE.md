# Third-party notices

Pingu's Plotting Table: A Mapper's Toolkit is closed-source software, © 2026 Off Shell Instruments Pty Ltd, under the open beta end user licence agreement in `LICENSE`. That licence covers Off Shell Instruments' own work only. The components and data below are not Off Shell Instruments': each keeps its own licence and credit, and nothing in `LICENSE` limits the rights those licences give you over them.

## Bundled libraries (`static/vendor/`, licence file beside each)
- Leaflet 1.9.4 - BSD-2-Clause, (c) Volodymyr Agafonkin
- Leaflet.draw 1.0.4 - MIT, (c) Jon West, Jacob Toye and Leaflet

The BSD-2-Clause and MIT licences require their copyright notice and licence text to travel with every copy, which is why each library's own licence file ships beside it in `static/vendor/`.

GB Mod Loader - Dusty

## Installed on your PC, not bundled
The installer (`installer.bat`) fetches Python packages from PyPI into the app's own `.venv`: Flask, pywebview, Requests, Pillow, NumPy, SciPy, OpenCV (opencv-python-headless), Matplotlib and PyOsmium. Each keeps its own open-source licence, which pip installs with it. They aren't part of the Software. The same goes for PWCG (Pat Wilson's Campaign Generator) and for PRISM and HSDSync if you have them: they are separate programs under their own authors' terms, and this project isn't affiliated with them.

## Data
- Map tiles and waterways (c) OpenStreetMap contributors, ODbL. Tiles come through the local proxy (own User-Agent, 7-day cache), search one request a second. Everything else OSM comes from Geofabrik's regional extracts, downloaded once per region. Packs built from it must keep the "(c) OpenStreetMap contributors" credit.
- Copernicus DEM GLO-90 (c) DLR e.V. 2010-2014 and (c) Airbus Defence and Space GmbH 2014-2018, provided under COPERNICUS by the European Union and ESA.
- NOAA NCEI ETOPO 2022 (public domain). ESA WorldCover 2021 v200 (CC BY 4.0, credit required).

## Fonts
The logo uses Georgia Bold Italic (a Windows system font). The font itself isn't shipped.

## The game
IL-2 Sturmovik: Great Battles, its files and assets belong to their owners, and the Software needs your own copy of the game. Packs you build contain material derived from your game, so check the game's terms before sharing one.
