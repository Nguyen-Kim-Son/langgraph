# MA-GeoAI Reproducibility Repository (Data + Logs + Notebook)

## Overview
This repository provides the **data references**, **execution notebook(s)**, and **reproducibility artifacts** (run logs and example outputs) used in the paper:

**“Multi-Agent Autonomous GeoAI Framework for Scalable and Self-Improving Geospatial Intelligence.”**

It is intended to support transparent reruns and auditing of the reported GIS experiments under a controlled protocol (Google Colab; fixed seeds; artifact-based logging).

## Repository contents (what to look for)
- `data/` — dataset files and/or dataset references used in the three case studies (see “Dataset Inventory” below).
- `notebooks/` — the Colab notebook used to execute the multi-agent GIS pipeline (two-phase protocol).
- `logs/` — reproducibility artifacts exported from experiments:
  - `runs_*.csv` (per-run outcomes, artifact checks, runtime, fallback indicator)
  - `codegen_cost_*.csv` (Phase-A API calls and token usage for cost accounting)
- `artifacts/` — a small subset of representative HTML/PNG outputs (e.g., seed=0) to verify the expected artifact contract without uploading all per-seed outputs.

> **Protocol note (as reported in the paper):** the experiments follow a **two-phase evaluation protocol**:
> Phase A performs one-time code generation per (system, case) and caches the produced program; Phase B executes cached programs for fixed seeds (0–9) without additional LLM calls.  
> The final benchmark grid is 5 systems × 3 cases × 10 seeds = 150 end-to-end runs.

---

## Dataset Inventory

### Case Study 1: Population Exposure Analysis (North Carolina)
**Reference:** U.S. Census Bureau TIGER/Line Shapefiles

| File | Size | Description | Format |
|------|------|-------------|--------|
| `HW_Sites_EPSG4326.zip` | 249 KB | Hazardous waste sites in North Carolina | Shapefile (EPSG:4326) |
| `tract_37_EPSG4326.zip` | 18 MB | Census tracts in North Carolina | Shapefile (EPSG:4326) |
| `NC_tract_population.csv` | 157 KB | Population by census tract | CSV |

**Purpose:** Quantify population within a 1-mile buffer around hazardous sites.

**Original Source (upstream):**  
https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html

---

### Case Study 2: Mobility Pattern Analysis (France)
**Reference:** INSEE / Orange Flux Vision mobility indicators (see upstream reference)

| File | Size | Description | Format |
|------|------|-------------|--------|
| `France.zip` | 66 KB | Administrative boundaries and a reproducible mobility proxy/template input | Shapefile/CSV |

**Purpose:** Produce monthly mobility change visualization (matrix + trend line + interactive December map).

**Reproducibility policy:** In the reported experiments, a **proxy/template (including optional synthetic generation)** is used to avoid dependence on intermittently unavailable upstream endpoints in Colab, while preserving the artifact contract and enabling stable auditing across seeds.

**Original Source (upstream reference):**  
https://www.insee.fr/en/statistiques/fichier/4769648/point-conj%20080920-effets-crise.pdf

---

### Case Study 3: County-level Mortality Modeling (US)
**Reference:** CDC National Center for Health Statistics (NCHS) provisional deaths by county (as cited in the paper)

| File | Size | Description | Format |
|------|------|-------------|--------|
| `us-counties-2020.csv` | 35 MB | County-level mortality/case table used for joins and rate computation | CSV |
| `contiguous_counties.zip` | 850 KB | Shapefile of contiguous US counties | Shapefile |
| `ACS2020_5year_county.csv` | 1.7 MB | Demographic indicators (ACS 2020 5-year) | CSV |

**Purpose:** Join mortality and demographic covariates, compute death-rate, and visualize choropleth + association plot.

**Original sources (upstream references):**
- CDC provisional deaths by county (paper-cited reference; see manuscript bibliography)
- County boundaries: U.S. Census Bureau
- Demographics: American Community Survey (ACS) 2020

> Note: This repository stores a **research snapshot** used to reproduce the reported experiments; for the most current data, consult upstream sources.

---

## How the data are used in the paper
These datasets support tool-based GIS workflows that stress common failure modes (CRS mismatch, geometry validity, schema drift, missingness, and external-service instability). The evaluation is audited via per-run logs, explicit artifact checks, and cost-separated reporting (Phase-A code generation vs. Phase-B seeded execution).

## Data format specifications
### Shapefiles (`.zip`)
- CRS: EPSG:4326 (WGS 84) unless otherwise stated
- ESRI Shapefile components: `.shp`, `.shx`, `.dbf`, `.prj`

### CSV files
- Encoding: UTF-8
- Delimiter: comma (`,`)
- Header: first row contains column names

## Updates
**Last Updated:** October 29, 2025  
This repository contains static snapshots used for reproducibility.

## Citation
If you use these materials, please cite the paper (currently under review/submission) and this repository URL:
https://github.com/Nguyen-Kim-Son/langgraph

## License and attribution
These datasets are aggregated from publicly available sources for academic research purposes. Please consult upstream licensing terms:
- U.S. Census Bureau data: Public domain
- INSEE: check INSEE usage terms
- CDC data: check CDC usage terms
- ACS data: Public domain

## Contact
- Kim-Son Nguyen — nkson@ictu.edu.vn  
- The-Vinh Nguyen — vinhnt@ictu.edu.vn
