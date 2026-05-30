# Traffic Flow Analysis Using Principal Component Analysis (PCA)

![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![RStudio](https://img.shields.io/badge/RStudio-2025-blue?logo=rstudio)
![PCA](https://img.shields.io/badge/Method-PCA-blue?style=for-the-badge)
![Regression](https://img.shields.io/badge/Analysis-Regression-green?style=for-the-badge)
![Time Series](https://img.shields.io/badge/Time%20Series-ARIMA-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
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

<pre>
traffic-analysis-pca/
│
├── README.md
├── LICENSE
├── report.pdf
├── traffic_analysis.Rmd
│
├── data/
│   └── traffic_dataset.csv
│
├── scripts/
│   ├── 01_load_and_clean.R
│   ├── 02_eda.R
│   ├── 03_pca.R
│   ├── 04_regression.R
│   ├── 05_time_series.R
│   └── 06_report.R
│
├── outputs/
│   ├── figures/
│   │   ├── histograms.png
│   │   ├── boxplots.png
│   │   ├── correlation_heatmap.png
│   │   ├── scree_plot.png
│   │   ├── biplot.png
│   │   ├── stl_decomposition.png
│   │   └── arima_forecast.png
│   └── tables/
│       ├── descriptive_stats.csv
│       ├── pca_loadings.csv
│       ├── regression_results.csv
│       └── arima_metrics.csv
│
└── glarus_dashboard/
    ├── dashboard_overview.png
    └── dashboard_config.json
</pre>


---

## 🚀 How to Reproduce

### Prerequisites

Install R and RStudio, then install required packages:

```r
install.packages(c(
    "tidyverse",
    "ggplot2",
    "corrplot",
    "forecast",
    "rmarkdown",
    "knitr",
    "readxl"
))
```
### Steps

1. Clone the repository:
```
git clone https://github.com/your-username/traffic-analysis-pca.git
cd traffic-analysis-pca
```
2. Open traffic_analysis.Rmd in RStudio
3. Click Knit → Select output format (HTML/PDF/Word)
4. The complete report will be generated automatically

### Run Scripts Sequentially (Alternative)
```r
source("scripts/01_load_and_clean.R")
source("scripts/02_eda.R")
source("scripts/03_pca.R")
source("scripts/04_regression.R")
source("scripts/05_time_series.R")
source("scripts/06_report.R")
```

## Sample Visualizations

| Analysis | Visualization |
|----------|---------------|
| **Distributions** | Histograms & boxplots by time of day / season / weather |
| **Correlations** | Pearson correlation heatmap |
| **PCA** | Scree plot & biplot (PC1–PC2) |
| **Regression** | Residual diagnostics plots |
| **Time Series** | STL decomposition & ARIMA forecast |

### Correlation Heatmap
![Correlation Heatmap](outputs/figures/correlation_heatmap.png)

### Scree Plot
![Scree Plot](outputs/figures/scree_plot.png)

### PCA Biplot (PC1–PC2)
![PCA Biplot](outputs/figures/biplot.png)

### ARIMA Forecast vs Actual Values
![ARIMA Forecast](outputs/figures/arima_forecast.png)

### STL Decomposition
![STL Decomposition](outputs/figures/stl_decomposition.png)

> *All figures are automatically generated and included in the final RMarkdown report.*
