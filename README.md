# AgriSense: Smart Precision Agriculture Using Satellite Remote Sensing and Vegetation Index Analysis

## Overview

AgriSense is a Digital Image Processing project developed for **CS406 – Digital Image Processing** at the **University of Management and Technology (UMT), Lahore**.

The project implements a complete satellite image analysis pipeline for precision agriculture using multispectral Sentinel-derived imagery. The objective is to monitor vegetation health, classify agricultural regions, and detect temporal changes using vegetation indices and classical image processing techniques.

The system was developed entirely in Python using open-source geospatial and image processing libraries.

---

## Student Information

**Name:** Muhammad Asif

**Registration Number:** F2022266062

**Course:** CS406 – Digital Image Processing

**Department:** Computer Science

**University:** University of Management and Technology (UMT), Lahore, Pakistan

**Instructor:** Dr. Jameel Ahmad

---

## Project Objectives

The main objectives of AgriSense are:

* Perform radiometric preprocessing on satellite imagery.
* Analyze vegetation conditions using spectral indices.
* Segment vegetation and land-cover regions.
* Apply morphological operations for mask refinement.
* Detect temporal vegetation changes and potential crop stress.
* Demonstrate practical applications of Digital Image Processing in agriculture.

---

## Dataset

The project uses Sentinel-derived multispectral GeoTIFF imagery covering agricultural regions of Punjab, Pakistan.

### Dataset Components

* TOA Reflectance Image
* BOA Reflectance Image
* DOS-1 Corrected Image
* Cloud Band Image (Date 1)
* Cloud Band Image (Date 2)
* Co-registered Images
* Final Multispectral Analysis Stack

### Image Properties

| Property   | Value       |
| ---------- | ----------- |
| CRS        | EPSG:32642  |
| Resolution | 10 m        |
| Width      | 5003 pixels |
| Height     | 5731 pixels |
| Bands      | 7–10        |

### Spectral Bands Used

| Band | Description         |
| ---- | ------------------- |
| B2   | Blue                |
| B3   | Green               |
| B4   | Red                 |
| B5   | Red Edge            |
| B8   | Near Infrared (NIR) |
| B11  | SWIR1               |
| B12  | SWIR2               |

---

## Technologies Used

### Programming Language

* Python 3.10+

### Libraries

* NumPy
* Pandas
* Rasterio
* Matplotlib
* OpenCV
* Scikit-Image
* Scikit-Learn
* GeoPandas
* Seaborn

---

## Project Pipeline

### Task 1: Data Acquisition & Preprocessing

* GeoTIFF inspection
* TOA analysis
* BOA analysis
* DOS-1 corrected image analysis
* Cloud-band inspection
* RGB composite generation
* Reflectance normalization

### Task 2: Weather-Aware Enhancement

* Contrast stretching
* CLAHE enhancement
* RGB visualization correction
* Histogram analysis

### Task 3: Vegetation Index Computation

The following vegetation indices were computed:

* NDVI
* EVI
* NDWI
* NDRE
* SAVI
* MSAVI

For each index:

* Index map generated
* Histogram generated
* Statistical analysis performed

### Task 4: Image Segmentation

#### Otsu Thresholding

Used to separate vegetation and non-vegetation regions.

#### K-Means Clustering

Performed unsupervised land-cover segmentation using multispectral and vegetation-index features.

#### Morphological Processing

Applied:

* Erosion
* Dilation
* Opening
* Closing

to refine segmentation masks.

### Task 5: Change Detection

Multi-temporal analysis performed using Date 1 and Date 2 cloud-band imagery.

Implemented:

* NDVI comparison
* NDVI change mapping
* Binary change detection
* Crop stress alert mapping

---

## Key Results

### Vegetation Index Statistics

| Index | Mean    |
| ----- | ------- |
| NDVI  | 0.4624  |
| EVI   | 0.3272  |
| NDWI  | -0.4723 |
| NDRE  | 0.1865  |
| SAVI  | 0.3040  |
| MSAVI | 0.2847  |

### NDVI Health Classification

| Class                           | Area (ha)  |
| ------------------------------- | ---------- |
| Water / Non-Vegetation          | 21,202.72  |
| Bare Soil / Very Low Vegetation | 21,465.43  |
| Sparse Vegetation               | 69,282.01  |
| Moderate Vegetation             | 109,648.29 |
| Healthy Dense Vegetation        | 65,123.48  |

### Segmentation Results

* Otsu Thresholding successfully identified vegetation regions.
* K-Means produced five spectral clusters.
* Morphological closing generated the most refined vegetation mask.

### Change Detection

* Multi-date NDVI analysis performed.
* Temporal vegetation differences visualized.
* Crop stress alert maps generated.

---

## Generated Outputs

### Figures

The project generated:

* RGB composites
* Vegetation index maps
* Histograms
* Correlation matrices
* NDVI health maps
* K-Means cluster maps
* Morphological comparison plots
* NDVI change maps
* Crop stress maps

### Tables

Generated tables include:

* Vegetation index statistics
* NDVI health area statistics
* K-Means cluster area statistics
* K-Means cluster interpretation
* Morphological area comparison
* Change detection statistics

---

## Repository Structure

```text
AgriSense/
│
├── notebooks/
│   └── AgriSense_Final.ipynb
│
├── figures/
│
├── tables/
│
├── report/
│   ├── AgriSense_Report.tex
│   └── AgriSense_Report.pdf
│
├── requirements.txt
│
└── README.md
```

---

## How to Run

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Launch Notebook

```bash
jupyter notebook
```

Open:

```text
AgriSense_Final.ipynb
```

and execute all cells sequentially.

---

## Limitations

* Limited overlap existed in provided co-registered images.
* No ground-truth field measurements were available.
* Deep learning segmentation models were not implemented.
* Change detection was performed using available valid multi-date imagery.

---

## Future Work

Future improvements include:

* U-Net semantic segmentation
* SegFormer implementation
* Crop type classification
* Yield prediction
* Time-series monitoring
* Integration with Google Earth Engine

---

## Conclusion

AgriSense demonstrates how Digital Image Processing and satellite remote sensing can be combined to support precision agriculture. Using multispectral imagery, vegetation indices, segmentation techniques, and temporal analysis, the project provides meaningful insights into vegetation health and agricultural monitoring while relying entirely on open-source tools and freely available satellite data.

---

## License

This repository is submitted for academic purposes as part of the requirements of CS406 – Digital Image Processing at UMT Lahore.
