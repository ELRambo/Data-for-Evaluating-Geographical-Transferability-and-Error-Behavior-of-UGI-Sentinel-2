# Data-for-Evaluating-Geographical-Transferability-and-Error-Behavior-of-UGI-Sentinel-2

# Urban Green Infrastructure Reference Labels

This repository contains semi-automated urban green infrastructure (UGI) reference labels and supporting materials developed for the study:

**Evaluating Geographical Transferability and Error Behavior of Urban Green Infrastructure Segmentation across Climate-Stratified Domains Using Sentinel-2 Data**

## Overview

The study evaluates the geographical transferability of Sentinel-2 UGI segmentation models across five climate-stratified environmental domains.

The dataset comprises 75 cities, with 15 cities in each domain. Within each domain, 10 cities were allocated to model training and five were reserved for held-out evaluation.

UGI was defined as vegetated land cover within the urban study extent that could be represented at the 10 m Sentinel-2 mapping scale, including tree canopy, grass, shrubs, and other vegetated surfaces.

The reference labels were generated semi-automatically using Sentinel-2 imagery, vegetation and water indices, and building-footprint information.

## Repository Contents

| File | Description |
|------|-------------|
| `UGI_reference_labels.zip` | Archive containing the semi-automated UGI reference labels. |
| `city_and_thresholds.xlsx` | Spreadsheet containing city-level information and the NDVI thresholds used for reference-label generation. |
| `links_to_gee_scripts.txt` | Links to the Google Earth Engine scripts associated with data preparation and reference-label generation. |
| `README.md` | Documentation for the repository and dataset. |

## Environmental Domains

The cities were grouped into five environmental domains:

- A: Tropical
- B: Arid
- C: Temperate
- D: Continental
- E: High-latitude cold environments

Domains A–D follow the Köppen–Geiger climate classification. Domain E is a study-defined high-latitude grouping that includes polar-climate cities and selected high-latitude temperate and continental cities.

## Reference-Label Generation

The reference labels were generated from Sentinel-2 Level-2A surface-reflectance imagery.

Sentinel-2 observations acquired between January 2019 and December 2020 were combined into a two-year median composite for each city.

Vegetation was identified using city-specific Normalized Difference Vegetation Index (NDVI) thresholds. The thresholds were parameterized using the city-level NDVI mean and standard deviation and selected through visual assessment of the resulting vegetation masks.

Water surfaces were excluded using the Normalized Difference Water Index (NDWI), and building footprints were used as an auxiliary mask to reduce vegetation labels associated with mapped buildings.

The resulting binary reference labels represent UGI and non-UGI at the 10 m Sentinel-2 mapping scale.

The city-specific NDVI thresholds are documented in `city_and_thresholds.xlsx`.

## Accessing the Data

Download and extract `UGI_reference_labels.zip` to access the reference-label files.

The spreadsheet `city_and_thresholds.xlsx` provides supporting information for interpreting the city-level labels.

Links to the associated Google Earth Engine scripts are provided in `links_to_gee_scripts.txt`.

Access to Google Earth Engine may require a Google account and an appropriately configured Earth Engine project.

## Important Considerations

The reference labels were generated semi-automatically and should not be interpreted as independently verified ground truth.

Their accuracy may vary among cities because of differences in vegetation characteristics, urban morphology, image conditions, and the limitations of threshold-based classification.

At the 10 m Sentinel-2 scale, individual pixels may contain mixtures of UGI and non-UGI surfaces. Assigning a single binary class to these pixels simplifies their underlying land-cover composition.

Users should consider these limitations when using the labels for model training, evaluation, or geographical-transfer experiments.

## Citation

If you use these reference labels in your research, please cite the associated study:

Zhang, J. *Evaluating Geographical Transferability and Error Behavior of Urban Green Infrastructure Segmentation across Climate-Stratified Domains Using Sentinel-2 Data.*
