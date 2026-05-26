# Republic of the Congo Administrative Divisions / République du Congo



## Overview

| Item | Details |
|------|---------|
| Department | 12 |
| District | 89 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-26 |

## Browse by Department

| # | Department | Districts | Link |
|---|----|----|------|
| 1 | Bouenza | 10 | [Browse](divisions/bouenza-cg01/) |
| 2 | Brazzaville | 1 | [Browse](divisions/brazzaville-cg02/) |
| 3 | Cuvette | 9 | [Browse](divisions/cuvette-cg03/) |
| 4 | Cuvette-Ouest | 6 | [Browse](divisions/cuvette-ouest-cg04/) |
| 5 | Kouilou | 6 | [Browse](divisions/kouilou-cg05/) |
| 6 | Lekoumou | 5 | [Browse](divisions/lekoumou-cg06/) |
| 7 | Likouala | 7 | [Browse](divisions/likouala-cg07/) |
| 8 | Niari | 14 | [Browse](divisions/niari-cg08/) |
| 9 | Plateaux | 11 | [Browse](divisions/plateaux-cg09/) |
| 10 | Point-Noire | 1 | [Browse](divisions/point-noire-cg10/) |
| 11 | Pool | 13 | [Browse](divisions/pool-cg11/) |
| 12 | Sangha | 6 | [Browse](divisions/sangha-cg12/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-department.json](data/all-department.json) | JSON | All 12 department records |
| [all-district.json](data/all-district.json) | JSON | All 89 district records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-department.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-department.json", "utf-8"));
console.log(`Total: ${data.length} departments`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=department, 2=district |
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
divisions/{department-slug}/
```

Districts are listed inline in each department's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-department links
- [Per-department data](docs/llms-full/) — Full data by department

## Citation

```
Republic of the Congo Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/republic-of-the-congo-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [open-admin-data](https://github.com/open-admin-data) — Open administrative data for ASEAN countries
- [thailand-administrative-divisions](https://github.com/open-admin-data/thailand-administrative-divisions) — Thailand dataset
