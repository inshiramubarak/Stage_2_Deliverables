# ACS WIL – Customer Churn Data Preprocessing

## Overview
This folder contains the data preprocessing and feature
preparation deliverables for the ACS WIL Customer Churn
Analysis project.

## My Role: Data Engineer
I prepared the customer churn dataset for the team members
working on ANN classification and K-Means clustering.

## Dataset
- Source: Dataset_ATS_v2.csv
- Total records: 7,043
- Original columns: 10
- Input features: 9
- Target: Churn

## Preprocessing Workflow
1. Inspected dataset structure and data types.
2. Checked missing, blank, duplicate-looking, and invalid values.
3. Identified conflicting phone-service records.
4. Retained all records because corrections could not be verified.
5. Separated input features and the Churn target.
6. Created an 80/20 stratified train-test split (random_state=42).
7. Applied one-hot encoding to categorical features.
8. Standardized tenure and MonthlyCharges.
9. Prepared separate predictive and clustering datasets.
10. Saved fitted preprocessing objects for reproducibility.

## Prepared Datasets
| File | Rows | Columns | Purpose |
|---|---:|---:|---|
| train_preprocessed.csv | 5,634 | 17 | ANN training |
| test_preprocessed.csv | 1,409 | 17 | ANN testing |
| clustering_preprocessed.csv | 7,043 | 16 | K-Means input |

The predictive datasets contain 16 features and Churn
encoded as No=0 and Yes=1.

The clustering dataset excludes Churn.

## Data Quality Findings
- Missing values: 0
- Blank text values: 0
- Duplicate-looking rows: 302
- Zero-tenure records: 11
- Conflicting phone-service records: 260
- Records removed: 0

Duplicate-looking rows were retained because no unique
customer identifier was available. Conflicting records
were documented rather than corrected without evidence.

## Additional Files
- encoder.pkl: fitted categorical encoder
- predictive_scaler.pkl: training-fitted numerical scaler
- clustering_scaler.pkl: full-data clustering scaler
- feature_information.json: feature names and target mapping
- preprocessing_config.json: reproducibility settings
- data_quality_report.csv: data-quality findings

## Important Notes
- The predictive encoder and scaler were fitted only on
  training data to avoid test-data leakage during fitting.
- The clustering dataset uses all available customers.
- The clustering teammate should review feature weighting,
  as one-hot features remain binary.
- No ANN or K-Means models were trained in this notebook.
