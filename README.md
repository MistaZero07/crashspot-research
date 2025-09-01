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

## 🚀 Next Steps
- Week 2: deeper cleaning + heatmaps (KDE)
- Week 3: clustering (DBSCAN) + overlay with road data (OSM)
- Later: predictive modeling & visualization dashboards

## 📊 Data Sources
- **FARS (Fatality Analysis Reporting System)** — NHTSA  
  [link](https://www.nhtsa.gov/research-data/fatality-analysis-reporting-system-fars)  
- Raw CSVs not included here; place them in `data_raw/`.
