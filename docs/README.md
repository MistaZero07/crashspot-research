# Crashspot Research – Progress Log

This document tracks weekly progress for the **Crashspot Research Project** 
(Louisiana statewide crashes + Monroe case study).

---

## Week 1 (Sept 1–7, 2025)
**Focus:** Project setup + crash data foundation

- ✅ Environment set up (Python, QGIS, ArcGIS, repo structure)
- ✅ Downloaded FARS 2022 & 2023 crash data (ACCIDENT.csv)
- ✅ Filtered to Louisiana (STATE=22) → 1,607 crashes
- ✅ Filtered further to Monroe (Ouachita Parish, COUNTY=73) → 60 crashes
- ✅ Cleaned invalid/missing coordinates
- ✅ Saved cleaned GeoJSON outputs:
  - `fars_la_2022_2023.geojson`
  - `fars_monroe_2022_2023_clean.geojson`
- ✅ Produced first interactive Folium map for Monroe crashes
- 📄 Report: `Crashspot_Week1_Report.docx`
- 📊 Workflow diagram: `Week1_Workflow.png`

## 🌍 Live Maps
- [Monroe Fatal Crashes (2022–2023)](https://MistaZero07.github.io/crashspot-research/maps/monroe_fars_2022_2023.html)
- [All Maps Index](https://MistaZero07.github.io/crashspot-research/maps/)



---

## Week 2 (Sept 8–14, 2025)
**Focus:** Cleaning + Exploratory Mapping

✅ Standardized important columns (YEAR, MONTH, DAY, HOUR → numeric)  
✅ Built DATE field for easier grouping  
✅ Cleaned invalid coordinates, confirmed CRS = WGS84 (EPSG:4326)  
✅ Generated summary tables (year, month, hour, county)  
✅ Created bar charts:  
   - Louisiana crashes by month → `la_by_month.png`  
   - Monroe crashes by hour → `monroe_by_hour.png`  
✅ Produced Kernel Density Estimation (KDE) heatmap for Monroe → `monroe_kde.png`  
✅ Added Week 2 starter notebook → `Crashspot_Week2_Starter/Crashspot_Week2_Starter.ipynb`  
📄 Report: [Week 2 Report (PDF)](Crashspot_Week2_Report.pdf)





---

## Week 3 (Sept 15–21, 2025)
**Planned Focus:** Spatial Analysis

- [ ] Apply DBSCAN clustering to crash data
- [ ] Overlay crash clusters with road attributes (surface, speed, lanes)
- [ ] Correlation analysis between crashes and road features

---

## Week 4 (Sept 22–28, 2025)
**Planned Focus:** Model Preparation

- [ ] Engineer features: road type, pavement, traffic density, land use, weather
- [ ] Define target variable (crash occurrence/density)
- [ ] Split into train/test datasets
- [ ] Run baseline models (Logistic Regression, Random Forest)

---

## Week 5 (Sept 29–Oct 5, 2025)
**Planned Focus:** Model Training

- [ ] Tune Random Forest / Gradient Boosting models
- [ ] Evaluate accuracy, precision, recall, AUC
- [ ] Identify top predictive features

---

## Week 6 (Oct 6–12, 2025)
**Planned Focus:** Model Testing + Validation

- [ ] Validate predictions on test set
- [ ] Document errors, limitations, feature importance

---

## Week 7 (Oct 13–19, 2025)
**Planned Focus:** Visualization & Dashboard

- [ ] Build interactive maps with Folium/Kepler.gl
- [ ] Create dashboard-style output (Streamlit or ArcGIS StoryMap)
- [ ] Highlight Monroe hotspots + statewide comparison

---

## Week 8 (Oct 20–31, 2025)
**Planned Focus:** Wrap-up & Reporting

- [ ] Write final research report (methods, results, discussion)
- [ ] Create presentation slides for conference
- [ ] Finalize maps, figures, dashboard
- [ ] Submit project deliverables

---
