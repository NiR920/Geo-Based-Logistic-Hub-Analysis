# Data Source

## Source

The submitted report identifies the source as Kaggle's **Real World Logistic Data** dataset by Pushpit Kamboj (2022).

Source recorded in the report:

https://www.kaggle.com/datasets/pushpitkamboj/logistics-data-containing-real-world-data

## Dataset size

The report describes the source dataset as:

- **15,549 observations**
- **41 variables**

## Variables used in the analysis

| Variable | Role in the project |
|---|---|
| `customer_id` | Customer identifier for RFM aggregation |
| `order_country` | Destination country / geographic validation |
| `order_city` | Destination city / geographic analysis |
| `sales` | Monetary value for RFM analysis |
| `order_date` | Recency calculation |
| `sales_per_customer` | Examined during feature selection |
| `order_item_product_price` | Examined during feature selection |
| `latitude` | Geographic coordinate |
| `longitude` | Geographic coordinate |

## Data-quality observations reported

The report states that no empty values or outliers were found during its checks. It did, however, identify mismatches between order city and order country and used geocoding to correct country information.

## Data handling policy

The raw Kaggle dataset is not stored in this repository. This avoids unnecessarily redistributing third-party data and keeps the repository lightweight.

If the analysis is reproduced, download the dataset from its original source and keep the local data files outside version control. Any Google Maps credentials used for geocoding must remain local and must never be committed.
