# Ames Housing Project
## Phase 1 – Data Cleaning

### Overview
In this phase, the Ames Housing dataset was loaded, explored, and cleaned to ensure data quality before modeling.

---

## Dataset Information
- Rows: 2,930
- Columns: 82 (before cleaning)
- Target Variable: SalePrice

---

## Cleaning Steps

### 1. Handling Missing Values

- Dropped columns with extremely high missing values (e.g., Pool QC).
- Filled categorical missing values with "Unknown".
- Filled skewed numerical features using Median.
- Filled symmetric numerical features using Mean.
- Filled discrete/count features using Mode.

This approach keeps the dataset consistent while minimizing information loss.

---

### 2. Removing Duplicates
- Checked for duplicated rows.
- Removed duplicates if any were found.

---

### 3. Handling Outliers
- Detected outliers in SalePrice.
- Capped extreme values at the 99th percentile.

---

### 4. Validation Checks
- Ensured no remaining missing values.
- Verified all SalePrice values are greater than 0.
- Confirmed the dataset structure after cleaning.

---

## Result
The dataset is now clean and ready for feature engineering and modeling.
