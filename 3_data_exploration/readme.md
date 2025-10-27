# 🏥 Hospital Performance — Data Exploration  
### Bradenton–Sarasota Area | HCAHPS · Readmissions · Safety

> This page summarizes the **exploratory analysis** and links to the interactive charts.

---

## 🔗 Quick Links to Visuals

- **Overall Comparison** — [Interactive](../4_outputs/visualizations/01_overall_comparison.html) · ![PNG]([../4_outputs/visualizations/01_overall_comparison.png](https://github.com/Mr-Glucose/Hospital-performance_Bradenton-Sarasota/blob/main/3_data_exploration/4_outputs/visualizations/01_overall_comparison.png))
- **Top 5 HCAHPS (Overall)** — [Interactive](../4_outputs/visualizations/02_top5_hcahps.html) · ![PNG](../4_outputs/visualizations/02_top5_hcahps.png)
- **Bottom 5 HCAHPS (Overall)** — [Interactive](../4_outputs/visualizations/03_bottom5_hcahps.html) · ![PNG](../4_outputs/visualizations/03_bottom5_hcahps.png)
- **Treemap: Top 5 by Hospital** — [Interactive](../4_outputs/visualizations/04_treemap_top5.html) · ![PNG](../4_outputs/visualizations/04_treemap_top5.png)
- **Correlation Heatmap** — [Interactive](../4_outputs/visualizations/05_correlation_heatmap.html) · ![PNG](../4_outputs/visualizations/05_correlation_heatmap.png)

> 📌 **Tip:** If GitHub doesn’t render the HTML preview, click “Raw” to download, or open locally in a browser.

---

## 1) Executive Summary

This analysis compares four hospitals using **HCAHPS patient experience**, **Readmissions**, and **Safety** metrics:

- **Sarasota Memorial Hospital**
- **Manatee Memorial Hospital**
- **HCA Florida Blake Hospital**
- **Lakewood Ranch Medical Center**

**Top takeaways**
- Sarasota Memorial leads in overall patient experience.
- “Medication communication”, “quiet at night”, and “care transition” show the biggest opportunities region-wide.
- Patient experience and safety move together; readmissions tend to move in the opposite direction.

---

## 2) At-a-Glance KPIs

| Hospital | Readmissions | Patient Experience (HCAHPS) | Safety |
|---|---:|---:|---:|
| **Sarasota Memorial Hospital** | 0.92 | 84.20 | 9.67 |
| **Lakewood Ranch Medical Center** | 0.95 | 83.00 | 12.96 |
| **Manatee Memorial Hospital** | 1.00 | 79.80 | 12.82 |
| **HCA Florida Blake Hospital** | 1.00 | 77.20 | 13.07 |

> ℹ️ Higher is better for **HCAHPS**; lower is better for **readmissions**; **safety** is a composite (lower is generally better when it reflects adverse events).

---

## 3) Hospital Profiles

<details>
<summary><strong>HCA Florida Blake Hospital</strong></summary>

**Strengths (Top 5):**  
- Nurse Communication — 85.00  
- Doctor Communication — 84.00  
- Hospital Cleanliness — 82.00  
- Discharge Information — 80.00  
- Overall Hospital Rating — 79.00  

**Opportunities (Bottom 5):**  
- Understood Symptoms to Watch — (data not reported)  
- Recommend Hospital (Stars) — (data not reported)  
- Recommend Hospital — Definitely Yes — (data not reported)  
- Recommend Hospital — Def/Prob No — (data not reported)  
- Recommend Hospital — Probably Yes — (data not reported)  
</details>

<details>
<summary><strong>Lakewood Ranch Medical Center</strong></summary>

**Strengths (Top 5):**  
- Nurse Communication — 90.00  
- Doctor Communication — 87.00  
- Hospital Cleanliness — 87.00  
- Discharge Information — 86.00  
- Would Recommend Hospital — 85.00  

**Opportunities (Bottom 5):**  
- Understood Symptoms to Watch — (data not reported)  
- Recommend Hospital (Stars) — (data not reported)  
- Recommend Hospital — Definitely Yes — (data not reported)  
- Recommend Hospital — Def/Prob No — (data not reported)  
- Recommend Hospital — Probably Yes — (data not reported)  
</details>

<details>
<summary><strong>Manatee Memorial Hospital</strong></summary>

**Strengths (Top 5):**  
- Nurse Communication — 88.00  
- Doctor Communication — 85.00  
- Hospital Cleanliness — 84.00  
- Discharge Information — 83.00  
- Overall Hospital Rating — 83.00  

**Opportunities (Bottom 5):**  
- Understood Symptoms to Watch — (data not reported)  
- Recommend Hospital (Stars) — (data not reported)  
- Recommend Hospital — Definitely Yes — (data not reported)  
- Recommend Hospital — Def/Prob No — (data not reported)  
- Recommend Hospital — Probably Yes — (data not reported)  
</details>

<details>
<summary><strong>Sarasota Memorial Hospital</strong></summary>

**Strengths (Top 5):**  
- Nurse Communication — 91.00  
- Would Recommend Hospital — 91.00  
- Doctor Communication — 90.00  
- Overall Hospital Rating — 89.00  
- Discharge Information — 86.00  

**Opportunities (Bottom 5):**  
- Understood Symptoms to Watch — (data not reported)  
- Recommend Hospital (Stars) — (data not reported)  
- Recommend Hospital — Definitely Yes — (data not reported)  
- Recommend Hospital — Def/Prob No — (data not reported)  
- Recommend Hospital — Probably Yes — (data not reported)  
</details>

---

## 4) Key Findings & Insights

**Overall HCAHPS ranking (avg score):**  
🥇 Sarasota Memorial (84.20)  
🥈 Lakewood Ranch (83.00)  
🥉 Manatee Memorial (79.80)  
4️⃣ HCA Florida Blake (77.20)

**Common strengths (regional averages):**  
- Nurse Communication — 88.50  
- Doctor Communication — 86.50  
- Hospital Cleanliness — 84.25  
- Overall Hospital Rating — 84.00  
- Discharge Information — 83.75

**Common opportunities (regional averages):**  
- Medication Communication — 69.75  
- Quiet at Night — 73.50  
- Care Transition — 77.75  
- Staff Responsiveness — 79.00  
- Would Recommend Hospital — 83.50

**Largest performance gaps (range across hospitals):**  
- Would Recommend Hospital — 78.00 → 91.00 (gap 13.00)  
- Overall Hospital Rating — 79.00 → 89.00 (gap 10.00)  
- Quiet at Night — 68.00 → 77.00 (gap 9.00)  
- Medication Communication — 66.00 → 74.00 (gap 8.00)  
- Care Transition — 75.00 → 81.00 (gap 6.00)

**Correlation insights (Pearson):**  
- Readmissions ↔ Patient Experience: **-0.92**  
- Readmissions ↔ Safety: **0.83**  
- Patient Experience ↔ Safety: **-0.68**  
> 🔎 Interpretation: As **readmissions** improve (go down), **patient experience** tends to go **up**.

---

## 5) Recommendations

**For hospital administrators (theme-based):**
- Implement **quiet hours** & noise reduction.
- Strengthen **care transitions** and discharge planning.
- Boost **medication communication** (pharmacist counseling, teach-back).
- Improve **responsiveness** (staffing ratios, call-bell workflows).
- Sustain gains in **cleanliness** and **provider communication**.

**For regional planning:**
- Share best practices for **medication communication** and **quiet-at-night**.
- Standardize **care transition protocols** across facilities.
- Build peer learning and **quarterly benchmarking**.

---

## 6) Data & Reproducibility

**Cleaned datasets**
- `../1_datasets/cleaned/hospital_clean.csv`  
- `../1_datasets/cleaned/hospital_measures_long.csv`

**Notebook / Script**
- `03_data_exploration.ipynb` (this folder)

**Summary stats**
- Hospitals analyzed: **4**  
- Total HCAHPS measures: **93**  
- Total data points: **372**  
- Average regional HCAHPS: **81.05**  
- Range: **66.00 – 91.00**

---

## 7) How to View the Charts Locally

1. Clone the repo and open this folder in VS Code.  
2. Open any HTML file from `../4_outputs/visualizations/` in your browser.  
3. Use the PNGs in presentations or the main project README.

---

