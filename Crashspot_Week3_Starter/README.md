# Crashspot – Week 3 Starter

**Focus:** Spatial Clustering (DBSCAN) + Road Overlay (OSM) — Monroe, LA

## Objectives
- Detect spatial clusters of fatal crashes in Monroe (2022–2023) using DBSCAN
- Summarize cluster sizes and visualize hotspots
- Overlay crashes onto Monroe’s road network
- Compute crash counts per road segment
- Produce interactive maps and figures for analysis

## Workflow
1. Load cleaned Monroe crashes from Week 1 (`fars_monroe_2022_2023_clean.geojson`)
2. Project to UTM 15N (EPSG:32615) for accurate distance calculations
3. Apply DBSCAN (`eps = 600 m`, `min_samples = 3`) to identify clusters
4. Save clustered results to `data_clean/fars_monroe_clusters.geojson`
5. Generate:
   - `monroe_cluster_sizes.png` → cluster size bar chart
   - `week3_monroe_clusters.html` → interactive cluster map
6. Load Monroe OSM roads (`monroe_roads.geojson`)
7. Clip roads to Monroe extent and join crashes to road segments
8. Save `monroe_roads_with_crash_counts.geojson`
9. Generate `week3_monroe_roads_counts.html` → interactive road crash density map

## Outputs
- `Crashspot_Week3_Starter.ipynb` — Week 3 notebook
- `data_clean/fars_monroe_clusters.geojson` — clustered crash points
- `outputs/figures/monroe_cluster_sizes.png` — cluster size chart
- `docs/maps/week3_monroe_clusters.html` — interactive cluster map
- `data_clean/monroe_roads_with_crash_counts.geojson` — road segments with crash counts
- `docs/maps/week3_monroe_roads_counts.html` — interactive roads crash map

## Insights
- Monroe has relatively **sparse fatal crashes**, with only one hotspot cluster detected
- Road overlay reveals which **road segments** are associated with more fatal crashes
- Together, this supports identifying roadway safety interventions

---
