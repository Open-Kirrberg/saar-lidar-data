# Saar LiDAR Explorer – Daten (Teil 1)

Static data for the [Saar LiDAR Explorer](https://open-kirrberg.github.io/saar-lidar-explorer/) (code: https://github.com/Open-Kirrberg/saar-lidar-explorer), served by GitHub Pages at https://open-kirrberg.github.io/saar-lidar-data/.

> **Schauen, nicht graben.** Everything here is terrain data and *hypotheses*, not finds. Archaeological sites are protected (Saarländisches Denkmalschutzgesetz SDschG, Denkmalschutzgesetz Rheinland-Pfalz DSchG). No digging, no metal detecting; report finds to the Landesdenkmalamt.

## Contents

| Path | What |
|---|---|
| `overall/` | AOI „Homburg / Kirrberg / Karlsberg“: `manifest.json`, height chunks (Terrarium PNG), relief layers, overview levels, DOM, orthophoto, historic maps, LoD2 buildings, OSM ways, ALKIS parcels, point clouds, relict candidates, place statistics *Orte im Vergleich* (`stats/places.json`, `stats/places.geojson`: aggregates per Gemarkung / Gemeinde, estimates as ranges) the historic forest mask (`forest_hist/`, an estimate from the 1935–40 map symbols) and the tree species layer (`species/`, DLR 10 m classes, an estimate). Format: `docs/data-contract.md` in the code repository. The Leaflet tiles (`xyz`) are in the second data repository (https://open-kirrberg.github.io/saar-lidar-data-2/), referenced by absolute URLs in the manifest. |
| `saarland/` | Stats-only AOI „Saarland – Gemeinden im Vergleich“ (no terrain, `kind: 'stats-only'`): `manifest.json`, `stats/places.geojson`, `stats/places.json` — level `gemeinde` of the leaderboard *Orte im Vergleich*, aggregates per Gemeinde, estimates as ranges. |
| `pois.geojson` | Known sites („Bekannte Orte“), WGS84. |
| `shared/karlsberg1789/` | Hypothetical reconstruction of Schloss Karlsberg, summer 1789 (light model for the explorer). |
| `castle-viewer/terrain/` | 1 m terrain crops (2025 DTM and the 1789 terrain hypothesis) used to build the castle viewer; `SHA256SUMS`. |
| `zones/` | Zone packages the explorer enters through a portal (`index.json`, format `docs/zone-contract.md`): `schloss-karlsberg/` (reconstruction 1789: zone manifest, 1789 terrain, texture sets) and `baeckerei-heusser/` (built twin of the bakery, shown with the owners' permission). |

## Relict candidates (`overall/candidates/`)

The 3276 *Verdachtsflächen* are the output of an **automatic, unverified** terrain-shape detector (pits, mounds, ditches, rectangular structures, platforms). They are **hypotheses, not verified sites**: most are natural forms, modern disturbances, tracks or noise. Nobody has checked them in the field. They are published for looking and learning only — **not** as a guide for digging, probing or detector use.

## Licences and attribution

The code is MIT-licensed (see the code repository). **The data keep their own licences:**

- Geobasisdaten Saarland (LVGL-SL: DGM1/DOM1/ALS points, DOP20, LoD2, ALKIS, historic maps) and Rheinland-Pfalz (GeoBasis-DE/LVermGeoRP): **Datenlizenz Deutschland – Namensnennung – Version 2.0** (dl-de/by-2-0, https://www.govdata.de/dl-de/by-2-0). All products here are processed („Daten bearbeitet“).
- Place statistics (`overall/stats/`) also use the **Zensus 2022** 100 m grid (© Statistische Ämter des Bundes und der Länder) and the **Marktstammdatenregister** (© Bundesnetzagentur), both dl-de/by-2-0, processed. They are aggregates per place, never per parcel, building or person.
- Tree species (`overall/species/`, and the species / age values in `stats/`): **DLR EOC, Tree Species Germany 2022** (Wegler et al. 2025, doi:10.15489/smh8w3j8i962), **CC BY 4.0**, Daten bearbeitet (umprojiziert). The species cross-check numbers in the manifest (`species.crossCheck`, no pixels): **Thünen-Institut, Dominant Tree Species for Germany 2017/2018 (Blickensdörfer et al. 2024, doi:10.3220/DATA20221214084846)**, **CC BY 4.0**. *Artenvielfalt* in `stats/places.json`: counts from the **GBIF** occurrence search (GBIF.org; records CC0 / CC BY 4.0 / CC BY-NC 4.0, incl. iNaturalist), no records or species names.
- Leaderboard level `saarland/stats/`: aggregates per Gemeinde only, never per parcel, building, tree or person. Inputs: Verwaltungsgebiete 1:25 000 (VG25), Gemeindegrenzen (BKG, CC-BY-4.0); Zensus 2022, Regionaltabelle Bevölkerung (Gemeinden) (Destatis, dl-de/by-2-0); Baumarten Deutschland 2022 (DLR, Sentinel-1/-2, 10 m) (DLR, CC-BY-4.0); Marktstammdatenregister, Solareinheiten (BNetzA, dl-de/by-2-0); GBIF-Fundmeldungen (nur Anzahlen je Gemeinde) (GBIF, CC0-1.0 / CC-BY-4.0 / CC-BY-NC-4.0 (je Datensatz)); 3D-Gebäudemodell LoD2 Saarland (LVGL-SL, dl-de/by-2-0); 3D-Gebäudemodell LoD2 Rheinland-Pfalz (LVermGeoRP, dl-de/by-2-0); Laserscanning DGM1/DOM1 Saarland (ALS 2025) (LVGL-SL, dl-de/by-2-0); DGM1/DOM1 Rheinland-Pfalz (LVermGeoRP, dl-de/by-2-0). Outlines: **BKG VG25** (© BKG, https://www.bkg.bund.de, **CC BY 4.0**, https://creativecommons.org/licenses/by/4.0/), Daten verändert: parts dissolved per AGS, simplified to 50 m.
- OpenStreetMap data (ways, most POI coordinates): **ODbL 1.0** (https://opendatacommons.org/licenses/odbl/), © OpenStreetMap-Mitwirkende.
- Reconstruction 1789 (`shared/karlsberg1789/`): own work (hypothesis); building footprints partly derived from the Lageplan 2006 by schloss-carlsberg.de („Mannlich“), **CC BY-SA 2.0 DE** — these derived geometries are shared under CC BY-SA 2.0 DE.
- Relief visualisations, candidates, levels and encodings: derived from the data above (same licences).
- Castle zone textures (`zones/schloss-karlsberg/textures/`): Poly Haven (https://polyhaven.com), **CC0 1.0**, downscaled. Bäckerei Heusser (`zones/baeckerei-heusser/`): the bakery's name, lettering, product texts and prices are shown with the owners' permission and are not licensed for reuse.

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
- © BKG (2026) CC BY 4.0 (Daten verändert), Datenquellen: https://sgx.geodatenzentrum.de/web_public/gdz/datenquellen/datenquellen_vg25.pdf (VG25)
- Rekonstruktion Schloss Karlsberg 1789 (Hypothese): Teilprojekt schloss-karlsberg, Katalog v2 (research/01-08)
- Grundrisse teils nach Lageplan 2006, schloss-carlsberg.de (CC BY-SA 2.0 DE)
- Sockeltiefen: DGM1 GeoBasis-DE/LVGL-SL (2026), dl-de/by-2-0
- Koordinaten überwiegend © OpenStreetMap-Mitwirkende (ODbL)
- siehe source je Objekt
- castle-viewer/terrain: DGM1 GeoBasis-DE/LVGL-SL (2026), dl-de/by-2-0, Daten bearbeitet; 1789-Gelände = Hypothese (eigene Arbeit)
