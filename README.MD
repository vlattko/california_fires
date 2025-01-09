## This is Earth engine code for analysis of fire potential in Los Angeles area 2025 fire breakout


In GEE

Load Sentinel‑2 from 2024-09-01 to “now”.
Compute NDVI.
Classify forest (1) vs. shrubland (2).
Calculate simple fire potential = 1 − NDVI.
Export a multi-band TIFF (RGB + classification + fire potential).
Locally

Load the exported TIFF with rasterio.
Load your Sentinel‑3 brightness temperature TIFF.
Threshold the SLSTR data at 50 °C → temp_mask.
Identify high fire-potential areas from the classification → high_fire_potential_mask.
Combine: hot_and_high_fire_risk = temp_mask & high_fire_potential_mask.
Visualize in geemap (or QGIS, etc.).
