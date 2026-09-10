# Quality Assurance and Review Notes

This repository was organized from the submitted five-page project report. The report's figures and narrative were reviewed together so that the repository does not introduce unsupported claims.

## Figure review

All eleven numbered figures in the report are accounted for in [`../results/figure-index.md`](../results/figure-index.md). The figures cover:

- overall variable correlation
- selected-variable description
- sales-variable correlation
- customer-clustering diagnostics
- RFM cluster distributions
- customer counts
- store-location cluster diagnostics and centroids
- loyal-city clustering diagnostics
- interactive loyal-customer geographic clustering
- proposed hub points

## Interpretation checks

The report consistently presents RFM and K-Means as an unsupervised approach for identifying a loyal segment and then locating geographic concentrations.

One wording inconsistency is retained rather than silently changed: the methodology/results select **k = 2** for customer clustering, while the conclusion says that customers were classified into **4 clusters**. The numerical customer-count table and preceding methodology support the k = 2 description. This should be corrected in the original report or source analysis if a new edition is produced.

The report also describes k = 3 as a good balance between model complexity and explained variance in the geographic analysis. Because K-Means and silhouette analysis are being used, future documentation should avoid calling silhouette selection an explained-variance measure unless an explicit variance metric is calculated.

## Reproducibility limitations

The current GitHub repository does not contain the original notebook/source code or the raw Kaggle dataset. Therefore the repository documents the completed analysis but does not claim that the exact original computation can currently be rerun from the repository alone.

A future reproducible release should add:

1. the cleaned analysis notebook or Python scripts;
2. a pinned dependency environment;
3. a clear input-data filename/schema;
4. a non-secret geocoding configuration example;
5. saved analysis outputs generated from code; and
6. a run guide explaining the complete workflow.

## Security review

No API key should be stored in source files. The `.gitignore` includes `.env` and common credential-file extensions. Any future Google Maps API key must be supplied through local environment configuration and must never be committed.
