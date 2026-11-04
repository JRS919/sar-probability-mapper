# SAR Probability Mapper

A planning aid that maps where a missing person is most likely to be found, based on their last known point (LKP), subject category and conditions.

It runs entirely in the browser: one `index.html` file, no server, no accounts, no data sent anywhere.

## What it does

- Starts from lost person behavior distance statistics (25 / 50 / 75 / 95% rings, modeled on ISRID data) for the selected subject category.
- Weights the probability by distance to roads, trails, streams, water and buildings, by slope and elevation change, and by known direction of travel.
- Adjusts for medical history, weather, darkness and hours since LKP.
- Shows the result as a probability heat map, distance rings, segments or contours.
- Lists a segment priority table with probability of area (POA), area and POA density, plus an incident summary you can copy.

## Maps

**OpenStreetMap (default).** Search an address or coordinates, or tap **My location**, then tap the map to place the LKP. The app loads automatically:

- the OpenStreetMap base map
- roads, trails, streams, ponds and lakes, and buildings (buildings only when the map covers about 7 miles or less), from the Overpass API
- elevation for slope and uphill/downhill weighting, from Terrain Tiles on AWS (USGS 3DEP, SRTM)

Use the drawing tools to add anything the map is missing, like logging roads or game trails. This mode needs an internet connection.

**Sample terrain.** A generated practice area that works offline.

**My map image.** Load a topo or aerial screenshot (CalTopo, Google Earth or USGS) with north up, enter its width in miles, then trace roads, trails, streams, water and buildings so the model can use them.

Map data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright).

## Running it

Open `index.html` in any modern browser, or enable GitHub Pages for this repo (Settings → Pages → deploy from `main`) to get a link you can open on any phone.

## Disclaimer

This is a prototype planning aid for experienced search managers. It does not replace a full search plan or consensus (Mattson) weighting. Check the distance values against your Lost Person Behavior reference and adjust for your terrain, weather and subject.
