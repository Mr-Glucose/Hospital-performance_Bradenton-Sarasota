# 🧹 Data Cleaning & Preparation — Milestone 2

### 📅 Phase: Week 2 — Day 4
This stage prepared the raw hospital data for analysis by cleaning, standardizing, and merging multiple datasets from the Centers for Medicare & Medicaid Services (CMS) and Florida Health Finder.

---

## 🎯 Objective
To create a clean, consistent, and analysis-ready dataset for evaluating **hospital performance, readmissions, safety, and patient satisfaction** across the Bradenton–Sarasota region.

---

## 📂 Datasets Used

| Dataset | Source | Purpose |
|----------|---------|---------|
| Hospital General Information | CMS | Basic identifiers and hospital characteristics |
| Readmissions and Deaths | CMS | Readmission ratios and discharge counts |
| HCAHPS (Patient Experience) | CMS | Survey results and satisfaction scores |
| Safety Indicators | CMS / Florida Health Finder | Safety and complication measures |

🧾 **Total raw records:** ~5,000 hospital entries across 4 datasets  
🏥 **Hospitals of focus:**  
1. Manatee Memorial Hospital  
2. HCA Florida Blake Hospital  
3. Sarasota Memorial Hospital  
4. Lakewood Ranch Medical Center  

---

## ⚠️ Issues Identified Before Cleaning

| Category | Description |
|-----------|-------------|
| 🧾 Inconsistent column names | “Facility Name” vs “Hospital Name”; “Facility ID” vs “Provider ID” |
| 🔢 Mixed datatypes | Text in numeric columns like “Not Available” or “–” |
| ❌ Missing values | Up to 30% missing readmission or survey scores |
| 🧍 Duplicate rows | Same hospital repeated across reporting periods |
| 📅 Mismatched date ranges | Different time periods for same measures |
| 📊 Non-standard scoring scales | Readmissions (0–1), HCAHPS (0–100), Safety (0–20) |
| 🧮 Outliers | Implausible scores (e.g., >1.2 readmission ratios) |

---

## 🔧 Cleaning Workflow Summary

| Step | Action | Result |
|------|---------|--------|
| 1️⃣ | Renamed columns across all datasets | Standardized IDs and names |
| 2️⃣ | Selected relevant analytical fields | Dropped addresses, phone, footnotes, dates |
| 3️⃣ | Converted scores to numeric (`pd.to_numeric`) | Ensured valid numeric types |
| 4️⃣ | Handled missing data | Removed invalid or null rows |
| 5️⃣ | Normalized value ranges | Readmissions: 0.6–1.2 • HCAHPS: 0–100 • Safety: 0–20 |
| 6️⃣ | Filtered hospitals | 4 local facilities kept |
| 7️⃣ | Merged cleaned datasets | Combined on `Provider ID` |
| 8️⃣ | Exported final datasets | Saved to `/1_datasets/cleaned/` |

---

## 📊 Final Outputs

| File | Description | Shape |
|------|--------------|--------|
| `hospital_clean.csv` | Merged hospital-level dataset | **4 rows × 14 columns** |
| `hospital_measures_long.csv` | Long-format dataset (measure-by-hospital) | **372 rows × 9 columns** |
| `hospital_crosswalk.csv` | ID-to-hospital mapping table | **4 rows × 2 columns** |

---

## 🧠 Key Results

- Reduced from **~5,000 raw records** → **4 target hospitals × 93 measures**  
- Removed duplicates, blanks, and inconsistent values  
- Ensured clean numeric columns and standardized metric names  
- Created reproducible data pipeline for further analysis (Day 5)

---

## 📍 Next Step
Proceed to **03_data_exploration.ipynb** to:
- Load the cleaned datasets  
- Explore score distributions and correlations  
- Generate visuals for HCAHPS, Readmissions, and Safety performance  

---

✅ **Milestone 2 Complete:** Cleaned, verified, and ready for analysis.

