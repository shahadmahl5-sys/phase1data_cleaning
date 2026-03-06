# 🏠 Ames Housing Project — Phase 1: Data Cleaning

## 1️⃣ Phase 1: Data Cleaning
In this phase, we focused on **loading the data, exploring it, and cleaning it** before any analysis or modeling.  
Goal: have a **clean DataFrame** with no missing values, duplicates, or crazy outliers.

---

## 2️⃣ What We Did

### 1. Load & Explore
- Used `pd.read_csv()` to load the dataset.  
- Checked the first 5 rows with `.head()` to understand the data.  
- Checked **shape (`.shape`) and data types (`.info()`)** to make sure everything looks right.  
- Fixed some column types like `MS SubClass`, `Mo Sold`, and `Yr Sold` from int to str.

### 2. Handling Missing Values
- Dropped columns with more than 80% missing (`Pool QC`, `Misc Feature`, `Alley`, `Fence`).  
- For categorical columns where NaN means the feature doesn’t exist, filled with `"None"` (like `Mas Vnr Type`, `Fireplace Qu`, `Bsmt Qual`, `Garage Type`).  
- For skewed numeric columns, filled missing values with **Median**.  
- For numeric count columns where NaN means the feature doesn’t exist, filled with **0**.  
- Filled `Electrical` with **Mode** since it had only one missing value.

### 3. Remove Duplicates
- Checked for duplicated rows using `.duplicated()`.  
- Dropped any duplicates if found.

### 4. Handle Outliers
- Detected outliers in `SalePrice` using the IQR method.  
- Capped extreme values at the **99th percentile**.  
- After capping, no outliers remained.

### 5. Validation
- Checked that no key columns have missing values.  
- All `SalePrice` values are > 0 ✅  
- DataFrame is not empty.

---

## 3️⃣ Result
- Dataset is now **clean** and ready for **Feature Engineering** or any modeling.  
- All steps are included in the `clean_data()` function so we can reuse it easily.  

> 🌟 Summary:  
> - Dropped columns with >80% missing  
> - Filled missing values smartly based on column type  
> - Removed duplicates  
> - Capped outliers  
> - Dataset ready for next steps!
