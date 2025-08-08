# DSWF
Dynamic Surface Water Fraction (DSWF) is a 10-meter global surface water fraction mapping, generated using Sentinel-2 imagery and the Dynamic World dataset.
DSWF is generated on-demand online using Google Earth Engine (GEE) in response to user-defined areas of interest and time. 

# Performance of DSWF
The accuracy of DSWF was evaluated across 113 sample tiles, demonstrating an overall root mean squared error (RMSE) of 0.092 and mean absolute error (MAE) of 0.027 when validated against both pure and mixed pixels.

# Code to access DSWF
DSWF is online calculated using Google Earth Engine (GEE). The code is accessible via the URL: https://code.earthengine.google.com/f5c84b72d6e76355152c61b54af7b9b0.
## Input parameters
  - Area of Interest (AOI)
  - Time range
  - Aggregation scale (default = 5)
  - Sample size (default = 3000)
  Both the aggregation scale and sample size are user-configurable as well.
## Notice
  - An error will occur if the Sentinel-2 image collection is empty for the given AOI and time range.
  - If the AOI spans more than two 1° × 1° grid cells, each block is processed separately, and the resulting water fraction maps are merged into a seamless output.
  - Due to memory constraints within Google Earth Engine (GEE), it is recommended to use an AOI covering fewer than 10 grid cells of size 1° × 1°.

# Validation dataset
## PlanetScope validation dataset (PSVD)
The reference water fraction maps in the PSVD are derived by degrading 3-meter resolution binary water labels annotated from PlanetScope imagery. The original hand-labeled data are collected from the paper "A globally sampled high-resolution hand-labeled validation dataset for evaluating surface water extent maps", and accessible at https://doi.org/10.25739/03nt-4f29.
## Google Earth validation dataset (GEVD)
The reference water fraction maps in the GEVD are derived by degrading 1-meter resolution binary water labels annotated from Google Earth imagery. The reference maps are publicly available for use and accessible at https://doi.org/10.5281/zenodo.16740103.
