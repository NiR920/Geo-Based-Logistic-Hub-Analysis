# Methodology

## 1. Data exploration

The submitted report describes a logistics dataset with 15,549 observations and 41 variables. Initial exploration checked the dataset structure, missing values, outliers, and consistency of geographic fields.

## 2. Geographic validation

The report identifies mismatches between `order_city` and `order_country`. Google Maps geocoding was used to validate and correct country information based on city names. A short delay between API calls was used to respect rate limits.

Because geocoding requires an API credential, any future implementation should load the key from an environment variable or another local secret store. Credentials must not be committed to the repository.

## 3. RFM feature engineering

Customer loyalty was represented using three RFM measures:

- **Recency:** calculated from the order date relative to the latest order date in the dataset.
- **Frequency:** number of orders associated with each customer.
- **Monetary:** total sales value associated with each customer.

The report selected `sales` as the monetary indicator after examining its relationship with other sales-related variables.

## 4. Customer segmentation

The RFM variables were standardized using a StandardScaler before K-Means clustering. The report states that dimensionality reduction was not required because only three RFM variables were used.

The report's customer-clustering analysis selected **k = 2** based on the reported silhouette analysis. The resulting clusters contained 15,491 and 28 customers, respectively. The smaller, higher-RFM cluster was interpreted as the loyal-customer segment.

## 5. Geographic clustering

Orders associated with the loyal-customer segment were filtered and geographic locations were represented using latitude and longitude. The report states that 57 unique customer–city combinations were identified.

K-Means was then applied to geographic locations. Elbow and silhouette analyses were used to evaluate candidate cluster counts. The report selected **k = 3** for the loyal-city geographic clustering and reports a silhouette score of **0.6663**.

Cluster centroids were interpreted as potential logistics hub candidate areas.

## 6. Visualization

The report uses Matplotlib and Seaborn for statistical plots, Plotly for an interactive geographic map, and Folium for mapped locations and cluster centroids.

## 7. Interpretation

The resulting geographic clusters are intended to identify areas of concentrated loyal-customer demand. They provide candidate areas for further logistics planning and regional strategy; they are not, by themselves, a complete facility-location optimization model.
