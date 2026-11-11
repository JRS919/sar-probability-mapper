# SAR Probability Mapper

A planning aid that maps where a missing person is most likely to be found, based on their last known point (LKP), subject category and conditions, and plans where drones and ground teams should search.

It runs in the browser from one `index.html` file: no server, no accounts. Map tiles and feature data load from public services (listed below).

**Current version:** v1.5 (2026-11-11). The version and date show in the browser tab and in the app header.

## What it does

- Starts from lost person behavior distance statistics (25 / 50 / 75 / 95% rings, modeled on ISRID data) for the selected subject category.
- Weights the probability by distance to roads, trails, streams, water and buildings, by slope and uphill/downhill travel, and by known direction of travel.
- Adjusts for medical history, weather, darkness and hours since LKP.
- **Search grid:** rings and pie sectors around the LKP (probability rings or your own distances in meters, 4 to 16 sectors, rotatable), or an 8 x 8 square grid. Every segment gets its share of the probability map (POA) and a priority rank.
- **Drone search blocks:** ranks ground by probability x chance the camera can see the subject (POD), using tree canopy, leaf season, light, weather, water and buildings, for thermal, RGB or both.
- **Exports, all numbered (v01, v02…) and dated:**
  - **ATAK data package (.zip):** every grid segment, drone block, probability area and distance ring arrives in ATAK as its own editable shape, plus the LKP. Tap a shape in ATAK to rename it to a search team, recolor it or add remarks.
  - One-page briefing (print, JPEG, PDF), KML, GeoJSON and a text summary.

## Maps

- **OpenStreetMap** (default), **OpenTopoMap** (terrain), USGS Topo, USGS Imagery, USGS Imagery + Topo, Esri World Imagery, Esri Streets and Esri Topo, from the layer button on the map.
- **Terrain shading** and **Contours** overlays are built from elevation data (AWS Terrain Tiles: USGS 3DEP and others).
- Roads, trails, streams, ponds and buildings come from the USGS National Map and OpenStreetMap (Overpass API). Tree canopy comes from the USFS / NLCD tree canopy cover dataset.

OpenStreetMap and OpenTopoMap tiles only load when the app is opened from its web address (GitHub Pages). Opened as a downloaded file, those two maps are blocked by their servers, so the app starts on USGS imagery instead.

Map data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright). Terrain map © [OpenTopoMap](https://opentopomap.org) (CC-BY-SA).

## Getting it into ATAK

1. Run the analysis, set up the search grid, then on the Results tab press **ATAK data package (.zip)**. Untick anything you don't want in the package.
2. In ATAK: **Import Manager → Local SD**, pick the .zip. Or send the .zip to the team as a data package.
3. Tap a segment, open its details, and change the name to the search team (for example "B3" → "Ground Team 2"), change its color, or add remarks.

ESRI shapefiles import into ATAK as read-only overlay layers, so the app uses ATAK's own shape format instead, which keeps every segment editable.

## Running it

Enable GitHub Pages for this repo (Settings → Pages → deploy from `main`) to get a link you can open on any phone or laptop: `https://jrs919.github.io/sar-probability-mapper/`. You can also open `index.html` directly in a browser.

## Disclaimer

This is a prototype planning aid for experienced search managers. It does not replace a full search plan or consensus (Mattson) weighting. Check the distance values against your Lost Person Behavior reference and adjust for your terrain, weather and subject. Drone detection (POD) values are planning estimates, not measured detection rates for a specific aircraft.
