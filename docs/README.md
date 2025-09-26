# Crashspot Research – Progress Log

This document tracks weekly progress for the **Crashspot Research Project** 
(Louisiana statewide crashes + Monroe case study).

---

## Week 1 
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

## Week 2 
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

## Week 3 
**Focus:** Spatial Analysis (Clustering + Road Overlay)

✅ Applied DBSCAN clustering on Monroe crashes (2022–2023)  
   • eps = 600 m, min_samples = 3 → 1 cluster detected  
   • Saved results → `data_clean/fars_monroe_clusters.geojson`
✅ Generated outputs:  
   • `outputs/figures/monroe_cluster_sizes.png` → cluster size bar chart  
   • [`docs/maps/week3_monroe_clusters.html`](https://MistaZero07.github.io/crashspot-research/maps/week3_monroe_clusters.html) → interactive cluster map  
✅ Loaded Monroe OSM road network (`monroe_roads.geojson`)  
✅ Spatial join: crashes → nearest road segments (~30 m)  
   • Saved results → `data_clean/monroe_roads_with_crash_counts.geojson`  
   • [`docs/maps/week3_monroe_roads_counts.html`](https://MistaZero07.github.io/crashspot-research/maps/week3_monroe_roads_counts.html) → interactive road crash density map  
✅ Added Week 3 starter notebook → `Crashspot_Week3_Starter/Crashspot_Week3_Starter.ipynb`  
📄 Report: [Week 3 Report (PDF)](Crashspot_Week3_Report.pdf)  


---

### Week 4
**Focus: Kernel Density Estimation (KDE) + Heatmaps**

✅ Selected optimal KDE bandwidths (GridSearchCV + fallbacks)  
✅ Generated KDE rasters for Monroe and Louisiana  
   • Monroe → fine-scale grid (~120 m cells)  
   • Louisiana → coarse-scale grid (~2000 m cells, upsized as needed)  
✅ Produced static raster heatmaps  
   • docs/maps/kde_monroe_vs_louisiana.png  
   • docs/maps/la_kde.png  
✅ Created interactive Folium heatmaps  
   • docs/maps/week4_monroe_heatmap.html  
   • docs/maps/week4_louisiana_heatmap.html  
✅ Exported GeoTIFF rasters for GIS use (QGIS/ArcGIS)  
   • outputs/geotiff/monroe_kde.tif  
   • outputs/geotiff/la_kde.tif  
✅ Added Week 4 starter notebook → `Crashspot_Week4_Starter/Crashspot_Week4_Starter.ipynb`  
📄 Report: [Week 4 Report (PDF)](Crashspot_Week4_Report.pdf)

---

### Week 5
**Focus: Model Preparation + Baseline ML Models**

- ✅ Engineered numeric features  
  - `hour`, `month`, `weekday`, `is_weekend`, `is_night`, `ve_total`, `persons`, `peds`
- ✅ Defined binary target variable:  
  - `target_multiveh` → multi-vehicle crash (1=yes, 0=no)
- ✅ Split dataset into train/test (80/20)
- ✅ Trained baseline models:  
  - Logistic Regression  
  - Random Forest
- ✅ Generated evaluation outputs:  
  - `docs/figures/week5_model_eval.png` → confusion matrices (LR vs RF)  
  - `docs/figures/week5_rf_feature_importance.png` → Random Forest feature importances
- ✅ Saved engineered dataset:  
  - `data_clean/week5_features.csv`
- ✅ Added Week 5 starter notebook:  
  - `Crashspot_Week5_Starter/Crashspot_Week5_Starter.ipynb`
- 📑 Report:  
  - `docs/Crashspot_Week5_Report.pdf`

---

## Week 6
**Focus:** Model enhancement + class imbalance handling + Gradient Boosting

- ✅ Addressed **class imbalance**  
  - Logistic Regression & Random Forest with `class_weight="balanced"`  
  - Applied **SMOTE oversampling** for minority class (when available)  
- ✅ Added **third model**: Gradient Boosting Classifier  
- ✅ Compared models using **validation F1-score**  
  - Best performer: Random Forest (balanced)  
- ✅ Evaluated on test set  
  - Generated **classification report & confusion matrix**  
  - Achieved near-perfect accuracy (small dataset caveat)  
- ✅ Produced evaluation outputs:  
  - `docs/figures/week6_roc.png` → ROC curve (best model)  
  - `docs/figures/week6_pr.png` → Precision–Recall curve (best model)  
  - *(optional)* `docs/figures/week6_val_results.csv` → validation comparison table  
- ✅ Saved artifacts:  
  - `models/week6_best_model.pkl` → serialized best model  
  - `data_clean/week6_features.csv` → engineered dataset snapshot  
- ✅ Added Week 6 starter notebook:  
  - `Crashspot_Week6_Starter.ipynb`  
- 📑 Report:  
  - `docs/Crashspot_Week6_Report.pdf`

---

## Week 7
**Planned Focus:** Visualization & Dashboard

- [ ] Build interactive maps with Folium/Kepler.gl
- [ ] Create dashboard-style output (Streamlit or ArcGIS StoryMap)
- [ ] Highlight Monroe hotspots + statewide comparison

---

## Week 8 
**Planned Focus:** Wrap-up & Reporting

- [ ] Write final research report (methods, results, discussion)
- [ ] Create presentation slides for conference
- [ ] Finalize maps, figures, dashboard
- [ ] Submit project deliverables

---
