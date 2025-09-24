# Crashspot – Week 4 Starter

**Focus:** Kernel Density Estimation (KDE) Heatmaps & Raster Exports — Monroe & Louisiana

## Objectives
- Select optimal KDE bandwidths for Monroe and Louisiana crash data.
- Generate smooth density rasters of crash hotspots at different spatial scales.
- Compare fine-resolution (Monroe) vs. coarse-resolution (Louisiana) KDEs.
- Produce interactive Folium heatmaps for web-based visualization.
- Export GeoTIFF rasters for use in GIS software (QGIS / ArcGIS).

## Workflow
1. Load cleaned Monroe and Louisiana crash datasets (`fars_monroe_2022_2023_clean.geojson`, `fars_la_2022_2023.geojson`).
2. Run bandwidth selection with **GridSearchCV** → pick KDE smoothing parameters.
3. Generate KDE rasters:
   - Monroe (cell ≈ 120 m, fine grid).
   - Louisiana (cell ≈ 2000 m, coarser grid).
4. Save raster outputs:
   - `kde_monroe_vs_louisiana.png`
   - `la_kde.png`
5. Build interactive Folium heatmaps:
   - `week4_monroe_heatmap.html`
   - `week4_louisiana_heatmap.html`
6. Export GeoTIFF rasters for GIS analysis:
   - `monroe_kde.tif`
   - `la_kde.tif`

## Outputs
- 📓 `Crashspot_Week4_Starter.ipynb` → main notebook.
- 📊 KDE raster images:
  - `docs/figures/kde_monroe_vs_louisiana.png`
  - `docs/figures/la_kde.png`
- 🌍 Interactive heatmaps:
  - `docs/maps/week4_monroe_heatmap.html`
  - `docs/maps/week4_louisiana_heatmap.html`
- 🗺️ GeoTIFFs (optional GIS):
  - `outputs/monroe_kde.tif`
  - `outputs/la_kde.tif`
- 📑 Report:
  - `docs/Crashspot_Week4_Report.pdf`


## Insights
- Monroe KDE reveals a strong concentration of crashes in central Monroe/West Monroe corridors.
- Louisiana KDE shows more dispersed hotspots (Shreveport, Alexandria, Monroe, New Orleans).
- Folium heatmaps provide an interactive way to visually explore density patterns.
- Exported GeoTIFF rasters allow integration with **QGIS/ArcGIS** for spatial overlays with road networks, land use, and traffic data.

---

