# Traffic Flow Analysis Using Principal Component Analysis (PCA)

![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![PCA](https://img.shields.io/badge/Method-PCA-blue?style=for-the-badge)
![Regression](https://img.shields.io/badge/Analysis-Regression-green?style=for-the-badge)
![Time Series](https://img.shields.io/badge/Time%20Series-ARIMA-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

## Overview

This project was completed as a **coursework** at **RTU MIREA** (Institute of Information Technologies, Applied Mathematics Department). The goal is to develop a complete analytical pipeline for identifying latent factors influencing road traffic intensity using **Principal Component Analysis (PCA)**.

The work covers the full data analysis lifecycle:
- Exploratory Data Analysis (EDA)
- Dimensionality reduction with PCA
- Regression on principal components
- Time series forecasting (ARIMA)
- Automated report generation (RMarkdown)
- Interactive dashboard design (Glarus BI)

---

## Objectives

| # | Task |
|---|------|
| 1 | Perform EDA and visualize distributions of traffic, weather, and temporal features |
| 2 | Conduct correlation analysis to justify PCA application |
| 3 | Apply PCA to reduce dimensionality and extract latent factors |
| 4 | Build regression models on original features and principal components |
| 5 | Forecast daily traffic volume using ARIMA |
| 6 | Automate reporting with RMarkdown (HTML/PDF/Word) |
| 7 | Design an interactive dashboard in Glarus BI |

---

## Key Results

### Principal Components

| Component | Interpretation | Variance Explained |
|-----------|----------------|--------------------|
| **PC1** | Road load factor (traffic volume + speed) | ~32% |
| **PC2** | Weather conditions (cloud cover + visibility) | ~18% |
| **PC3** | Precipitation intensity (rain + wind) | ~14% |
| **Total** | 3 components | **~64%** |

### Regression Comparison

| Model | R² | Multicollinearity |
|-------|----|--------------------|
| Original features (OLS) | ~0.88 | Present (inflated by load_factor) |
| Regression on PCs | ~0.64 | **Eliminated** ✓ |

### Time Series Forecasting

- **Model:** ARIMA with automatic parameter selection
- **Training:** First 4 years of daily data
- **Test:** Last year
- **MAE:** Comparable to series standard deviation

---

## Tools & Technologies

| Category | Tools |
|----------|-------|
| **Language** | R |
| **Data Manipulation** | tidyverse, dplyr, readr |
| **Visualization** | ggplot2, corrplot |
| **Statistical Analysis** | stats (PCA, regression, hypothesis testing) |
| **Time Series** | forecast (ARIMA, STL decomposition) |
| **Reporting** | RMarkdown, knitr |
| **BI Platform** | Glarus BI (interactive dashboards) |

---

## Repository Structure
