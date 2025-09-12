# Crashspot — Data Sources Log

## Accident Data
- **Source name**: Fatality Analysis Reporting System (FARS) 
- **URL / access method**: https://www.nhtsa.gov/file-downloads?p=nhtsa/downloads/FARS/
- **Spatial coverage / years**: Nationwide, 2022–2023 (filtered to Louisiana + Monroe)
- **Format**: CSV converted to GeoJSON
- **Fields of interest**: latitude, longitude, YEAR, MONTH, DAY, HOUR, severity, county, state
- **License / usage notes**: Public, US government dataset (free to use)
- **Last updated**: Downloaded Sept 2025

## Road Network / Conditions (OSM prep for Week 3)
- **Source name**: (OpenStreetMap / City public works / DOT pavement)
- **URL / access method**: 
- **Attributes available**: surface, lanes, lighting, speed limit, etc.
- **Format**: 
- **License / usage notes**: 
- **Last updated**: 

## Environmental / Context (future if needed)
- **Traffic counts**: 
- **Land use**: 
- **Weather**: 
- **Other**: 

## Processing Notes
- **CRS used**: WGS84 (EPSG:4326)
- **Cleaning steps**:
  Filtered to STATE=22 (Louisiana)
  Filtered to COUNTY=73 (Ouachita / Monroe subset)
  Removed null or invalid coordinates
  Saved as cleaned GeoJSONs
- **Known caveats**:
  FARS covers fatal crashes only (not all accidents)
  OSM road attributes vary in completeness
