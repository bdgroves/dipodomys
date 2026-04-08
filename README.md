# 🐾 DIPODOMYS

### *A Data Portrait of Death Valley's Kangaroo Rats*

**[Live Site → bdgroves.github.io/dipodomys](https://bdgroves.github.io/dipodomys)**

---

## The Animal

It is two in the morning at Badwater Basin, the lowest point in North America at 282 feet below sea level. The temperature has dropped to 95°F. A small, pale mammal the size of a large gerbil emerges from a burrow entrance in the hardpan, pauses, then launches itself across the salt flat in a series of long bipedal bounds — five feet per leap, tail spinning for balance, landing in silence.

It will not drink water tonight. It never does.

*Dipodomys deserti* — the Desert Kangaroo Rat — is one of the most physiologically extreme mammals on Earth. It lives in one of the hottest, driest environments on the planet, and it does so without ever consuming free liquid water. Instead, it extracts moisture metabolically from dry seeds, through the same oxidative process by which all cells release energy from carbohydrates. Its kidneys concentrate urine at five times the efficiency of a human's. Its nasal passages recapture moisture from exhaled breath before it escapes. It has, over five million years of evolution in the Mojave basin, essentially solved the problem of liquid water.

And it does all of this while being spectacularly, almost absurdly, agile.

---

## Two Species, One Valley

Death Valley hosts two kangaroo rat species, and their differences tell a story about the two great survival strategies available to desert specialists.

**Dipodomys deserti** — the larger of the two, pale as bleached sand — is a narrow specialist. It lives almost exclusively on open, firm sandy flats and alluvial fans. It requires loose, wind-deposited sand for burrowing. It will not venture onto rocky substrate. Its entire range barely extends beyond the Mojave. Everything about it is finely tuned to a specific kind of extreme: the open, hot, sparsely vegetated desert floor. This is an animal that has bet everything on one habitat, and it has been winning for millions of years.

**Dipodomys merriami** — Merriam's Kangaroo Rat — has made the opposite bet. Smaller, darker, and equipped with four hind toes instead of five, it is the most widespread kangaroo rat in North America. It lives in desert scrub, sagebrub steppe, alluvial bajadas, Joshua tree woodland, and rocky slopes. It ranges from California to Texas, from sea level to the mountain foothills. Where *deserti* has specialized, *merriami* has generalized — and the tradeoff shows in their relative abundance. *Merriami* is everywhere. *Deserti* is only here, in exactly this kind of place.

Where the two species meet — as they do across Death Valley's sandy flats — they partition microhabitats. *Deserti* takes the open dunes. *Merriami* works the surrounding scrub. The boundary between them is ecological, not geographic, drawn in seed patches and burrow densities and nightly foraging circuits.

---

## The Environment

Death Valley is not merely hot. It is the hottest reliably measured place on Earth, with a surface air temperature record of **134°F (56.7°C)** set at Furnace Creek in July 1913. Its lowest point sits nearly three hundred feet below sea level, at the bottom of a long-collapsed lake bed that dried as the Sierra Nevada rose and blocked Pacific moisture. Annual rainfall averages **2.2 inches**. Some years, none falls at all.

The valley floor is an extreme even within desert ecology — a rain shadow within a rain shadow, ringed by mountain ranges that strip moisture from every approaching storm system. The Panamint Range to the west rises to 11,049 feet at Telescope Peak. The elevation change from summit to valley floor — over 11,000 vertical feet in less than 20 miles — is one of the steepest in the contiguous United States.

Kangaroo rats survive here through a combination of behavioral and physiological adaptations so complete they almost seem designed for this specific place:

- **Burrow thermoregulation** — subsurface temperatures at 18 inches run 20–30°C cooler than the surface, allowing animals to avoid the worst heat entirely
- **Nocturnal activity** — emergence timed to the window after surface temperatures drop but before early dawn
- **Fur-lined cheek pouches** — external storage allowing rapid seed harvest and transport without repeated surface exposure
- **Enlarged auditory bullae** — the outsized middle ear structures that give kangaroo rats their distinctive wide-skulled profile, evolved to detect the low-frequency wingbeats of approaching owls in near-total darkness
- **Bipedal saltation** — locomotion that delivers explosive, directional escape jumps of up to nine feet, making them nearly impossible for a striking rattlesnake to intercept

The desert floor at night, to a kangaroo rat, is not a hostile environment. It is home.

---

## The Data

This project pulls from **[iNaturalist](https://www.inaturalist.org)**, the largest community science biodiversity platform in existence, via their public REST API. Every observation on the map is a georeferenced wildlife sighting contributed by a naturalist, researcher, or citizen scientist — many photographed with a phone flashlight in the middle of the night in one of the most remote desert regions in the United States.

The data tells its own story. The temporal chart reveals the **citizen science explosion** clearly: a long flat line of museum specimen records from the early 20th century, a modest uptick as field ecologists began systematic surveys in the mid-century, and then — after roughly 2012 — a near-vertical spike as iNaturalist reached critical mass and made every person with a smartphone a potential data contributor. The bias is real and worth naming: we know more about where these animals were seen in 2023 than in 1983, not because they changed their range, but because observer coverage changed.

The **elevation chart** shows the habitat partitioning directly: *deserti* clusters tightly near and below sea level, on the valley floor and lower alluvial fans. *Merriami* spreads across a wider elevation range, turning up on bajadas, in canyons, on the slopes of the surrounding ranges. Two species, same valley, different vertical worlds.

The **seasonal chart** captures an interesting observer effect: activity appears to drop in peak summer, not because the animals become less active (they don't — food is most abundant in spring and fall, but they are active year-round), but because *human observers* avoid Death Valley in July and August when temperatures routinely exceed 120°F on the valley floor.

All occurrence data is fetched **live on page load** — no cached datasets, no static files. Every visit reflects the current state of the iNaturalist database.

---

## The Stack

This is a deliberately minimal project. No frameworks. No build system. No package manager. One HTML file.

| Layer | Technology | Why |
|---|---|---|
| **Frontend** | Vanilla HTML/CSS/JS | No build step, instant GitHub Pages deploy, zero dependencies to rot |
| **Mapping** | [Leaflet.js](https://leafletjs.com) + [MarkerCluster](https://github.com/Leaflet/Leaflet.markercluster) | Lightweight, performant, excellent clustering for dense point data |
| **Map tiles** | [CartoDB Dark Matter](https://carto.com/basemaps) | Dark basemap complements the desert-night aesthetic without competing with data |
| **Charts** | [Chart.js](https://www.chartjs.org) | Responsive, canvas-based, minimal footprint |
| **Occurrence data** | [iNaturalist API v1](https://api.inaturalist.org/v1) | Research-grade observations, bounding box queries, CORS-enabled, free |
| **Photos** | iNaturalist API (same endpoint) | CC-licensed field photos embedded directly from observer contributions |
| **Typography** | [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) · [Crimson Pro](https://fonts.google.com/specimen/Crimson+Pro) · [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) | Display serif for drama, body serif for readability, mono for data |
| **Hosting** | GitHub Pages | Free, fast, zero config, version-controlled |

The design philosophy mirrors the ecology: **specialization where it matters, nothing extraneous**. The page makes six API calls on load (two species × up to three pages of occurrence data, plus two photo fetches), renders everything client-side, and requires no server, no database, no authentication, and no maintenance.

---

## Why This Matters

Citizen science platforms like iNaturalist have fundamentally changed what is possible in ecological research. A dataset that would have required years of fieldwork and hundreds of thousands of dollars in survey effort can now be assembled in seconds via API call. The observations mapped here span over a century — but the vast majority were made in the last decade, by people who weren't professional scientists, who just happened to be in the desert at night with a phone and an interest in what they found.

That democratization of data collection has a flip side: **observer bias is ecological signal**. The gaps on the map are not just places where kangaroo rats don't live — they are places where people with smartphones don't go. The peak in the temporal chart at 2020–2022 reflects, among other things, pandemic-era outdoor recreation trends. Understanding what the data *doesn't* show is as important as understanding what it does.

Visualizing that data — making it interactive, explorable, and contextualized by natural history narrative — is a form of scientific communication. The goal is not just to show where these animals are, but to make legible *why* they are there, what it costs them to be there, and what it would mean to lose them.

*Dipodomys deserti* survives 134-degree heat without drinking water. It has earned a decent website.

---

## Data Sources

| Source | Details |
|---|---|
| iNaturalist occurrence data | `api.inaturalist.org/v1/observations` · taxon IDs 44120 (*deserti*), 44126 (*merriami*) · research-grade only |
| iNaturalist photos | Same endpoint · CC-licensed field photographs |
| Natural history content | Animal Diversity Web, Wikipedia (CC BY-SA), primary literature |

---

## Related

- **[desert-ecostats](https://github.com/bdgroves/desert-ecostats)** — R-based community ecology toolkit (NMDS, PERMANOVA, indicator species analysis, co-occurrence) that this project grew out of
- **[brooksgroves.com](https://brooksgroves.com)** — built for the Ologies section

---

*Built by [Brooks Groves](https://brooksgroves.com) · GIS Analyst & Data Scientist · Lakewood, WA*
