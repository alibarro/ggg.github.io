# Mapping of Mineral Alteration and Principal Component Analysis

![Project overview image](../assets/images/Sentinel-2A-PCA-Dissin-Burkina_Faso.png)

## Overview

This project used Principal Component Analysis (PCA) and band ratio techniques on Sentinel-2A imagery to identify invisible hydrothermal alteration zones and iron oxide signatures in Dissin, Burkina Faso, supporting mineral exploration by revealing surface alteration patterns not visible in standard true-color imagery.

**Study Area:** Dissin, Burkina Faso  
**Duration:** June 2021 – December 2024  
**Role:** Solo project  
**Status:** Completed

---

## Methods & Tools

**Data Sources**

- Sentinel-2A multispectral imagery — Copernicus Open Access Hub

**Processing Steps**

1. Authenticated and initialized the Google Earth Engine (GEE) Python API, and set up supporting libraries (rasterio, matplotlib, psycopg2, sqlalchemy) for raster handling and data storage.
2. Loaded a Sentinel-2A scene over the study area and selected the relevant spectral bands (B1–B12).
3. Mean-centered the imagery across the region of interest to enable an efficient covariance-based PCA.
4. Computed the band-to-band covariance matrix and performed an eigen decomposition to derive eigenvalues and eigenvectors.
5. Projected the centered imagery onto the eigenvectors to generate the Principal Components, normalized by their standard deviations.
6. Calculated targeted mineral indices from raw band ratios and normalized differences, including:
      - Oxide index (B4/B2)
      - Clay/hydroxyl index (B11/B12)
      - Ferrous mineral index (B11/B8)
      - NDVI (vegetation)
      - NDCI (clay)
      - NDII (iron)
      - Carbonate and silica indices
7. Combined indices into composite stacks (mineral stack, ratio composite, ND ratio composite) for integrated visual interpretation.
8. Visualized PCA bands, individual indices, and composite layers on an interactive map (geemap) over a satellite basemap to identify and interpret alteration zones.

**Tools Used**

| Tool | Purpose |
|------|---------|
| Google Earth Engine (GEE) | Cloud-based processing of Sentinel-2A imagery, PCA, and index calculations |
| Python | Scripting the analysis pipeline (ee, geemap, rasterio, matplotlib) |
| Google Colab | Interactive development and execution environment |

---

## Links

[View Code on GitHub](https://github.com/alibarro/ggg.github.io){ .md-button }
[View Data Source](https://dataspace.copernicus.eu/){ .md-button }