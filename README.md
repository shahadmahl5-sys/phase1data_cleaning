# 🏠 Ames Housing Project — Phase 1: Data Cleaning
**SHahad Alharbi | ML Foundations Capstone Report**

---

## 1️⃣ Introduction
For Phase 1, I used the **Ames Housing dataset** with 2,930 houses and 80+ features.  
Goal: **load, check, and clean** the data so it’s ready for later analysis.

---

## 2️⃣ Cleaning Steps

### a) Missing Values
- Drop columns with **too many missing values**: `Pool QC`, `Misc Feature`, `Alley`, `Fence`.  
- Fill categorical columns where NaN means “not there” (e.g., `Mas Vnr Type`, `Fireplace Qu`, `Garage Type`) with `"None"`.  
- Fill skewed numeric columns with **median** (`Lot Frontage`, `Garage Yr Blt`, `BsmtFin SF 1`, `Garage Cars`).  
- Fill numeric count columns where NaN means absence with **0** (`Bsmt Full Bath`, `Mas Vnr Area`).  
- Fill the single missing value in `Electrical` with **mode**.

### b) Data Types
- Convert categorical columns stored as numbers to strings: `MS SubClass`, `Mo Sold`, `Yr Sold`.

### c) Outliers
- Looked at `SalePrice` using IQR.  
- Capped very high/low values at the **99th percentile**.

### d) Duplicates
- Checked for duplicate rows and removed them (none found).

### e) Quick Check
- No missing values left in main columns.  
- All `SalePrice` > 0.  
- DataFrame is not empty.  

> All steps are inside a simple **`clean_data()` function** so it can be run anytime.

---

## 3️⃣ Dataset After Cleaning
- **Rows:** 2,930  
- **Columns:** fewer than original 82 (dropped some with too many NaNs)  
- **Target (`SalePrice`)**: clean, no missing values, outliers capped  

> Summary:  
> - Dropped very empty columns  
> - Filled missing values smartly (median, zero, mode, `"None"`)  
> - Fixed types for categorical numbers  
> - Capped extreme prices  
> - No duplicates  
> - Ready for analysis
