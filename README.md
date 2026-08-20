# Brazil Administrative Divisions / Brasil



## Overview

| Item | Details |
|------|---------|
| State | 27 |
| Municipality | 5,572 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-20 |
| Website | [openadmindata.org/br](https://openadmindata.org/br/) |
| API | [openadmindata.org/api/br](https://openadmindata.org/api/br/) |
| Flag | [PNG](https://onlygames.me/flags-png/br/) · [SVG](https://onlygames.me/flags-svg/br/) · [PDF](https://onlygames.me/flags-pdf/br/) |
| National Anthem | [🎵 Listen & Download Brazil National Anthem MP3](https://onlygames.me/national-anthems/br/) |

## Browse by State

| # | State | Municipalitys | Link |
|---|----|----|------|
| 1 | Rondônia (Rondonia) | 52 | [Browse](divisions/rondonia-br11/) |
| 2 | Acre | 22 | [Browse](divisions/acre-br12/) |
| 3 | Amazonas | 62 | [Browse](divisions/amazonas-br13/) |
| 4 | Roraima | 15 | [Browse](divisions/roraima-br14/) |
| 5 | Pará (Para) | 144 | [Browse](divisions/para-br15/) |
| 6 | Amapá (Amapa) | 16 | [Browse](divisions/amapa-br16/) |
| 7 | Tocantins | 139 | [Browse](divisions/tocantins-br17/) |
| 8 | Maranhão (Maranhao) | 217 | [Browse](divisions/maranhao-br21/) |
| 9 | Piauí (Piaui) | 224 | [Browse](divisions/piaui-br22/) |
| 10 | Ceará (Ceara) | 184 | [Browse](divisions/ceara-br23/) |
| 11 | Rio Grande do Norte | 167 | [Browse](divisions/rio-grande-do-norte-br24/) |
| 12 | Paraíba (Paraiba) | 223 | [Browse](divisions/paraiba-br25/) |
| 13 | Pernambuco | 185 | [Browse](divisions/pernambuco-br26/) |
| 14 | Alagoas | 102 | [Browse](divisions/alagoas-br27/) |
| 15 | Sergipe | 75 | [Browse](divisions/sergipe-br28/) |
| 16 | Bahia | 417 | [Browse](divisions/bahia-br29/) |
| 17 | Minas Gerais | 853 | [Browse](divisions/minas-gerais-br31/) |
| 18 | Espírito Santo (Espirito Santo) | 78 | [Browse](divisions/espirito-santo-br32/) |
| 19 | Rio de Janeiro | 92 | [Browse](divisions/rio-de-janeiro-br33/) |
| 20 | São Paulo (Sao Paulo) | 645 | [Browse](divisions/sao-paulo-br35/) |
| 21 | Paraná (Parana) | 399 | [Browse](divisions/parana-br41/) |
| 22 | Santa Catarina | 295 | [Browse](divisions/santa-catarina-br42/) |
| 23 | Rio Grande do Sul | 499 | [Browse](divisions/rio-grande-do-sul-br43/) |
| 24 | Mato Grosso do Sul | 79 | [Browse](divisions/mato-grosso-do-sul-br50/) |
| 25 | Mato Grosso | 141 | [Browse](divisions/mato-grosso-br51/) |
| 26 | Goiás (Goias) | 246 | [Browse](divisions/goias-br52/) |
| 27 | Distrito Federal | 1 | [Browse](divisions/distrito-federal-br53/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-state.json](data/all-state.json) | JSON | All 27 state records |
| [all-municipality.json](data/all-municipality.json) | JSON | All 5,572 municipality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-state.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['municipality']} municipalitys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-state.json", "utf-8"));
console.log(`Total: ${data.length} states`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=state, 2=municipality |
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
divisions/{state-slug}/
```

Municipalitys are listed inline in each state's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-state links
- [Per-state data](docs/llms-full/) — Full data by state

## Citation

```
Brazil Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/brazil-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
