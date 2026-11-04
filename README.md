# SAR Probability Mapper

A planning aid that maps where a missing person is most likely to be found, based on their last known point (LKP), subject category and conditions.

It runs entirely in the browser: one `index.html` file, no server, no accounts, no data sent anywhere.

## What it does

- Starts from lost person behavior distance statistics (25 / 50 / 75 / 95% rings, modeled on ISRID data) for the selected subject category.
- Weights the probability by distance to roads, trails, streams, water and buildings, by slope and elevation change, and by known direction of travel.
- Adjusts for medical history, weather, darkness and hours since LKP.
- Shows the result as a probability heat map, distance rings, segments or contours.
- Lists a segment priority table with probability of area (POA), area and POA density, plus an incident summary you can copy.

## Using your own map

Load a topo or aerial screenshot (CalTopo, Google Earth or USGS) with north up, enter its width in miles, then trace roads, trails, streams, water and buildings with the drawing tools so the model can use them.

## Running it

Open `index.html` in any modern browser, or enable GitHub Pages for this repo (Settings → Pages → deploy from `main`) to get a link you can open on any phone.

## Disclaimer

This is a prototype planning aid for experienced search managers. It does not replace a full search plan or consensus (Mattson) weighting. Check the distance values against your Lost Person Behavior reference and adjust for your terrain, weather and subject.
