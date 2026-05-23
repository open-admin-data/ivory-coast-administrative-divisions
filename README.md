# Ivory Coast Administrative Divisions / Côte d&#39;Ivoire

Open dataset of Ivory Coast's (Côte d'Ivoire) administrative hierarchy — 33 regions, 108 departments, and 510 sub-prefectures. French reference data with geographic coordinates at every level. Designed for developers, researchers, government agencies, and AI agents.

Licensed under CC-BY-4.0. Browse the hierarchy through GitHub's folder navigation, download aggregate files in JSON/CSV/NDJSON, or integrate directly via raw URLs.

## Overview

| Item | Details |
|------|---------|
| Region | 33 |
| Department | 108 |
| Sub-prefecture | 510 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-23 |

## Browse by Region

| # | Region | Departments | Sub-prefectures | Link |
|---|----|----|----|------|
| 1 | Agneby-Tiassa | 4 | 19 | [Browse](divisions/agneby-tiassa-ci03/) |
| 2 | Bafing | 3 | 15 | [Browse](divisions/bafing-ci04/) |
| 3 | Bagoue | 3 | 14 | [Browse](divisions/bagoue-ci05/) |
| 4 | Belier | 4 | 15 | [Browse](divisions/belier-ci06/) |
| 5 | Bere | 3 | 9 | [Browse](divisions/bere-ci07/) |
| 6 | Bounkani | 4 | 17 | [Browse](divisions/bounkani-ci08/) |
| 7 | Cavally | 4 | 17 | [Browse](divisions/cavally-ci09/) |
| 8 | District Autonome D&#39;Abidjan | 1 | 5 | [Browse](divisions/district-autonome-dabidjan-ci01/) |
| 9 | District Autonome De Yamoussoukro | 2 | 4 | [Browse](divisions/district-autonome-de-yamoussoukro-ci02/) |
| 10 | Folon | 2 | 7 | [Browse](divisions/folon-ci10/) |
| 11 | Gbeke | 4 | 20 | [Browse](divisions/gbeke-ci11/) |
| 12 | Gbokle | 2 | 9 | [Browse](divisions/gbokle-ci12/) |
| 13 | Goh | 2 | 16 | [Browse](divisions/goh-ci13/) |
| 14 | Gontougo | 5 | 29 | [Browse](divisions/gontougo-ci14/) |
| 15 | Grands Ponts | 3 | 10 | [Browse](divisions/grands-ponts-ci15/) |
| 16 | Guemon | 4 | 23 | [Browse](divisions/guemon-ci16/) |
| 17 | Hambol | 3 | 19 | [Browse](divisions/hambol-ci17/) |
| 18 | Haut-Sassandra | 4 | 23 | [Browse](divisions/haut-sassandra-ci18/) |
| 19 | Iffou | 3 | 15 | [Browse](divisions/iffou-ci19/) |
| 20 | Indenie-Djuablin | 3 | 14 | [Browse](divisions/indenie-djuablin-ci20/) |
| 21 | Kabadougou | 5 | 15 | [Browse](divisions/kabadougou-ci21/) |
| 22 | Loh-Djiboua | 3 | 17 | [Browse](divisions/loh-djiboua-ci22/) |
| 23 | Marahoue | 3 | 18 | [Browse](divisions/marahoue-ci23/) |
| 24 | Me | 4 | 17 | [Browse](divisions/me-ci24/) |
| 25 | Moronou | 3 | 11 | [Browse](divisions/moronou-ci25/) |
| 26 | N&#39;Zi | 3 | 10 | [Browse](divisions/nzi-ci27/) |
| 27 | Nawa | 4 | 11 | [Browse](divisions/nawa-ci26/) |
| 28 | Poro | 4 | 27 | [Browse](divisions/poro-ci28/) |
| 29 | San Pedro | 2 | 11 | [Browse](divisions/san-pedro-ci29/) |
| 30 | Sud-Comoe | 4 | 17 | [Browse](divisions/sud-comoe-ci30/) |
| 31 | Tchologo | 3 | 12 | [Browse](divisions/tchologo-ci31/) |
| 32 | Tonkpi | 5 | 33 | [Browse](divisions/tonkpi-ci32/) |
| 33 | Worodougou | 2 | 11 | [Browse](divisions/worodougou-ci33/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 33 region records |
| [all-department.json](data/all-department.json) | JSON | All 108 department records |
| [all-sub_prefecture.json](data/all-sub_prefecture.json) | JSON | All 510 sub-prefecture records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['department']} departments")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=department, 3=sub-prefecture |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{region-slug}/
divisions/{region-slug}/{department-slug}/
```

Sub-prefectures are listed inline in each department's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Ivory Coast Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/ivory-coast-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [open-admin-data](https://github.com/open-admin-data) — Open administrative data for ASEAN countries
- [thailand-administrative-divisions](https://github.com/open-admin-data/thailand-administrative-divisions) — Thailand dataset
