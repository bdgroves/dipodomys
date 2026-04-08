# 🐾 DIPODOMYS

**A data-driven field portrait of Death Valley's kangaroo rats.**

Live at: [bdgroves.github.io/dipodomys](https://bdgroves.github.io/dipodomys)

Built for the [Ologies section](https://brooksgroves.com) of brooksgroves.com.

---

## What it is

A single-page field study combining natural history narrative, species profiles, and live data visualization for two kangaroo rat species — *Dipodomys deserti* and *Dipodomys merriami* — in the Death Valley region of the Mojave Desert.

All occurrence data is fetched live from the [GBIF API](https://www.gbif.org) on page load. No build step. No server. No stale data.

## What's on the page

- **Narrative intro** — natural history essay on kangaroo rat ecology and Death Valley
- **Species profiles** — side-by-side field guide cards for *D. deserti* and *D. merriami*
- **Distribution map** — Leaflet + CartoDB dark tiles, clustered occurrence points from GBIF
- **Records by year** — full historical record timeline
- **Species over time** — stacked line chart comparing observation trends post-1970
- **Seasonal activity** — monthly observation distribution
- **Elevation profile** — histogram of where each species is recorded by altitude
- **Adaptation notes** — metabolic water, bipedal locomotion, thermal strategy, seed caching, habitat partitioning, predator evasion

## Tech

- Pure HTML/CSS/JS — no framework, no bundler
- [Leaflet](https://leafletjs.com) + [Leaflet.MarkerCluster](https://github.com/Leaflet/Leaflet.markercluster) for mapping
- [Chart.js](https://www.chartjs.org) for all data visualization
- [GBIF Occurrence Search API](https://www.gbif.org/developer/occurrence) — live data, no API key required
- [CartoDB Dark Matter](https://carto.com/basemaps) tiles
- Google Fonts: Playfair Display, Crimson Pro, JetBrains Mono
- GitHub Pages for hosting

## GBIF taxon keys

| Species | Key |
|---|---|
| *Dipodomys deserti* | 2438531 |
| *Dipodomys merriami* | 2438529 |

## Related

- [desert-ecostats](https://github.com/bdgroves/desert-ecostats) — R-based ecology statistics toolkit this project grew out of
