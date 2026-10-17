<p align="center">
  <img src="docs/assets/logo.svg" alt="QuarkGIS logo" width="96">
</p>

<h1 align="center">QuarkGIS</h1>

<p align="center">
  <b>Open, edit and share real QGIS projects in your browser, rendered by QGIS itself.</b><br>
  Nothing to install and no server: your projects and data stay on your machine,
  and what you save opens unchanged in QGIS Desktop.
</p>

<p align="center">
  <a href="https://github.com/ismailsunni/quarkgis/actions/workflows/test.yml"><img alt="Tests" src="https://github.com/ismailsunni/quarkgis/actions/workflows/test.yml/badge.svg"></a>
  <img alt="Built on qgis-js" src="https://img.shields.io/badge/built%20on-qgis--js-589632?style=flat-square">
  <img alt="License: GPL-2.0-or-later" src="https://img.shields.io/badge/license-GPL--2.0--or--later-2563eb?style=flat-square">
  <img alt="5 languages" src="https://img.shields.io/badge/languages-5-0e9384?style=flat-square">
</p>

<p align="center">
  <a href="https://ismailsunni.id/quarkgis/"><img alt="Launch the web app" src="https://img.shields.io/badge/Launch-web%20app-589632?style=for-the-badge&logo=webassembly&logoColor=white" height="36"></a>
  <a href="https://ismailsunni.id/quarkgis/docs/"><img alt="Read the documentation" src="https://img.shields.io/badge/Read-the%20docs-0e9384?style=for-the-badge&logo=materialformkdocs&logoColor=white" height="36"></a>
</p>

<p align="center">
  <img src="docs/assets/screenshots/app.png" alt="QuarkGIS with the Natural Earth demo project: the layer tree on the left, the world map drawn by QGIS in the Equal Earth projection, and the map tools on the right" width="100%">
</p>

## Why QuarkGIS

- **It is QGIS.** QuarkGIS runs QGIS core compiled to WebAssembly ([qgis-js](https://github.com/qgis/qgis-js)), so symbols, labels and projections look exactly as in QGIS Desktop.
- **Your projects, unchanged.** It opens `.qgs` / `.qgz` projects and edits them in QGIS's own format. What you save opens in Desktop with nothing lost or converted.
- **Nothing to install.** A web page: open a project folder, a file, or a link. In Chrome and Edge, Save writes back to your own files, like a desktop app.
- **Private.** Files are read in the browser and nothing is uploaded. The network is used only for the web layers and catalogs you add, and for links you publish.
- **The common 80%, simply.** Style, label, query, edit, analyse and print a map, with sensible defaults, an action search for everything and a short tour. The long tail of QGIS stays in Desktop.
- **Web-native.** Share a link that opens at your view, embed a map, add satellite imagery and open data from public catalogs, show your location on a phone.

## A tour

<table>
<tr>
<td width="50%" valign="top"><img src="docs/assets/screenshots/style.png" alt="The Style panel with a graduated style on population" width="100%"><p align="center"><sub><b>Styling.</b> Single, categorized, graduated (with QGIS's own breaks), rule-based, heatmap and clusters; labels, popups and QML.</sub></p></td>
<td width="50%" valign="top"><img src="docs/assets/screenshots/table.png" alt="The attribute table with African countries selected on the map and in the table" width="100%"><p align="center"><sub><b>Attributes.</b> A fast table with QGIS expressions, selection synced with the map, statistics, field calculator and joins.</sub></p></td>
</tr>
<tr>
<td width="50%" valign="top"><img src="docs/assets/screenshots/editing.png" alt="Editing: moving a selected country with the edit toolbar" width="100%"><p align="center"><sub><b>Editing.</b> Add, reshape, move, rotate, split, merge and explode, with snapping, QGIS forms and undo, written to the GeoPackage.</sub></p></td>
<td width="50%" valign="top"><img src="docs/assets/screenshots/catalog.png" alt="The open data panel with Sentinel-2 results over Jakarta and one image on the map" width="100%"><p align="center"><sub><b>Open data.</b> Search Sentinel-2, elevation and public data portals, and add the results to the map.</sub></p></td>
</tr>
<tr>
<td width="50%" valign="top"><img src="docs/assets/screenshots/profile.png" alt="An elevation profile drawn across a DEM" width="100%"><p align="center"><sub><b>Map tools.</b> Measure, elevation profiles, swipe compare, grid, bookmarks, location, and PNG or PDF export.</sub></p></td>
<td width="50%" valign="top"><img src="docs/assets/screenshots/time.png" alt="The time slider playing dated points month by month" width="100%"><p align="center"><sub><b>Time.</b> A time slider driven by the layers' QGIS temporal settings.</sub></p></td>
</tr>
<tr>
<td width="50%" valign="top"><img src="docs/assets/screenshots/processing.png" alt="The Processing panel with the buffer algorithm" width="100%"><p align="center"><sub><b>Processing.</b> Buffer, clip, intersection, union, dissolve, joins by location and more, with outputs matching QGIS Desktop.</sub></p></td>
<td width="50%" valign="top"><img src="docs/assets/screenshots/properties.png" alt="Layer properties showing a layer's information" width="100%"><p align="center"><sub><b>Layer properties.</b> Information, a provider filter, field aliases, joins, scale ranges and metadata, as in QGIS.</sub></p></td>
</tr>
</table>

## Features

| Area | Highlights |
| --- | --- |
| **Projects** | Open `.qgs` / `.qgz` files and folders, GeoPackages with an embedded project, projects by URL and published links. Save back to your files (Chrome, Edge), in the browser, or download a `.qgz` or a `.zip` with the data. Undo for every change, autosave and crash recovery, missing data located by following the project's paths |
| **Data** | GeoPackage, GeoJSON, Shapefile, FlatGeobuf, GeoParquet, GeoTIFF, KML, GPX, CSV, Excel and MBTiles. XYZ, WMS, WMTS, WFS, OGC API Features and Tiles, ArcGIS REST, vector tiles, PMTiles and COG. STAC catalogs and CKAN data portals. A basemap gallery and the QGIS Hub |
| **Cartography** | Rendered by QGIS in any CRS. Single, categorized, graduated (equal interval, quantile, natural breaks, pretty, standard deviation, manual), rule-based, heatmap and cluster renderers; labels; raster pseudocolor, hillshade and RGB with histograms; scale ranges; QML import and export |
| **Attributes** | Attribute table with QGIS expressions and an expression builder; selection by click, shape, expression and location; statistics; field calculator and field management; QGIS attribute forms; joins |
| **Editing** | Add, edit vertices, move, rotate, split, merge, explode, delete; snapping; copy and paste between layers; written to GeoPackage with undo |
| **Analysis** | 18 QGIS algorithms with GEOS (buffer, clip, difference, intersection, union, dissolve, join by location, merge, reproject…), checked against Desktop; elevation profiles; measuring |
| **Map** | View history, place and coordinate search, coordinates in decimal, DMS, UTM and MGRS, a grid, bookmarks, legend, map tips, swipe and side-by-side compare, time slider, your location |
| **Sharing** | Links that open at a view, published maps (GitHub gists) with versions and secrets removed, embedding with a postMessage API, PNG and PDF map export |
| **Interface** | Action search (Ctrl+K), keyboard shortcuts, a welcome tour, dark mode, phone layout, English, German, French, Spanish and Indonesian |

The [user guide](https://ismailsunni.id/quarkgis/docs/getting-started/) covers each area, [data formats](https://ismailsunni.id/quarkgis/docs/data-formats/) lists what opens, edits and exports, and the [comparison](docs/feature-comparison.md) sets QuarkGIS beside GeoLibre and RustGIS.

## Get started

Open **[ismailsunni.id/quarkgis](https://ismailsunni.id/quarkgis/)** in a recent desktop Chrome, Edge or Firefox, then open a project folder, a project file, or try the demo. The QGIS engine (about 20 MB) is downloaded once and cached.

Open a project from the web with `?url=`, for example [the demo project](https://ismailsunni.id/quarkgis/?url=projects/world/world.qgz). See [Sharing and embedding](https://ismailsunni.id/quarkgis/docs/guide/sharing/) for links, published maps and the embed API.

To host it yourself, build the static site (below) and serve `dist/` with `Cross-Origin-Opener-Policy: same-origin` and `Cross-Origin-Embedder-Policy: require-corp`, or keep the bundled service worker that adds them.

## Development

```sh
npm install
npm run dev        # http://localhost:5173
npm run check      # svelte-check / TypeScript
npm test           # unit tests (Vitest)
npm run test:e2e   # Playwright: renders compared with QGIS Desktop, round-trips, features
npm run build      # static site in dist/
```

Built with Vite, TypeScript, Svelte 5, OpenLayers, qgis-js (QGIS 4.2), SQLite WebAssembly, GEOS WebAssembly and proj4. The [development guide](https://ismailsunni.id/quarkgis/docs/development/) has the code map, tests, generated assets and how to add a translation.

## How it works

The open project is kept as its QGIS XML: every change is written into it and QGIS reloads it, so the map is always what Desktop will show. QGIS renders the map; web tiles and images it can't fetch yet are drawn by OpenLayers in their place in the layer stack. Edits are SQL on the GeoPackage with the official SQLite WebAssembly build, processing runs in GEOS (the library behind QGIS's native algorithms), and CRS definitions come from QGIS's own database. More in [How it works](https://ismailsunni.id/quarkgis/docs/how-it-works/), including the current limitations.

## License and credits

QuarkGIS is free software under the [GNU General Public License v2.0 or later](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html), like QGIS.

It stands on [QGIS](https://qgis.org) and [qgis-js](https://github.com/qgis/qgis-js), [OpenLayers](https://openlayers.org), [GEOS](https://libgeos.org), [SQLite](https://sqlite.org), [PROJ](https://proj.org) and [proj4js](https://github.com/proj4js/proj4js), [geotiff.js](https://geotiffjs.github.io), [Svelte](https://svelte.dev) and [Zensical](https://zensical.org). The demo uses [Natural Earth](https://www.naturalearthdata.com) data. QuarkGIS is an independent project, not an official QGIS.ORG product.
