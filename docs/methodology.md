# Methodology

## Data Sources

- **OCHA COD-AB Côte d'Ivoire** (CC BY-IGO) — 33 regions, 108 departments, 510 sub-prefectures with P-codes and centroid coordinates

## Processing

1. Administrative records from OCHA COD-AB XLSX gazetteer
2. Coordinates from OCHA centroid data (100% coverage)
3. Multi-format export: JSON, NDJSON, CSV

## Important Notes

- Côte d'Ivoire does not have an area-based postal code system (uses BP/boîte postale)
- French is the official language; place names are the same in French and English

## Accuracy

- Coordinates: 100% at all levels
- Names: 100% at all levels (French)
- Build script is idempotent: same input always produces same output