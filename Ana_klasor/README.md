#  ERA5 Wind Extreme Analysis (Marmara Region)

##  Project Overview

This project performs a comprehensive **extreme wind analysis** using ERA5 reanalysis data. The workflow integrates meteorological data processing, statistical modeling, and spatial analysis to estimate **wind risk metrics**, including **return levels** and **extreme event frequencies**.

The primary goal is to identify high-risk wind مناطق (zones) in the Marmara region and quantify their statistical behavior for applications such as:

* Offshore & marine operations
* Wind energy assessment
* Risk and hazard analysis

---

##  Methodology

### 1. Data Processing

* Multi-file ERA5 NetCDF datasets
* Grid alignment using nearest-neighbor reindexing
* Time-series concatenation

### 2. Wind Speed Calculation

Wind speed is derived from 10m wind components:

[ U = \sqrt{u_{10}^2 + v_{10}^2} ]

---

### 3. Temporal Analysis

* Monthly averages
* Seasonal means
* Annual maxima (block maxima method)

---

### 4. Extreme Value Analysis

Two approaches are used:

#### 🔹 Gumbel Approximation

* Based on mean and standard deviation
* Provides quick estimation of return levels

#### 🔹 Generalized Extreme Value (GEV)

* Fitted using Maximum Likelihood Estimation
* Applied spatially across all grid points

Return level formula:

[ RL_T = F^{-1}(1 - 1/T) ]

where (T) is the return period.

---

### 5. Spatial Risk Analysis

* 50-year return wind speed map
* Extreme wind zones (threshold-based)
* Seasonal extreme mapping

---

### 6. Frequency Analysis

* Probability of exceeding thresholds (e.g., 12, 15, 20 m/s)
* Expressed as percentage occurrence over time

---

### 7. Point-Based Analysis

* Identification of maximum-risk grid point
* Return level curve generation
* Observed vs modeled extremes comparison

---

### 8. Uncertainty Quantification

* Bootstrap resampling
* 95% confidence interval estimation for return levels

---

##  Key Outputs

*  Spatial 50-year return wind map
*  Return level curves (log-scale)
*  Extreme wind hotspot detection
*  Threshold exceedance frequency maps

---

##  Key Skills Demonstrated

* Xarray & multi-dimensional data processing
* Climate data handling (ERA5)
* Extreme Value Theory (GEV modeling)
* Parallel computation (Dask)
* Scientific visualization (Matplotlib, Cartopy)
* Statistical uncertainty analysis (Bootstrap)

---

##  Limitations

* Limited to ~30 years of data (affects long return period reliability)
* Block maxima assumes independence
* Fixed thresholds (not percentile-based)

---


##  Tech Stack

* Python
* Xarray
* NumPy
* SciPy
* Matplotlib
* Cartopy

---

##  Data Source

* ERA5 Reanalysis Dataset (ECMWF)

---

##  Author

Meteorology Engineering Student
Focused on atmospheric modeling, data analysis, and extreme weather risk assessment

---

##  How to Run

```bash
pip install xarray numpy pandas scipy matplotlib cartopy netcdf4
```

```bash
python analysis.py
```
Data Availability: Due to GitHub file size limits, the full 30-year dataset is not included in this repository. You can download the ERA5 dataset from the Copernicus Climate Data Store.
---

##  Notes

This project is designed as a **portfolio-level scientific analysis** suitable for applications in:

* Wind energy companies
* Marine meteorology
* Risk modeling & insurance
* Climate data science

