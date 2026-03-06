# 🏠 Ames Housing Project — Phase 1: Data Cleaning
**Student Name | ML Foundations Capstone Report**

---

## 1️⃣ Introduction
For this phase, I worked with the **Ames Housing dataset**, which contains 2,930 residential property sales in Ames, Iowa. Each record has over 80 features describing the house’s lot, structure, condition, and neighborhood, along with the final sale price.  

The main goal of Phase 1 was to **load the data, understand it, and clean it**, so that the dataset would be ready for analysis and modeling in later phases.

---

## 2️⃣ Cleaning Summary

### a) Missing Values
- Dropped columns with **more than 80% missing values**: `Pool QC`, `Misc Feature`, `Alley`, `Fence`. Imputing these would be unreliable.  
- Filled categorical columns where NaN means the feature doesn’t exist (e.g., `Mas Vnr Type`, `Fireplace Qu`, `Garage Type`) with `"None"`.  
- Filled numeric columns with extreme outliers (skewed) with **median** (`Lot Frontage`, `Garage Yr Blt`, `BsmtFin SF 1`, `Garage Cars`, etc.).  
- Filled numeric count columns where NaN indicates absence (`Bsmt Full Bath`, `Mas Vnr Area`) with **0**.  
- Filled the single missing value in `Electrical` with **mode**.  

### b) Data Types
- Converted columns that are **categorical but stored as integers** to strings: `MS SubClass`, `Mo Sold`, `Yr Sold`.  

### c) Outliers
- Detected outliers in `SalePrice` using the IQR method.  
- Capped extreme values at the **99th percentile**. This prevents the most expensive houses from distorting analysis without removing real sales.  

### d) Duplicates
- Checked for full-row duplicates using `.duplicated()`.  
- Removed any duplicates (none were found in this dataset).

### e) Validation
- Ensured no missing values remain in key columns.  
- Confirmed all `SalePrice` values are **greater than 0**.  
- Verified the DataFrame is not empty.  

All of these steps are included in a **`clean_data()` function**, which can be reused for other datasets or future phases.  

---

## 3️⃣ Dataset After Cleaning
- **Rows:** 2,930  
- **Columns:** Reduced from 82 to cleaned set (some dropped for missing values)  
- **Target:** `SalePrice` is clean, with outliers capped and no missing values.  

> Summary:  
> - Columns with >80% missing dropped  
> - Missing values filled smartly (median, zero, mode, or `"None"`)  
> - Data types fixed for categorical features  
> - Outliers capped at 99th percentile  
> - No duplicates  
> - Dataset ready for analysis
