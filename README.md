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
- Report: `docs/Crashspot_Week1_Report.pdf`

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
 
## 🗂️ Week 4 Accomplishments
- Selected KDE bandwidths (GridSearchCV + safe defaults)  
  - Monroe → fine resolution (~120 m cells)  
  - Louisiana → coarse resolution (~2000 m cells)  
- Generated KDE raster heatmaps  
  - docs/maps/kde_monroe_vs_louisiana.png → side-by-side comparison  
  - docs/maps/la_kde.png → statewide KDE  
- Built interactive Folium heatmaps  
  - docs/maps/week4_monroe_heatmap.html → Monroe hotspots  
  - docs/maps/week4_louisiana_heatmap.html → Louisiana hotspots  
- Exported GeoTIFF rasters for GIS analysis  
  - outputs/geotiff/monroe_kde.tif  
  - outputs/geotiff/la_kde.tif  
- Reports:  
  - docs/Crashspot_Week4_Report.pdf

## 🗂️ Week 5 Accomplishments
- Engineered features from crash data
  - Temporal: hour, month, weekday, is_weekend, is_night
  - Crash attributes: ve_total, persons, peds
- Defined target variable: target_multiveh (multi-vehicle crash indicator)
- Split into train/test datasets (stratified, 80/20 split)
- Trained baseline models
  - Logistic Regression → accuracy = 1.0, f1 = 1.0
  - Random Forest → accuracy = 1.0, f1 = 1.0
- Generated outputs
  - docs/figures/week5_model_eval.png → confusion matrices
  - docs/figures/week5_rf_feature_importance.png → feature importance chart
  - data_clean/week5_features.csv → engineered features
- Added Crashspot_Week5_Starter.ipynb notebook
- Reports
  - docs/Crashspot_Week5_Report.pdf

## 🗂️ Week 6 Accomplishments
- Addressed class imbalance  
  - Logistic Regression & Random Forest with `class_weight="balanced"`  
  - Applied SMOTE oversampling (when available)
- Added third model: Gradient Boosting Classifier
- Compared models using validation F1-score  
  - Best performer: Random Forest (balanced)
- Evaluated on test set  
  - Generated classification report & confusion matrix  
  - Achieved near-perfect accuracy (small dataset caveat)
- Generated outputs:  
  - docs/figures/week6_roc.png → ROC curve (best model)  
  - docs/figures/week6_pr.png → Precision–Recall curve (best model)  
  - data_clean/week6_features.csv → engineered dataset snapshot  
- Saved artifacts:  
  - models/week6_best_model.pkl → serialized best model  
- Added Crashspot_Week6_Starter.ipynb notebook
- Report:  
  - docs/Crashspot_Week6_Report.pdf

## 🗂️ Week 7 Accomplishments
- Tuned models with hyperparameter optimization
  - Random Forest → RandomizedSearchCV  
  - Gradient Boosting → GridSearchCV  
- Evaluated on test set  
  - Generated classification reports & confusion matrices  
  - Achieved 100% accuracy, precision, recall, and F1 (small dataset caveat)  
- Performed robust validation  
  - tratified 5-Fold Cross-Validation (F1, ROC AUC = 1.000)  
  - shuffle-label test confirmed no leakage  
- Generated outputs:  
  - docs/figures/week7_roc_RF_tuned.png → ROC curve (RF tuned)  
  - docs/figures/week7_pr_RF_tuned.png → Precision–Recall curve (RF tuned)  
  - docs/figures/week7_roc_GB_tuned.png → ROC curve (GB tuned)  
  - docs/figures/week7_pr_GB_tuned.png → Precision–Recall curve (GB tuned)  
- Saved artifacts:  
  - models/week7_best_model.pkl → serialized best model  
- Added Crashspot_Week7_Starter.ipynb notebook  
- Report:  
  - docs/Crashspot_Week7_Report.pdf  

## 🗂️ Week 8 Accomplishments
- Completed **model interpretation** using Permutation Importance  
- Identified **`ve_total` (number of vehicles)** as the strongest predictor of multi-vehicle crashes  
- Exported figure: `docs/figures/week8_permutation_importance.png`  
- Generated **interactive hotspot map**: `docs/maps/week8_predicted_hotspots.html`  
- Confirmed pipeline completion with message: *“Week 8 completed cells ready.”*  

## ✅ Research Phase Completed (Weeks 1–8)
By the end of September, I successfully completed all eight weeks of the Crashspot research pipeline:

- Week 1–4: Data cleaning, feature engineering, clustering, and hotspot analysis  
- Week 5–7: Baseline + tuned machine learning models, evaluation, and comparison  
- Week 8: Model interpretation (feature importance) and spatial integration into interactive maps  

This concludes the **research phase** of Crashspot.  
Next step: transition into an **application/web app** to showcase interactive crash hotspot analysis.


## 📊 Data Sources
- **FARS (Fatality Analysis Reporting System)** — NHTSA  
  [link](https://www.nhtsa.gov/research-data/fatality-analysis-reporting-system-fars)  
