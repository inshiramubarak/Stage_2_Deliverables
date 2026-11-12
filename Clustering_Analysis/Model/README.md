# K-Means Customer Segmentation Model

## Objective
Group customers based on similarities in tenure and monthly
charges to support customer understanding and targeted business
initiatives.

## Dataset and Features
- Input: Data_Preparation/clustering_preprocessed.csv
- Customers: 7,043
- Selected features, in order: tenure, MonthlyCharges
- Both features were already standardised during preprocessing.
- No additional scaling was applied.
- Churn and the remaining columns were excluded from model fitting.

The full clustering dataset was used for exploratory segmentation.
The separate ANN training and testing datasets were not used here.
This analysis does not measure predictive performance on unseen data.

## Model Settings
- Algorithm: K-Means
- Number of clusters: 4
- random_state: 42
- n_init: 20

Four clusters were selected using the elbow method, supported by
the highest sampled silhouette score among the tested cluster counts.

## Training Code
```python
features = ["tenure", "MonthlyCharges"]
X = df[features].copy()

final_model = KMeans(
    n_clusters=4,
    random_state=42,
    n_init=20
)

cluster_labels = final_model.fit_predict(X)
```

## Model Outputs
- kmeans_model.joblib: a dictionary containing the trained model,
  expected feature order, and a note about input scaling.
- customers_with_clusters.csv: the preprocessed dataset with an
  added Cluster column.
- Customer_Clustering_Analysis.ipynb: the analysis and training notebook.

Cluster identifiers 0–3 are labels, not rankings.

## Reusing the Saved Model
For already preprocessed data, select the same two standardised
features in the saved order:

```python
saved = joblib.load("kmeans_model.joblib")
new_labels = saved["model"].predict(
    new_preprocessed[saved["features"]]
)
```

For raw numerical inputs, first apply the original fitted
clustering_scaler.pkl to tenure and MonthlyCharges in the correct
order. Do not fit a new scaler or scale prepared data again.

## Interpretation and Limitations
The model groups customers by tenure and monthly charges.
It does not predict churn or establish that any segment has
a higher churn risk.

The original scaler was used to convert values back to months
and original monthly-charge units for interpretation.

Results depend on the selected features, scaling, and model
settings. Other customer characteristics were not used to
define these segments.

Upstream data-quality findings included duplicate-looking rows
and conflicting phone-service records. These were retained and
documented by the data preparation teammate. Phone-service
features were not used in this model.
