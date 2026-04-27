# 🏠 Alicante Housing Market Analysis

> **End-to-end data science project**: from raw web scraping to predictive modelling and statistical inference on the Alicante real estate market.

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://www.python.org/)
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17583274.svg)](https://doi.org/10.5281/zenodo.17583274)

---

## 📌 Overview

This project builds a complete data pipeline to answer the following research question:

> **What factors — size, location, amenities — have the greatest impact on housing prices in Alicante?**

Starting from raw HTML pages on Idealista.com (Spain's leading real estate portal), the project covers every stage of the data science lifecycle: data collection, cleaning, geospatial enrichment, unsupervised exploration, supervised modelling with interpretability, and formal hypothesis testing.

---

## 🔁 Project Pipeline

```
Idealista.com
      │
      ▼
 [1] Web Scraping          → Selenium · 1,802 listings collected
      │
      ▼
 [2] Data Cleaning         → Pandas · outlier handling · missing data imputation
      │
      ▼
 [3] Geospatial Enrichment → geopy · Nominatim (OpenStreetMap) · lat/lon coordinates
      │
      ▼
 [4] Unsupervised Analysis → UMAP · natural cluster identification
      │
      ▼
 [5] Supervised Modelling  → XGBoost + SHAP · feature importance & interpretability
      │
      ▼
 [6] Hypothesis Testing    → Mann-Whitney U · statistical validation
```

---

## 📊 Key Results

| Factor | SHAP Importance | Finding |
|---|---|---|
| Surface area (m²) | 0.31 | Strongest price predictor |
| Latitude | 0.13 | Proximity to coast drives price up |
| Longitude | 0.13 | East-facing locations command premium |
| Elevator | 0.08 | Significant positive effect |
| Sea views | 0.08 | Significant positive effect |

- **Garage**: Mann-Whitney U test (p ≈ 0.000) confirms that listings with a garage are systematically priced higher, independent of other features.
- **UMAP clustering** reveals distinct market segments by property type and geographic zone.
- **Geocodification success rate**: ~87% of listings successfully resolved to lat/lon coordinates via Nominatim.

---

## 🗂️ Repository Structure

```
├── notebooks/
│   ├── 01_scraping.ipynb          # Web scraping with Selenium
│   └── 02_cleaning_analysis.ipynb # Cleaning, modelling, hypothesis testing
├── data/
│   └── README.md                  # Dataset info + Zenodo DOI link
└── requirements.txt
```

---

## 📦 Dataset

The dataset (1,802 listings, 11 variables) is publicly available on Zenodo:

🔗 [https://doi.org/10.5281/zenodo.17583274](https://doi.org/10.5281/zenodo.17583274)

**Variables collected:** title, price, property type, surface area (m²), rooms, floor, agency, garage, sea views, elevator, terrace.

**License:** [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) — attribution required, non-commercial use only.

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Data collection | Python, Selenium, Regex |
| Data processing | Pandas, NumPy |
| Geospatial | geopy, Nominatim (OpenStreetMap) |
| Machine learning | Scikit-learn, XGBoost |
| Interpretability | SHAP |
| Dimensionality reduction | UMAP |
| Statistical testing | SciPy (Mann-Whitney U, Shapiro-Wilk, Levene) |
| Visualisation | Matplotlib, Seaborn |
| Version control | Git, GitHub |

---

## ⚙️ Setup

```bash
git clone https://github.com/jsanjuanj-uoc/alicante-housing-market-analysis.git
cd alicante-housing-market-analysis
pip install -r requirements.txt
```

Then open the notebooks in order:
1. `notebooks/01_scraping.ipynb`
2. `notebooks/02_cleaning_analysis.ipynb`

> ⚠️ The scraper uses Selenium with Chrome. Make sure you have ChromeDriver installed and matching your Chrome version.

---

## 👥 Authors

- **Jordi Sanjuan Jover** — [GitHub](https://github.com/jsanjuanj-uoc) [LinkedIN](https://www.linkedin.com/in/jsanjuanj/) 

*Academic project — Màster en Ciència de Dades, Universitat Oberta de Catalunya (UOC)*
---

## 📄 License

The **code** in this repository is licensed under the [MIT License](https://opensource.org/licenses/MIT).

The **dataset** is published separately on Zenodo under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) — attribution required, non-commercial use only. Original data rights belong to [Idealista.com](https://www.idealista.com).
