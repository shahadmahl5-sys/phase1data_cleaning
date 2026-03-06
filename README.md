# 🏠 Ames Housing Project — Phase 1: Data Cleaning
**Shahad Alharbi | Data Cleaning**

---

## 1️⃣ Introduction
For Phase 1, I worked with the **Ames Housing dataset** (2,930 houses, 80+ features).  
Goal: **load, explore, and clean** the data so it’s ready for analysis and later modeling.

---

## 2️⃣ Cleaning Steps

### a) Missing Values
- Drop columns with **>80% missing**: `Pool QC`, `Misc Feature`, `Alley`, `Fence`.  
- Fill categorical columns where NaN means “doesn’t exist” (e.g., `Mas Vnr Type`, `Fireplace Qu`, `Garage Type`) with `"None"`.  
- Fill numeric skewed features with **median** (`Lot Frontage`, `Garage Yr Blt`, `BsmtFin SF 1`, `Garage Cars`).  
- Fill numeric counts with **0** (`Bsmt Full Bath`, `Mas Vnr Area`).  
- Fill single missing value in `Electrical` with **mode**.

### b) Data Types
- Convert categorical features stored as integers to strings: `MS SubClass`, `Mo Sold`, `Yr Sold`.

### c) Outliers
- Checked `SalePrice` using IQR.  
- Capped extreme values at the **99th percentile**.

### d) Duplicates
- Checked for duplicates using `.duplicated()` and removed them (none found).

### e) Validation
- No missing values remain in key columns.  
- All `SalePrice` > 0.  
- DataFrame is not empty.  

> All steps are wrapped in a **`clean_data()` function** for reuse.

---

## 3️⃣ Dataset After Cleaning
- **Rows:** 2,930  
- **Columns:** reduced from 82 to cleaned set  
- **Target (`SalePrice`)**: clean, outliers capped, no missing values  

> ✅ Summary:  
> - Dropped columns with too many missing values  
> - Filled missing values smartly (median, zero, mode, `"None"`)  
> - Fixed data types  
> - Capped outliers  
> - No duplicates  
> - Dataset ready for analysis
