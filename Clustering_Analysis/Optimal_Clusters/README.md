# Selecting the Number of Clusters

## Features and Method
K-Means clustering was performed using tenure and MonthlyCharges
for 7,043 customers. Both features had already been standardised
during data preparation. Churn was excluded from clustering.

Models were fitted for k values from 1 to 10 using random_state=42
and n_init=20.

## Elbow Method
Inertia decreased sharply between k=1 and k=4. Beyond k=4,
the reductions became smaller, indicating an elbow around
four clusters.

## Silhouette Comparison
Silhouette scores were evaluated for k=2 to k=10 using a
reproducible sample of 3,000 customers with random_state=42.

The highest sampled silhouette score was approximately 0.473
at k=4, supporting the choice suggested by the elbow graph.

## Selected Number
Four clusters were selected based on the elbow pattern and
the highest sampled silhouette score among the tested values.

This is a supported choice for the selected features and
tested settings, rather than proof of a uniquely optimal
customer segmentation.

## Supporting Files
- cluster_selection.png: elbow and silhouette graphs.
- cluster_comparison.csv: inertia and silhouette results.
