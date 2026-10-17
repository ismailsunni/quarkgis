# Development

The source is on [GitHub](https://github.com/ismailsunni/quarkgis), under GPL-2.0-or-later like QGIS.

## Setup

```sh
npm install
npm run dev        # http://localhost:5173 (the dev server sets COOP/COEP headers)
npm run check      # svelte-check / TypeScript
npm test           # unit tests (Vitest)
npm run test:e2e   # Playwright: reference renders, round-trip, features
npm run build      # static site in dist/
```

Stack: Vite, TypeScript, Svelte 5, OpenLayers, qgis-js 4.2.3 (pinned), SQLite WASM, GEOS WASM, proj4.

## Code map

| Path | What |
| --- | --- |
| `src/lib/doc.ts` | The project XML document, loading it in QGIS, saving |
| `src/lib/map.ts` | The OpenLayers map: QGIS render layers and browser-drawn web layers |
| `src/lib/style.ts`, `raster.ts` | Renderers, labels, classification, QML |
| `src/lib/editing.ts`, `editmap.ts`, `editops.ts` | Feature editing on GeoPackages |
| `src/lib/processing.ts` | Algorithms (GEOS) |
| `src/lib/remote.ts` | Web layers: data sources, capabilities, downloads |
| `src/lib/actions.ts` | Opening/saving, identify, the action search |
| `src/lib/localfs.ts`, `relocate.ts` | Projects linked to local files, allowed folders, unavailable layers |
| `src/lib/catalog.ts` | Open data catalogs (STAC, CKAN) |
| `src/lib/viewlink.ts`, `navigation.ts`, `geolocate.ts` | Links to a view, view history and grid, location |
| `src/lib/printmap.ts` | PDF map page |
| `src/lib/joins.ts`, `temporal.ts` | QGIS joins and temporal settings |
| `src/i18n/*.json` | Translations |
| `src/components/` | The UI (Svelte) |
| `tests/` | Unit and end-to-end tests, reference projects |
| `scripts/` | Generated assets and checks against QGIS Desktop |

## Generated assets

Run with QGIS Desktop's Python, e.g. `QT_QPA_PLATFORM=offscreen PYTHONPATH=/usr/share/qgis/python python3 …`:

| Script | Output |
| --- | --- |
| `scripts/make_demo_project.py` | `public/projects/world` demo (Natural Earth) |
| `scripts/make_templates.py` | Empty project, default symbols and label settings |
| `scripts/make_functions.py` | Expression function list for the builder |
| `scripts/make_reference_projects.py` | 10 reference projects and their Desktop renders |
| `scripts/check_roundtrip.py` | Verifies projects saved by the round-trip test in Desktop |
| `scripts/compare_processing.py` | Compares processing outputs with Desktop's algorithms |

`node scripts/hub-mirror.mjs` mirrors the QGIS Hub into `public/hub` (hub.qgis.org doesn't send CORS headers; the deploy refreshes it weekly).

## Continuous integration

`.github/workflows/test.yml` runs the unit tests, the Playwright suite, and the Desktop round-trip check in the `qgis/qgis` container. Pushes to `main` deploy the app and this documentation to GitHub Pages; a service worker (`public/sw.js`) provides cross-origin isolation there and caches the engine.

## Tests

- **Unit tests** (Vitest) cover parsers, classification breaks (checked against QGIS's), coordinates and statistics.
- **End-to-end tests** (Playwright) open ten reference projects and compare the renders with QGIS Desktop's pixel by pixel, save projects and check them in QGIS Desktop (in the `qgis/qgis` Docker image, on CI), and exercise the features.
- `scripts/compare_processing.py` runs the same algorithms in QGIS Desktop and compares the outputs.

## Translations

The UI text is English; translations live in `src/i18n/<code>.json`, keyed by the English text. To add or update a language:

```sh
node scripts/i18n-keys.mjs           # coverage per language
node scripts/i18n-keys.mjs --write   # add new keys (empty) to every language file
```

Fill in the empty values, keeping `{placeholders}` as they are, and add the language to `LANGUAGES` in `src/lib/i18n.ts` for a new one.

## Documentation

This site is built with [Zensical](https://zensical.org) from `docs/`:

```sh
pip install zensical
zensical serve                               # http://localhost:8000
node scripts/docs-screenshots.mjs <app-url>  # refresh the screenshots
```

It is published with the app, at `/quarkgis/docs/`.
