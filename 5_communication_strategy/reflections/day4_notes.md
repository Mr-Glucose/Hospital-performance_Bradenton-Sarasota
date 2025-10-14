# Day 4 – Data Cleaning Notes

**What I did**
- Standardized IDs to 6-digit CCN (zero-padded); fixed join issues.
- Normalized hospital names to uppercase; standardized City/Town -> City.
- Converted numeric fields; removed empty/duplicate columns.
- Aggregated domain scores to hospital level (means/median); built long table for plotting.

**Issues & decisions**
- Readmissions measures didn’t align with HCAHPS/Safety; chose domain-wise aggregation per CCN instead of joining by “Measure”.
- Some numeric fields had footnotes -> coerced to NaN.
- Kept both wide (for comparisons) and long (for visualizations) outputs.

**What’s next (Day 5 preview)**
- Compare hospitals on key metrics (bar charts for readmit mean, HCAHPS linear mean, Safety mean).
- Explore top/bottom HCAHPS questions per hospital (from long table).
- Draft initial insights for README.
