# Data Dictionary (Cleaned)

## hospital_crosswalk.csv
- Provider ID (string, CCN – zero-padded 6)
- Hospital Name (string, uppercase)
- City, State, ZIP Code (string)

## hospital_clean.csv  (one row per hospital)
- Provider ID, Hospital Name, City, State, ZIP Code
- Readmission_Score_mean / _median (float): average/median of “Readmission Score” across readmission measures available in CMS file.
- Readmission_n (int): number of readmission measure rows aggregated.
- HCAHPS_LinearMean_mean (float): average of HCAHPS linear scores across questions.
- HCAHPS_Star_mean (float): average of HCAHPS star ratings.
- HCAHPS_ResponseRate_mean (float): average survey response rate (%).
- HCAHPS_n (int): distinct HCAHPS measures aggregated.
- Safety_Score_mean (float): average of safety measure scores.
- Safety_n (int): count of safety measure rows aggregated.

## hospital_measures_long.csv (long/stacked per measure)
- Provider ID, Hospital Name, City, State, ZIP Code
- Domain (Readmissions | HCAHPS | Safety)
- Measure (string): source measure text/ID
- Score (float): domain-specific score normalized to a numeric field.
