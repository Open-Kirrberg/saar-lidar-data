# Saar LiDAR Explorer – Daten (Teil 1)

Static data for the [Saar LiDAR Explorer](https://open-kirrberg.github.io/saar-lidar-explorer/) (code: https://github.com/Open-Kirrberg/saar-lidar-explorer), served by GitHub Pages at https://open-kirrberg.github.io/saar-lidar-data/.

> **Schauen, nicht graben.** Everything here is terrain data and *hypotheses*, not finds. Archaeological sites are protected (Saarländisches Denkmalschutzgesetz SDschG, Denkmalschutzgesetz Rheinland-Pfalz DSchG). No digging, no metal detecting; report finds to the Landesdenkmalamt.

## Contents

| Path | What |
|---|---|
| `overall/` | AOI „Homburg / Kirrberg / Karlsberg“: `manifest.json`, height chunks (Terrarium PNG), relief layers, overview levels, DOM, orthophoto, historic maps, LoD2 buildings, OSM ways, ALKIS parcels, point clouds, relict candidates. Format: `docs/data-contract.md` in the code repository. The Leaflet tiles (`xyz`) are in the second data repository (https://open-kirrberg.github.io/saar-lidar-data-2/), referenced by absolute URLs in the manifest. |
| `pois.geojson` | Known sites („Bekannte Orte“), WGS84. |
| `shared/karlsberg1789/` | Hypothetical reconstruction of Schloss Karlsberg, summer 1789 (light model for the explorer). |
| `castle-viewer/terrain/` | 1 m terrain crops (2025 DTM and the 1789 terrain hypothesis) used to build the castle viewer; `SHA256SUMS`. |

## Relict candidates (`overall/candidates/`)

The 3276 *Verdachtsflächen* are the output of an **automatic, unverified** terrain-shape detector (pits, mounds, ditches, rectangular structures, platforms). They are **hypotheses, not verified sites**: most are natural forms, modern disturbances, tracks or noise. Nobody has checked them in the field. They are published for looking and learning only — **not** as a guide for digging, probing or detector use.

## Licences and attribution

The code is MIT-licensed (see the code repository). **The data keep their own licences:**

- Geobasisdaten Saarland (LVGL-SL: DGM1/DOM1/ALS points, DOP20, LoD2, ALKIS, historic maps) and Rheinland-Pfalz (GeoBasis-DE/LVermGeoRP): **Datenlizenz Deutschland – Namensnennung – Version 2.0** (dl-de/by-2-0, https://www.govdata.de/dl-de/by-2-0). All products here are processed („Daten bearbeitet“).
- OpenStreetMap data (ways, most POI coordinates): **ODbL 1.0** (https://opendatacommons.org/licenses/odbl/), © OpenStreetMap-Mitwirkende.
- Reconstruction 1789 (`shared/karlsberg1789/`): own work (hypothesis); building footprints partly derived from the Lageplan 2006 by schloss-carlsberg.de („Mannlich“), **CC BY-SA 2.0 DE** — these derived geometries are shared under CC BY-SA 2.0 DE.
- Relief visualisations, candidates, levels and encodings: derived from the data above (same licences).

Attribution entries (also in `ATTRIBUTION`):

- © GeoBasis-DE/LVGL-SL (2026), dl-de/by-2-0, Daten bearbeitet
- © GeoBasis-DE/LVermGeoRP (2026), dl-de/by-2-0, www.lvermgeo.rlp.de, Daten bearbeitet
- © OpenStreetMap-Mitwirkende, ODbL
- © GeoBasis-DE/LVGL-SL (2026), dl-de/by-2-0 (ALKIS)
- © GeoBasis-DE/LVermGeoRP (2026), dl-de/by-2-0, www.lvermgeo.rlp.de, Daten bearbeitet (ALKIS)
- © GeoBasis-DE/LVGL-SL (2026), dl-de/by-2-0, Daten bearbeitet (LoD2)
- © GeoBasis-DE/LVermGeoRP (2026), dl-de/by-2-0, www.lvermgeo.rlp.de, Daten bearbeitet (LoD2)
- © GeoBasis-DE/LVGL-SL (2026), dl-de/by-2-0 (DOP20)
- © GeoBasis-DE/LVGL-SL (2026), dl-de/by-2-0, Daten bearbeitet (Historische Karten)
- © GeoBasis-DE/LVermGeoRP (2026), dl-de/by-2-0, www.lvermgeo.rlp.de, Daten bearbeitet (DOP20)
- © GeoBasis-DE/LVGL-SL (2026), dl-de/by-2-0 (DOP20 CIR)
- © GeoBasis-DE/LVermGeoRP (2026), dl-de/by-2-0, www.lvermgeo.rlp.de, Daten bearbeitet (DOP20 RGBI)
- Zensus 2022, © Statistische Ämter des Bundes und der Länder, dl-de/by-2-0, Daten bearbeitet
- Marktstammdatenregister – © Bundesnetzagentur für Elektrizität, Gas, Telekommunikation, Post und Eisenbahnen, dl-de/by-2-0, Daten bearbeitet
- Baumarten: DLR, Tree Species Germany 2022 (Wegler et al. 2025), CC BY 4.0, doi:10.15489/smh8w3j8i962, Daten bearbeitet (umprojiziert)
- GBIF.org (2026-11-08) GBIF Occurrence Search, https://www.gbif.org
- Abgleich Baumarten: Thünen-Institut, Dominant Tree Species for Germany 2017/2018 (Blickensdörfer et al. 2024), CC BY 4.0
- Rekonstruktion Schloss Karlsberg 1789 (Hypothese): Teilprojekt schloss-karlsberg, Katalog v2 (research/01-08)
- Grundrisse teils nach Lageplan 2006, schloss-carlsberg.de (CC BY-SA 2.0 DE)
- Sockeltiefen: DGM1 GeoBasis-DE/LVGL-SL (2026), dl-de/by-2-0
- Koordinaten überwiegend © OpenStreetMap-Mitwirkende (ODbL)
- siehe source je Objekt
- castle-viewer/terrain: DGM1 GeoBasis-DE/LVGL-SL (2026), dl-de/by-2-0, Daten bearbeitet; 1789-Gelände = Hypothese (eigene Arbeit)
