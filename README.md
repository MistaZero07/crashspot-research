# Crashspot Research (Louisiana & Monroe)

This repository contains the **research pipeline** behind the Crashspot project, 
which visualizes traffic accidents and explores road safety issues in Louisiana, 
with a case study focused on Monroe (Ouachita Parish).

## 📂 Project Structure
```
Crashspot/
  Crashspot_Week1_Starter/   # notebook, requirements, docs
  data_raw/                  # raw data (ignored in git)
  data_clean/                # cleaned datasets (ignored in git)
  outputs/                   # maps & figures (ignored in git)
  docs/                      # reports, workflow diagrams
  scripts/                   # optional scripts
```

## 🗂️ Week 1 Accomplishments
- Set up Python environment & repo structure
- Downloaded FARS 2022 & 2023 crash data
- Filtered to Louisiana (STATE=22) and Monroe (COUNTY=73)
- Cleaned invalid coordinates
- Saved clean GeoJSONs:
  - `fars_la_2022_2023.geojson`
  - `fars_monroe_2022_2023_clean.geojson`
- Generated first interactive map:
  - `outputs/maps/monroe_fars_2022_2023.html`
- Report: `docs/Crashspot_Week1_Report.docx`
- Workflow diagram: `docs/Week1_Workflow.png`

## 🗂️ Week 2 Accomplishments
- Standardized FARS fields (YEAR, MONTH, DAY, HOUR → numeric + DATE column)
- Cleaned invalid coordinates & ensured CRS = WGS84 (EPSG:4326)
- Generated summary tables (year, month, hour, county)
- Produced bar charts:
  - Louisiana crashes by month (`la_by_month.png`)
  - Monroe crashes by hour (`monroe_by_hour.png`)
- Built KDE hotspot heatmap for Monroe (`monroe_kde.png`)
- Saved outputs in `outputs/figures/`
- Added `Crashspot_Week2_Starter.ipynb` notebook
- 📄 Report: [Week 2 Report (PDF)](https://MistaZero07.github.io/crashspot-research/Crashspot_Week2_Report.pdf)

## 🗂️ Week 3 Accomplishments
- Applied DBSCAN clustering on Monroe crashes (2022–2023)  
  - eps = 600 m, min_samples = 3 → 1 cluster detected  
  - Saved results → `data_clean/fars_monroe_clusters.geojson`
- Generated outputs:
  - `outputs/figures/monroe_cluster_sizes.png` → cluster size bar chart
  - [`docs/maps/week3_monroe_clusters.html`](https://MistaZero07.github.io/crashspot-research/maps/week3_monroe_clusters.html) → interactive cluster map
- Loaded Monroe OSM road network (`monroe_roads.geojson`)
- Spatial join: crashes → nearest road segments (~30 m)
  - Saved results → `data_clean/monroe_roads_with_crash_counts.geojson`
  - [`docs/maps/week3_monroe_roads_counts.html`](https://MistaZero07.github.io/crashspot-research/maps/week3_monroe_roads_counts.html) → interactive road crash density map
- Reports:
  - `docs/Crashspot_Week3_Report.pdf`
    

## 📊 Data Sources
- **FARS (Fatality Analysis Reporting System)** — NHTSA  
  [link](https://www.nhtsa.gov/research-data/fatality-analysis-reporting-system-fars)  
- Raw CSVs not included here; place them in `data_raw/`.
