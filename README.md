# MA-GeoAI Research Data Repository

## 📊 Overview

This folder contains research datasets used in the paper **"MA-GeoAI: A Multi-Agent Autonomous GIS Framework for Scalable and Self-Improving Geospatial Intelligence"** by Kim-Son Nguyen and The-Vinh Nguyen.

All datasets are provided for research reproducibility and are referenced in the paper as supplementary materials for references [27], [28], and [29].

## 📁 Dataset Inventory

### Case Study 1: Population Exposure Analysis (North Carolina)
**Reference:** [27] U.S. Census Bureau: TIGER/Line Shapefiles

| File | Size | Description | Format |
|------|------|-------------|--------|
| `HW_Sites_EPSG4326.zip` | 249 KB | 89 hazardous waste sites in North Carolina | Shapefile (EPSG:4326) |
| `tract_37_EPSG4326.zip` | 18 MB | 15,847 census tracts in North Carolina | Shapefile (EPSG:4326) |
| `NC_tract_population.csv` | 157 KB | Population data by census tract | CSV |

**Purpose:** Quantify population within 1-mile buffer around hazardous sites

**Original Source:** U.S. Census Bureau TIGER/Line Shapefiles  
https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html

---

### Case Study 2: COVID-19 Mobility Analysis (France)
**Reference:** [28] INSEE: International developments - Effects of the crisis

| File | Size | Description | Format |
|------|------|-------------|--------|
| `France.zip` | 66 KB | Time-series mobility data during lockdown periods | Shapefile/CSV |

**Purpose:** Analyze temporal changes in mobility during COVID-19 lockdown and visualize outcomes using multi-panel plots

**Original Source:** Institut national de la statistique et des études économiques (INSEE), Orange Flux Vision data  
https://www.insee.fr/en/statistiques/fichier/4769648/point-conj%20080920-effets-crise.pdf

---

### Case Study 3: COVID-19 Mortality Analysis (US Counties)
**Reference:** [29] CDC National Center for Health Statistics

| File | Size | Description | Format |
|------|------|-------------|--------|
| `us-counties-2020.csv` | 35 MB | COVID-19 cases and deaths by US county (2020) | CSV |
| `contiguous_counties.zip` | 850 KB | Shapefile of 3,142 contiguous US counties | Shapefile |
| `ACS2020_5year_county.csv` | 1.7 MB | Demographic indicators from ACS 2020 5-year estimates | CSV |

**Purpose:** Examine correlations between death rates and demographic indicators across 3,142 U.S. counties

**Original Sources:**
- COVID-19 Data: NY Times COVID-19 Data Repository
- Shapefile: U.S. Census Bureau
- Demographics: American Community Survey (ACS) 2020

---

## 🔬 Usage in Research

These datasets are used in the experimental validation section of the MA-GeoAI paper to demonstrate:

1. **Scalability:** Multi-agent system handling large-scale geospatial datasets
2. **Automation:** Autonomous GIS workflow without manual intervention
3. **Accuracy:** Reproducible results with validated geospatial analysis

## 📝 Data Format Specifications

### Shapefiles (.zip)
- Coordinate System: EPSG:4326 (WGS 84)
- Format: ESRI Shapefile compressed in ZIP
- Components: .shp, .shx, .dbf, .prj files

### CSV Files
- Encoding: UTF-8
- Delimiter: Comma (,)
- Header: First row contains column names

## 🔄 Data Updates

**Last Updated:** October 29, 2025

These datasets are static snapshots used for research reproducibility. For the most current data, please refer to the original sources listed above.

## 📖 Citation

If you use these datasets in your research, please cite:

```bibtex
@article{nguyen2025mageoai,
  title={MA-GeoAI: A Multi-Agent Autonomous GIS Framework for Scalable and Self-Improving Geospatial Intelligence},
  author={Nguyen, Kim-Son and Nguyen, The-Vinh},
  journal={[Journal Name]},
  year={2025},
  note={Data available at: https://github.com/Nguyen-Kim-Son/langgraph/raw/main/data}
}
```

## 🔗 Related Resources

- **Research Paper:** [Link to paper when published]
- **Code Repository:** https://github.com/Nguyen-Kim-Son/langgraph
- **Jupyter Notebook:** `Multi_agent_DeepSeek.ipynb`

## ⚖️ License and Attribution

These datasets are aggregated from publicly available sources for academic research purposes. Please refer to original data sources for specific licensing terms:

- **U.S. Census Bureau data:** Public domain
- **INSEE data:** Check INSEE usage terms
- **NY Times COVID data:** CC BY-NC-SA 4.0
- **ACS data:** Public domain

## 📧 Contact

For questions about the datasets or research:

- **Kim-Son Nguyen** - nkson@ictu.edu.vn
- **The-Vinh Nguyen** - vinhnt@ictu.edu.vn

Thai Nguyen University of Information and Communication Technology  
Department of Information Systems / Software Engineering  
Thai Nguyen, Vietnam

---

**Note:** This README is generated to support the research paper submission and data reproducibility requirements.
