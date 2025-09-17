
# Walkability ML

This is a **self‑contained HTML app** that runs entirely in your browser (Chromebook‑friendly). Click any point on the map to:
- Fetch OpenStreetMap data via Overpass for a ~1km radius
- Compute features: intersection density, amenity mix entropy, destination access, transit stops density, sidewalk ratio, crosswalk density
- Produce a **0–100 walkability score** using literature‑informed seed weights (and optional in‑browser retraining via tf.js)
- Generate **cost‑aware improvement suggestions** with rough unit costs

## How to run
1. Download `index.html` from this folder.
2. Double‑click it to open in Chrome. (If Overpass rate‑limits, wait ~30–60s and click again.)
3. Click the map to analyze any area. Use **Use my location** to jump to you.
4. (Optional) Upload a labeled CSV in the Advanced panel to **retrain** the weights.

## CSV schema
`inters_per_km2,amenity_entropy,dest_access,transit_density_per_km2,sidewalk_ratio,crosswalks_per_km2,label`

See `sample_labels.csv` for a toy example (fabricated).

## Notes
- OSM sidewalk/crosswalk tagging varies by city; treat outputs as screening‑level.
- Update unit costs in the script under `UNIT_COSTS` with your local bid tabs for accuracy.
