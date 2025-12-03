# Presentation Materials
---

## 📊 Power BI Dashboard

Interactive dashboard analyzing hospital performance across 4 facilities in Bradenton-Sarasota, revealing an 8-point medication communication gap and strong correlation (r = -0.92) between patient experience and readmissions.

### Dashboard Previews

**Full Dashboard View:**
![Complete Dashboard](./Interactive_Dashboard_screenshots/dashboard_full_view.png)
*Full dashboard showing all visualizations: KPI cards, medication gap analysis, regional comparisons, and correlation plot*

**Interactive Features:**
![Dashboard with Filters Applied](./Interactive_Dashboard_screenshots/dashboard_interactive_view1.png)
![Dashboard with Filters Applied](./Interactive_Dashboard_screenshots/dashboard_interactive_view2.png)
*Demonstrating slicer functionality - filtering to specific hospitals for focused analysis*

**Key Finding - Correlation Analysis:**                                                                                                    
![Scatter Plot - Patient Experience vs Readmissions](./scatter_plot_correlation.png)                                                       
*Statistical visualization proving patient experience directly impacts readmissions (r = -0.92, p < 0.01)*

**Regional Strengths Analysis:**                                                                                                           
![Top 5 Strengths Comparison](./top5_strengths.png)    
 *Comparative view showing what all hospitals do well - nurse communication, doctor communication, cleanliness*

---

## 📥 Download Dashboard Files

### For Viewing:
- **[📄 Dashboard (PDF)](./Hospital_Performance_Dashboard.pdf)** - PDF version for easy viewing and sharing

### For Exploration:
- **[💾 Dashboard Source File (.pbix)](./Hospital_Performance_Dashboard.pbix)** - Requires Power BI Desktop (free) to open and explore interactively
  - [Download Power BI Desktop](https://powerbi.microsoft.com/desktop/)

---

## 🎯 Dashboard Components

### KPI Cards (Top Row)
Four executive summary cards showing overall patient experience scores:
- **Sarasota Memorial:** 84.2 (highest performer)
- **Lakewood Ranch:** 83.0
- **Manatee Memorial:** 79.8
- **Blake Hospital:** 77.2 (improvement opportunity)

### Medication Communication Analysis
Bar chart highlighting the 8-point gap in medication communication scores:
- Shows the single biggest improvement opportunity
- Lowest-performing measure across all hospitals (avg: 69.75)
- Clear visual of performance disparity between hospitals

### Top 5 Regional Strengths
Clustered column chart comparing hospitals on their best measures:
- Nurse Communication (88+ regional average)
- Doctor Communication (85+ regional average)
- Would Recommend Hospital
- Overall Hospital Rating
- Hospital Cleanliness

### Bottom 5 Improvement Opportunities
Identifies areas needing focus:
- **Medication Communication** (69.75 avg - PRIMARY FINDING)
- Hospital Quietness
- Care Transitions
- Staff Responsiveness
- Pain Management

### Correlation Scatter Plot (Key Finding!)
Visualizes the statistical relationship between patient experience and readmissions:
- **r = -0.92** (strong negative correlation)
- **p < 0.01** (statistically significant)
- **Interpretation:** Better communication = Fewer readmissions
- Trendline clearly shows the negative relationship

### Interactive Slicers
- **Hospital Filter:** Select one or multiple hospitals to compare
- **Measure Category Filter:** Focus on specific quality domains
- All charts update dynamically based on selections

---

## 🛠️ Technical Stack

**Visualization:**
- Power BI Desktop for dashboard design and interactive features
- DAX for calculated measures and KPIs
- Custom color scheme aligned with project branding

**Data Preparation:**
- Python (Pandas, NumPy) for data cleaning and transformation
- Statistical analysis using SciPy for correlation testing
- Data from CMS Hospital Compare (October 2023 - September 2024)

**Design Principles:**
- Consistent color coding across all visualizations
- Executive-level clarity and readability
- Mobile-responsive layout considerations
- Interactive exploration capabilities for stakeholders

---

## 🎨 Color Scheme

**Hospital Colors** (maintained throughout all visualizations):
- **Sarasota Memorial:** #84BEE0 (Sky Blue)
- **Lakewood Ranch:** #3DAD9E (Teal)
- **Manatee Memorial:** #F0C940 (Gold Yellow)
- **Blake Hospital:** #D16837 (Burnt Orange)
  
**Design Rationale:**
These colors were specifically chosen to respect each hospital's actual branding and visual identity. Additionally, each hospital's official logo is displayed in the dashboard, creating an authentic, professional presentation.

**UI Colors:**
- Background: #F9FAFB (Light Gray)
- Cards: #FFFFFF (White)
- Text: #1F2937 (Dark Gray)
- Accents: Project theme colors

---

## 📈 Key Metrics Summary

**Data Coverage:**
- 4 hospitals analyzed
- 119 quality measures evaluated
- 44 HCAHPS patient experience measures
- 6 readmission indicators
- 20+ safety measures
- Data period: October 2023 - September 2024

**Key Findings:**
- **8-point medication communication gap** (66-74 range)
- **r = -0.92 correlation** between patient experience and readmissions
- **Regional average:** 69.75 for medication communication (lowest measure)
- **Highest variance:** Medication communication (σ = 3.5)

---

## 🎥 Presentation Video

**[▶️ Watch Dashboard Walkthrough](YOUR_VIDEO_LINK_HERE)**
*4-5 minute video demonstration showing interactive features and key insights*

---

## 💡 Usage Guide

### For Hospital Administrators:
1. Start with KPI cards to see overall performance
2. Use slicers to focus on your hospital
3. Compare your medication scores to regional best performers
4. Review correlation plot to understand impact on readmissions

### For Quality Improvement Teams:
1. Focus on Bottom 5 chart for improvement priorities
2. Use Top 5 chart to identify best practices to replicate
3. Compare specific measure categories using slicers
4. Export findings for team discussions

### For Data Analysts:
1. Download .pbix file to explore data model
2. Review DAX measures and calculations
3. Examine data transformations and relationships
4. Adapt methodology for other regions or measures

---

## 📝 Additional Documentation

**Related Project Files:**
- `../5_communication_strategy/roberts_story.md` - Patient-centered narrative
- `../4_data_analysis/readme.md` - Technical methodology 
- `../3_data_exploration/readme.md` - Complete statistical analysis
- `../README.md` - Full project overview

---

## 👤 Author

**Arthur Dorvil**  
MIT Emerging Talent (ET6) - Certificate in Computer and Data Science

**Project Type:** Capstone Data Science Project  
**Completion Date:** November 2025  
**Tools Used:** Python, Power BI, Statistical Analysis

**Connect:**
- GitHub: [Mr-glucose](https://github.com/mr-glucose)
- LinkedIn: [Here](https://www.linkedin.com/in/lens-marc-arthur-dorvil)
- Portfolio: [mr-glucose/Hospital-performance_Bradenton-Sarasota](https://github.com/mr-glucose/Hospital-performance_Bradenton-Sarasota)

---

## 📊 Skills Demonstrated

This dashboard showcases:
- ✅ Power BI proficiency (DAX, slicers, KPI cards, interactive dashboards)
- ✅ Data visualization best practices & clear executive-facing design
- ✅ Clean data modeling and Python-based data cleaning/transformation
- ✅ Statistical analysis and correlation interpretation (r, variance, significance)
- ✅ Strong data storytelling and executive-level communication
- ✅ Healthcare analytics expertise (HCAHPS, CMS readmissions & quality metrics)
- ✅ Ability to turn real-world problems into actionable insights
- ✅ End-to-end project delivery (data → analysis → visualization → strategy)

---

## 📄 License & Data

**Data Source:** Centers for Medicare & Medicaid Services (CMS) Hospital Compare  
**Data License:** Public domain (U.S. Government data)  
**Analysis License:** MIT License  
**Data Period:** October 1, 2023 - September 30, 2024

All analysis, visualizations, and insights are original work created for educational purposes as part of the MIT Emerging Talent program.

---

## 🔄 Updates & Maintenance

**Version:** 1.1 (November 2025)  
**Status:** Complete - Ready for portfolio presentation  
**Last Updated:** December 2025

For questions about methodology, data sources, or dashboard usage, please open an issue on the GitHub repository.

---

*This dashboard transforms 119 quality measures into actionable insights, proving that better patient communication directly reduces hospital readmissions. When patients understand, patients recover.*
