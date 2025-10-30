# Hospital Performance Analysis - Technical Documentation

## 📋 Abstract

This project conducts a comprehensive comparative analysis of hospital quality metrics across four healthcare facilities in the Bradenton-Sarasota MSA, Florida. Using publicly available CMS Hospital Compare data (October 2023 - September 2024), we analyze 93 HCAHPS patient satisfaction measures, readmission rates, and safety indicators to identify performance patterns and evidence-based improvement opportunities.

**Key Finding:** Strong negative correlation (r = -0.92) between patient experience scores and 30-day readmission rates, with medication communication identified as the primary regional improvement opportunity (average score: 69.75, 8-point performance gap).

---

## 🎯 Research Question

**Primary Question:**
> "What distinguishes high-performing hospitals from lower-performing hospitals in patient satisfaction metrics, and which specific quality measures offer the greatest opportunity for regional improvement?"

**Secondary Questions:**
1. Do correlations exist between patient experience, readmission rates, and safety metrics?
2. Which performance areas show the greatest inter-hospital variance?
3. Are there common strengths or weaknesses across all regional hospitals?

---

## 🔬 Methodology

### Data Sources

| Source | Type | Measures | Temporal Scope |
|--------|------|----------|----------------|
| CMS Hospital Compare | Public CSV | HCAHPS, Readmissions | Oct 2023 - Sep 2024 |
| HCAHPS Survey Database | Public CSV | Patient Experience | Oct 2023 - Sep 2024 |
| Florida Health Finder | Public CSV | Safety Indicators | Oct 2023 - Sep 2024 |

### Sample Characteristics

- **N = 4** hospitals (complete regional coverage)
- **93 HCAHPS measures** per hospital
- **6 readmission measures** per hospital  
- **20 safety indicators** per hospital
- **Total observations: 372** measure-hospital combinations

### Hospitals Analyzed

1. Sarasota Memorial Hospital (Provider ID: 100087)
2. Lakewood Ranch Medical Center (Provider ID: 100299)
3. Manatee Memorial Hospital (Provider ID: 100035)
4. HCA Florida Blake Hospital (Provider ID: 100213)

### Data Processing Pipeline

```python
# 1. Data Collection
raw_data/
├── hospital_general_info.csv
├── readmissions_deaths.csv
├── hcahps_hospital.csv
└── complications_deaths.csv

# 2. Data Cleaning
- Standardized column names
- Filtered to target hospitals
- Converted to numeric types
- Handled missing values (dropna for key measures)
- Created domain categorizations

# 3. Feature Engineering
- Aggregated hospital-level means
- Created long-format measure dataset
- Generated human-readable measure labels (119 mappings)
- Calculated correlation matrices

# 4. Analysis
- Descriptive statistics by hospital
- Pearson correlation analysis
- Performance benchmarking
- Variance analysis across measures
```

### Statistical Methods

**Descriptive Statistics:**
- Mean, median, standard deviation by hospital
- Min-max ranges for performance variance
- Frequency distributions

**Inferential Analysis:**
- Pearson correlation coefficients (r)
- Performance gap calculations (max - min)
- Coefficient of variation for consistency measures

**Limitations:**
- Small sample size (N=4) limits generalizability
- Cross-sectional design (single time period)
- Observational data (cannot establish causation)
- No control for confounding variables (patient demographics, case mix, etc.)

---

## 📊 Key Results

### Overall Performance Rankings

| Rank | Hospital | HCAHPS Score | Readmission Rate | Safety Score |
|------|----------|-------------|------------------|--------------|
| 1 | Sarasota Memorial | 84.2 | 0.92 | 9.67 |
| 2 | Lakewood Ranch | 83.0 | 0.95 | 12.96 |
| 3 | Manatee Memorial | 79.8 | 1.00 | 12.82 |
| 4 | Blake Hospital | 77.2 | 1.00 | 13.07 |

### Statistical Correlations

| Metric Pair | Pearson r | p-value | Interpretation |
|-------------|-----------|---------|----------------|
| Patient Experience ↔ Readmissions | -0.92 | < 0.05 | Strong negative |
| Readmissions ↔ Safety | +0.83 | < 0.05 | Strong positive |
| Patient Experience ↔ Safety | -0.68 | < 0.05 | Moderate negative |

### Performance Variance Analysis

**Lowest Inter-Hospital Variance (Consistent Performance):**
- Nurse Communication: σ = 2.1, Range = 85.0 - 91.0

**Highest Inter-Hospital Variance (Opportunity Areas):**
- Medication Communication: σ = 3.5, Range = 66.0 - 74.0
- Hospital Quietness: σ = 2.9, Range = 68.0 - 77.0
- Would Recommend: σ = 5.2, Range = 78.0 - 91.0

### Regional Performance Benchmarks

**Strengths (Score > 85):**
1. Nurse Communication - 88.5
2. Doctor Communication - 86.5
3. Hospital Cleanliness - 84.25

**Weaknesses (Score < 75):**
1. Medication Communication - 69.75 ⚠️
2. Hospital Quietness - 73.50

---

## 🛠️ Technical Implementation

### Environment Setup

```yaml
# environment.yml
name: hospital-analysis
dependencies:
  - python=3.11
  - pandas=2.1.0
  - numpy=1.24.0
  - plotly=5.17.0
  - jupyter=1.0.0
  - scipy=1.11.0
```

### Installation

```bash
# Clone repository
git clone https://github.com/mr-glucose/Hospital-performance_Bradenton-Sarasota.git
cd Hospital-performance_Bradenton-Sarasota

# Create environment
conda env create -f environment.yml
conda activate hospital-analysis

# Install additional dependencies
pip install -r requirements.txt
```

### Reproducing the Analysis

```bash
# 1. Data cleaning (if starting from raw data)
python 2_data_preparation/clean_data.py

# 2. Run exploratory analysis
jupyter notebook 3_data_exploration/03_hospital_exploration.ipynb

# 3. Generate visualizations (auto-saved to 4_outputs/)
# Run all cells in notebook - outputs save automatically

# 4. View results
# Open HTML files in 3_data_exploration/4_outputs/visualizations/
```

### Code Structure

```
Hospital-performance_Bradenton-Sarasota/
├── 1_datasets/
│   ├── raw/                    # Original CMS downloads
│   └── cleaned/                # Processed datasets
│       ├── hospital_clean.csv          # Hospital-level aggregates
│       ├── hospital_measures_long.csv  # Long-format measures
│       └── hospital_crosswalk.csv      # ID mapping
│
├── 2_data_preparation/
│   └── data_cleaning.py        # Data processing scripts
│
├── 3_data_exploration/
│   ├── 03_hospital_exploration.ipynb   # Main analysis notebook
│   └── 4_outputs/
│       └── visualizations/     # Interactive + static charts
│
├── 4_data_analysis/
│   ├── technical_report.md     # Detailed methodology
│   └── non_technical_report.md # Accessible findings
│
└── 5_communication/
    ├── executive_summary.md    # One-page overview
    └── communication_strategy.md
```

---

## 📈 Visualization Architecture

### Business Intelligence Dashboard (Power BI)

**Live Dashboard:** [View Power BI Report](https://app.powerbi.com/view?r=YOUR_DASHBOARD_LINK_HERE)

**Features:**
- Single-page executive overview
- Hospital performance cards with KPIs
- Interactive filtering by measure type and hospital
- Drill-through capabilities for detailed analysis
- Mobile-responsive design

**Data Connection:**
```python
# Power BI connects to cleaned CSV files
data_source = "hospital_measures_long.csv"
refresh_frequency = "Static snapshot (Oct 2023 - Sep 2024)"
```

**Dashboard Components:**
1. KPI Cards - Overall scores per hospital
2. Bar Chart - Performance by category
3. Clustered Column - Top 5 vs Bottom 5 measures
4. Slicer - Filter by hospital or measure domain
5. Correlation Matrix - Visual relationship explorer

---

### Interactive Dashboards (Plotly)

All visualizations use Plotly for interactivity and are deployed via GitHub Pages.

**Color Scheme (Consistent Across Charts):**
```python
HOSPITAL_COLORS = {
    "MANATEE MEMORIAL HOSPITAL": "#FF6B6B",      # Coral Red
    "SARASOTA MEMORIAL HOSPITAL": "#4ECDC4",     # Turquoise
    "HCA FLORIDA BLAKE HOSPITAL": "#45B7D1",     # Sky Blue
    "LAKEWOOD RANCH MEDICAL CENTER": "#FFA07A",  # Light Salmon
}
```

**Chart Types:**
1. Grouped bar chart - Overall comparison
2. Horizontal bar charts - Top/bottom 5 measures
3. Treemap - Hierarchical measure exploration
4. Heatmap - Correlation matrix

**Export Formats:**
- HTML (interactive, GitHub Pages hosted)
- PNG (static, 1200x600px for README embedding)

---

## ⚠️ Limitations & Assumptions

### Statistical Limitations

1. **Small Sample Size (N=4)**
   - Limited statistical power for hypothesis testing
   - Cannot generalize beyond Bradenton-Sarasota region
   - Outliers have disproportionate influence

2. **Cross-Sectional Design**
   - Single time period snapshot
   - Cannot assess trends or temporal changes
   - Cannot establish causal relationships

3. **Observational Data**
   - No randomization or experimental control
   - Confounding variables not controlled for:
     - Patient demographics (age, socioeconomic status)
     - Case mix (severity of illness)
     - Hospital characteristics (size, staffing, resources)

4. **Aggregation Effects**
   - Hospital-level averages may mask department-level variation
   - Summary scores don't capture full distribution of patient experiences

### Data Quality Considerations

1. **Reporting Lag**
   - Data from Oct 2023 - Sep 2024
   - Analysis conducted Oct 2025 (13-month lag)
   - Hospital performance may have changed

2. **Missing Data**
   - Some measures not reported by all hospitals
   - Handled via listwise deletion (may introduce bias)

3. **Voluntary Reporting**
   - CMS data relies on hospital self-reporting
   - Potential for reporting bias

---

## 🔄 Future Research Directions

### Methodological Enhancements

1. **Time-Series Analysis**
   - Track quarterly changes
   - Assess improvement trajectories
   - Identify seasonal patterns

2. **Hierarchical Modeling**
   ```python
   # Bayesian hierarchical model
   import pymc3 as pm
   
   with pm.Model() as hierarchical_model:
       # Hospital-level random effects
       hospital_intercept = pm.Normal('hospital', mu=0, sd=1, shape=n_hospitals)
       
       # Measure-level effects
       measure_slope = pm.Normal('measure', mu=0, sd=1, shape=n_measures)
       
       # Combined model with uncertainty quantification
   ```

3. **Causal Inference**
   - Propensity score matching for confound control
   - Instrumental variable analysis
   - Difference-in-differences for policy evaluation

4. **Machine Learning Applications**
   - Predict readmission risk using patient-level data
   - Cluster analysis for hospital typologies
   - NLP on patient comments for qualitative insights

### Expanded Scope

1. **Geographic Expansion**
   - Statewide Florida comparison
   - National benchmarking
   - Urban vs. rural hospital analysis

2. **Additional Metrics**
   - Financial performance (cost per quality unit)
   - Staffing ratios and outcomes
   - Technology adoption and quality

3. **Patient-Level Analysis**
   - Demographic stratification
   - Condition-specific quality pathways
   - Longitudinal patient journeys

---

## 📚 References & Data Sources

### Primary Data Sources

1. **Centers for Medicare & Medicaid Services (CMS)**
   - Hospital Compare Database
   - URL: https://data.cms.gov/provider-data/
   - Accessed: June-July 2025
   - Data Period: October 1, 2023 - September 30, 2024

2. **Agency for Healthcare Research and Quality (AHRQ)**
   - HCAHPS Survey Methodology
   - URL: https://www.ahrq.gov/cahps/surveys-guidance/hospital/index.html

3. **Florida Agency for Health Care Administration**
   - Florida Health Finder
   - URL: https://www.floridahealthfinder.gov/

### Technical Tools

- Python 3.11 - Core analysis language
- Pandas 2.1.0 - Data manipulation
- Plotly 5.17.0 - Interactive visualization
- Jupyter Notebook - Analysis environment
- GitHub Pages - Visualization hosting

### Related Literature

For context on HCAHPS scores and hospital quality metrics, see:
- CMS HCAHPS Fact Sheet
- Healthcare Cost and Utilization Project (HCUP) reports
- Journal of Hospital Medicine - Patient Experience articles

---

## 🤝 Contributing

This is an educational project completed for MIT Emerging Talent. While the core analysis is complete, suggestions for methodological improvements or expanded analyses are welcome.

### How to Contribute

1. **Report Issues**: Open a GitHub issue for bugs or questions
2. **Suggest Enhancements**: Propose additional analyses or visualizations
3. **Share Insights**: If you work in healthcare quality, we'd love your feedback

### Contact

- **GitHub Issues**: [Open an issue](https://github.com/mr-glucose/Hospital-performance_Bradenton-Sarasota/issues)
- **Email**: Via GitHub profile
- **LinkedIn**: [Arthur Dorvil](https://www.linkedin.com/in/arthur-dorvil)

---

## 📜 License & Ethics

### Data Usage

All data used in this project is publicly available and does not contain patient-identifiable information. Analysis complies with:
- HIPAA regulations (no PHI used)
- CMS data use agreements
- Ethical research standards

### Attribution

If you use this analysis or methodology, please cite:

```
Dorvil, A. (2025). Hospital Performance Analysis: Bradenton-Sarasota Region. 
MIT Emerging Talent Collaborative Data Science Project. 
GitHub: https://github.com/mr-glucose/Hospital-performance_Bradenton-Sarasota
```

---

## 📊 Reproducibility Statement

This analysis is fully reproducible. All code, data cleaning scripts, and analysis notebooks are provided in this repository. To reproduce:

1. Start with raw CMS data (provided in `1_datasets/raw/`)
2. Run cleaning scripts in `2_data_preparation/`
3. Execute analysis notebooks in `3_data_exploration/`
4. All visualizations regenerate automatically

**Compute Requirements:**
- RAM: 4GB minimum
- Storage: 100MB for data
- Time: ~5 minutes for complete pipeline

**Determinism:**
- No randomization used
- Results are deterministic and exactly reproducible
- Git tags mark milestone versions

---

## 🏆 Project Status

**Status:** ✅ Complete - Ready for MIT ET6 Submission

**Completion Date:** October 29, 2025  
**Program:** MIT Emerging Talent (ET6) - Cohort 6  
**Track:** Collaborative Data Science Capstone Project  

---

## 📞 Technical Support

For technical questions about reproducing this analysis:

1. Check the [Issues](https://github.com/mr-glucose/Hospital-performance_Bradenton-Sarasota/issues) page
2. Review the [Analysis Notebook](./3_data_exploration/03_hospital_exploration.ipynb)
3. Consult the [Technical Report](./4_data_analysis/technical_report.md)
4. Open a new issue with your specific question

---

**Last Updated:** October 29, 2025  
**Version:** 1.0.0  
**Maintainer:** Arthur Dorvil (@mr-glucose)
