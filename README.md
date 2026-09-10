# Predictive Loyalty Modeling and Geo-Based Logistic Hub Optimization

A data-driven logistics analytics project that combines **RFM customer loyalty modeling** with **geospatial K-Means clustering** to identify high-value customer concentrations and suggest potential locations for future logistics hubs.

> **Project type:** Data mining, customer analytics, geospatial analysis, and logistics network planning  
> **Primary language:** Python  
> **Dataset:** Real World Logistic Data (Kaggle)  
> **Authors:** Md Nazmul Islam Razib and Md Ariful Ahsan

## Overview

Efficient logistics planning requires understanding both **where demand is concentrated** and **which customers create the greatest business value**. This project connects those two perspectives.

The workflow first uses **Recency, Frequency, and Monetary (RFM)** metrics to segment customers without requiring a pre-existing loyalty label. K-Means clustering is then used to identify the customer segment interpreted in the report as the loyal-customer group. Orders associated with those customers are subsequently geocoded and clustered geographically to identify central areas that may serve as candidates for future logistics hub expansion or regional marketing.

The submitted report is preserved in this repository as the primary record of the project.

## Research Objective

The project investigates how customer loyalty patterns can be combined with geographic information to support logistics hub planning.

The analytical questions addressed by the report are:

1. How can customer purchasing behavior be transformed into meaningful RFM loyalty segments?
2. How can the geographic distribution of loyal customers be clustered to identify potential logistics hub areas?
3. How can the resulting geographic patterns support logistics expansion and regional business decisions?

## Methodology

The project follows this analytical pipeline:

```text
Logistics Dataset
       │
       ▼
Data Exploration & Validation
       │
       ├── Missing/inconsistent-value checks
       └── Geographic validation
       │
       ▼
RFM Feature Engineering
       │
       ├── Recency  → time since latest order
       ├── Frequency → number of orders
       └── Monetary → total sales
       │
       ▼
Feature Scaling
       │
       ▼
K-Means Customer Segmentation
       │
       └── k selected using clustering diagnostics
       │
       ▼
Loyal Customer Segment
       │
       ▼
Geocoded Order Locations
       │
       ▼
Geographic K-Means Clustering
       │
       ├── Elbow analysis
       └── Silhouette analysis
       │
       ▼
Potential Hub Centroids
       │
       ▼
Maps & Business Interpretation
```

## Dataset

The report uses the **Real World Logistic Data** dataset published on Kaggle. The source is documented in the report as:

https://www.kaggle.com/datasets/pushpitkamboj/logistics-data-containing-real-world-data

The reported dataset contains **15,549 observations and 41 variables**. The analysis focuses on customer, order, sales, and geographic fields including:

- `customer_id`
- `order_country`
- `order_city`
- `sales`
- `order_date`
- `sales_per_customer`
- `order_item_product_price`
- `latitude`
- `longitude`

The report describes checks for missing values, outliers, and inconsistencies between order city and country. Google Maps geocoding was used to validate/correct country information and obtain geographic information for the analysis.

## Key Analytical Results

According to the submitted report:

- **28 customers** were identified as belonging to the customer cluster interpreted as the loyal segment.
- Customer loyalty was modeled using **Recency, Frequency, and Monetary value**.
- Customer features were standardized before K-Means clustering.
- **k = 2** was selected for the customer clustering based on the reported silhouette analysis, with a silhouette score above 0.9.
- Loyal-customer orders produced **57 unique customer–city combinations** for the subsequent geographic analysis.
- Geographic clustering identified **k = 3** as the preferred number of clusters for loyal-customer locations.
- The reported silhouette score for the geographic clustering at **k = 3 was 0.6663**.
- Cluster centroids were interpreted as **potential logistics hub candidates**, rather than as confirmed optimal facility locations.

The report gives example dominant locations associated with the three geographic clusters: **Kars, Aurangabad, and Managua**.

## Tools & Technologies

The report identifies the following tools and Python libraries:

- Python
- pandas
- NumPy
- scikit-learn
- googlemaps
- Folium
- Plotly
- Matplotlib
- Seaborn

The analysis uses K-Means clustering, feature scaling, silhouette analysis, elbow analysis, geocoding, and geographic visualization.

## Repository Structure

```text
Geo-Based-Logistic-Hub-Analysis/
├── README.md
├── LICENSE
├── CITATION.cff
├── requirements.txt
├── docs/
│   ├── README.md
│   ├── methodology.md
│   ├── data-source.md
│   ├── analysis.md
│   └── quality-assurance.md
├── analysis/
│   └── README.md
├── data/
│   └── README.md
├── results/
│   ├── README.md
│   └── figure-index.md
└── Md Nazmul Islam Razib_Md Ariful Ahsan.pdf
```

The repository intentionally does **not** claim to contain source notebooks or raw data that are not currently available in the project archive. The documentation describes the analysis from the submitted report and provides a clear structure for adding reproducible source files if they become available.

## Results & Visualizations

The report contains eleven numbered figures covering:

1. Correlation of all variables
2. Description of the selected variables
3. Correlation of sales-related variables
4. Customer-clustering diagnostics
5. RFM cluster distributions
6. Customer counts by cluster
7. Optimal k analysis for store-location centroids
8. Store-location centroids
9. Optimal geographic cluster analysis for loyal cities
10. Geographic clustering of loyal customers
11. Predicted new logistics hub points based on customer-loyalty geoclustering

The figure index in [`results/figure-index.md`](results/figure-index.md) records the role and location of each figure in the submitted report.

## Important Scope Note

This project identifies **potential hub areas from clustered loyal-customer locations**. It is not a full facility-location optimization model. The reported centroids should therefore be interpreted as data-driven candidate locations that could support further logistics planning, rather than as final investment decisions.

## Reproducibility

The submitted report is the authoritative record of the completed analysis. The repository is structured so that the original analysis code, notebooks, and non-sensitive data-processing artifacts can be added later without changing the documented analytical interpretation.

For API-based geocoding, credentials should always be supplied through local environment configuration and **must not be committed to GitHub**.

## Documentation

- [`docs/methodology.md`](docs/methodology.md) — analytical methodology and workflow
- [`docs/data-source.md`](docs/data-source.md) — dataset provenance and variables
- [`docs/analysis.md`](docs/analysis.md) — RFM and geographic analysis details
- [`docs/quality-assurance.md`](docs/quality-assurance.md) — review notes and known limitations
- [`results/figure-index.md`](results/figure-index.md) — figure-by-figure index

## Authors

**Md Nazmul Islam Razib**  
Department of Microdata Analysis, Högskolan Dalarna, Borlänge, Sweden

**Md Ariful Ahsan**  
Department of Microdata Analysis, Högskolan Dalarna, Borlänge, Sweden

## Academic Record

**Title:** *Predictive Loyalty Modeling and Geo-Based Logistic Hub Optimization*

The original submitted report is retained in the repository as:

`Md Nazmul Islam Razib_Md Ariful Ahsan.pdf`

## License

This repository is released under the MIT License. See [`LICENSE`](LICENSE).
