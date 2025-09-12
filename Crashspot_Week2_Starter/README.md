# Crashspot – Week 2 Starter

**Focus:** Cleaning + Exploratory Mapping (Louisiana & Monroe)

## Contents
- `Crashspot_Week2_Starter.ipynb` → Main Jupyter notebook for Week 2
- `requirements.txt` → (optional) Python dependencies, same as Week 1 unless extra packages are added

## Goals
- Load cleaned FARS crash data from Week 1 (`fars_la_2022_2023.geojson`, `fars_monroe_2022_2023_clean.geojson`)
- Standardize date/time fields (YEAR, MONTH, DAY, HOUR) and build a DATE column
- Create exploratory summaries (counts by year, month, hour, county)
- Generate bar charts for Louisiana (monthly crashes) and Monroe (hourly crashes)
- Produce a Kernel Density Estimation (KDE) heatmap of Monroe crash hotspots
- Prepare OpenStreetMap road network data for Week 3 analysis

## Outputs
- Figures (PNG) saved in `outputs/figures/`
  - `la_by_month.png`
  - `monroe_by_hour.png`
  - `monroe_kde.png`
- Refined understanding of temporal patterns and hotspot visualization

## Notes
- Data sources are documented globally in `Crashspot_Week1_Starter/data_sources.md`
- Week 2 builds directly on cleaned outputs from Week 1

