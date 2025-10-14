# Day 3 Exploration Summary
_Repo:_ hospital-performance-bradenton-sarasota  
_Date:_ 2025-10-12

## Files Loaded
- 2025-10-11_hospital_general_information.csv
- 2025-10-11_readmissions.csv
- 2025-10-11_hcahps_hospital.csv
- 2025-10-11_complications_deaths.csv

## Dataset Structure (high level)
- General Info: rows=…, cols=… | key columns: (Hospital Name/Facility Name, Provider ID/CCN, City, State, ZIP)
- Readmissions: rows=…, cols=… | key columns: (Provider ID/CCN, Measure Name, Score, Footnotes…)
- HCAHPS: rows=…, cols=… | key columns: (Provider ID/CCN, Measure ID/Name, HCAHPS Linear Mean…)
- Safety (Complications & Deaths): rows=…, cols=… | key columns: (Provider ID/CCN, Measure ID/Name, Score)

## Presence of Local Hospitals (by name search)
- Manatee Memorial Hospital: found in General, Readmissions, HCAHPS, Safety
- HCA Florida Blake Hospital: found in General, Readmissions, HCAHPS, Safety
- Lakewood Ranch Medical Center: found in General, Readmissions, HCAHPS, Safety
- Sarasota Memorial Hospital: found in General, Readmissions, HCAHPS, Safety

> If any show “0 matches” in a dataset, use the dataset’s exact spelling and re-run.

## Notes / Next Steps
- CCN/Provider ID will be the join key for Week 2 cleaning.
- Next: standardize IDs, select measures, and produce cleaned tables in `1_datasets/cleaned/`.
