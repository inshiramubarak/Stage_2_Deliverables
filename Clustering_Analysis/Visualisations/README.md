# Customer Segments: Visualisation and Interpretation

## Overview
K-Means identified four segments among 7,043 customers using
standardised tenure and MonthlyCharges.

The labelled graph displays values converted back to tenure
in months and the original monthly-charge units.

## Files
- customer_segments_labelled.png: customer scatter plot with
  segment labels and cluster centres.
- cluster_summary.csv: customer counts, average tenure,
  average monthly charges, and segment percentages.

## Segment Summary

| Cluster | Segment | Customers | Average tenure (months) | Average monthly charges | Share |
|---|---|---:|---:|---:|---:|
| 0 | Shorter tenure, higher charges | 2,202 | 14.81 | 81.23 | 31.27% |
| 1 | Shorter tenure, lower charges | 1,733 | 10.48 | 32.49 | 24.61% |
| 2 | Longer tenure, higher charges | 1,948 | 58.76 | 93.08 | 27.66% |
| 3 | Longer tenure, lower charges | 1,160 | 54.10 | 34.15 | 16.47% |

Percentages may not total exactly 100% because of rounding.
Shorter/longer tenure and higher/lower charges are relative
segment descriptions, rather than fixed business thresholds.

## Reading the Graph
- Each point represents a customer record; points may overlap.
- The horizontal axis shows tenure in months.
- The vertical axis shows monthly charges in original dataset units.
- Colours identify cluster membership.
- Black X markers show cluster centres.
- C0–C3 identify the corresponding cluster centres.

Clustering was performed in standardised feature space.
Original units are used in the graph to make interpretation easier.

## Interpretation and Suggested Actions

### Cluster 0: Shorter Tenure, Higher Charges
The largest segment contains 2,202 customers, with average tenure
of 14.81 months and average monthly charges of 81.23.

Suggested action: assess onboarding support, billing clarity,
and whether customers understand the value of their plans.

### Cluster 1: Shorter Tenure, Lower Charges
This segment contains 1,733 customers, with average tenure
of 10.48 months and average monthly charges of 32.49.

Suggested action: offer onboarding guidance and assess suitable
service options based on customer needs and affordability.

### Cluster 2: Longer Tenure, Higher Charges
This segment contains 1,948 customers, with average tenure
of 58.76 months and average monthly charges of 93.08.

Suggested action: assess loyalty benefits and proactive service
reviews for established customers with higher monthly charges.

### Cluster 3: Longer Tenure, Lower Charges
This segment contains 1,160 customers, with average tenure
of 54.10 months and average monthly charges of 34.15.

Suggested action: maintain reliable, affordable service and assess
whether existing plans continue to meet customer needs.

## Limitations
These suggested actions are business hypotheses to investigate,
not interventions proven effective by this analysis.

Churn was excluded from clustering. Segment membership alone
does not establish churn risk, customer satisfaction,
profitability, or customer lifetime value.

Only tenure and monthly charges determined the segments.
Further analysis would be required to evaluate churn rates
or other outcomes within each group.
