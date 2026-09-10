# Analysis

## Customer loyalty model

The project uses RFM analysis to represent customer behavior through recency, frequency, and monetary value. These three features are standardized and used as inputs to K-Means clustering.

The report identifies two customer clusters. The cluster interpreted as loyal contains **28 customers**, while the other contains **15,491 customers**.

The loyal segment is characterized in the report by higher recency, frequency, and monetary values relative to the other cluster.

## Loyal-customer geographic analysis

After selecting the loyal segment, the analysis examines where those customers' orders were placed. The report identifies **57 unique customer–city combinations**.

Latitude and longitude are used for geographic clustering. Elbow and silhouette diagnostics are used to select the geographic cluster count.

The report selects **three geographic clusters**, with a reported silhouette score of **0.6663** at k = 3.

## Hub candidate interpretation

For each geographic cluster, the report summarizes cluster size, mean latitude and longitude, and the dominant city. Cluster centroids are then plotted as candidate logistics hub points.

The report gives the following example dominant cities:

| Geographic cluster | Reported dominant city | Reported cluster size |
|---|---|---:|
| 0 | Kars | 23 |
| 1 | Aurangabad | 14 |
| 2 | Managua | 20 |

These values should be read as reported in the submitted analysis. The cluster sizes do not necessarily represent the number of unique customers; the report describes them in the context of the geographic clustering output.

## Visual analysis

The submitted report contains eleven figures covering correlation analysis, variable selection, RFM clustering, cluster diagnostics, geographic clustering, and proposed hub points. See [`../results/figure-index.md`](../results/figure-index.md).
