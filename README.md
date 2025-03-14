# Cyclistic Bike-Share Capstone

## Overview
This repository contains my capstone project analyzing Cyclistic bike-share data in Chicago, with the goal of discovering strategies to convert casual riders into annual members. The final report outlines the data cleaning process, key findings, and targeted recommendations.

## Repository Structure
- `scripts/`: R scripts used for data cleaning and analysis  
- `report/`: Final PDF of the case study (Cyclistic_Bike-Share_Case_Study.pdf)  
- `README.md`: This document

## Data Sources
- **Divvy Trip Data (12 Months)**: Provided by Motivate International Inc. under the [Divvy Data License Agreement](https://www.divvybikes.com/data-license-agreement).  
  - Contains ride start/end times, station info, bike types, and rider types (casual or member).

## Data Cleaning & Analysis Methods
1. **Merging & Initial Prep**  
   - Combined 12 monthly CSV files into a single dataset in R.  
   - Inspected column names, data types, and overall structure.

2. **Imputing Missing Locations**  
   - Used k-nearest neighbors (via the `FNN` package in R) to fill missing station IDs.  
   - Filled missing station names by matching the most frequent name per station ID.

3. **Standardizing Text Fields**  
   - Normalized station name spellings (lowercasing, trimming).  
   - Ensured consistent mapping between station IDs and names.

4. **Fixing Data Types & Duplicates**  
   - Converted `rideable_type` and `member_casual` columns to factors.  
   - Removed duplicate ride IDs using `distinct()`.

5. **Outliers & Final Refinements**  
   - Computed ride lengths (`ended_at - started_at`) and removed negative durations or rides over 24 hours.  
   - Excluded zero/sub-one-minute rides (likely data errors).  
   - Capped ride lengths at 2 hours after distribution analysis.  
   - Saved the final dataset as `Cyclistic_cleaned_final.rds`.

6. **Visualization & Insights**  
   - Created charts in R (e.g., using `ggplot2`) to highlight differences between casual riders and members.  
   - Analyzed seasonal trends, station preferences, and ride frequencies.

## Key Findings
- **Longer but fewer rides by casual riders** (often on weekends/afternoons).  
- **Shorter, more frequent rides by members** (often on weekdays/commuting hours).  
- **Strong seasonal bias** for casual riders (peaking in summer, dropping in winter).  
- **Station usage differences**: casual riders favor recreational areas, members frequent commuter hubs.

## Recommendations
- **Target High-Usage Casual Riders**: Tailored incentives for those taking multiple or longer rides.  
- **Flexible Membership Options**: Weekend/afternoon-focused plans for leisure riders.  
- **Seasonal Marketing Campaigns**: Capitalize on summer ridership, offer winter perks to retain casual users.

## Technologies & Tools
- **RStudio**  
- **R** (tidyverse, FNN, ggplot2, etc.)  
- **Markdown** (documentation)

## How to Replicate
1. **Clone** this repository.  
2. **Check** the `scripts/` folder for data cleaning scripts (e.g., `data_cleaning_1.R`, `data_cleaning_2.R`, etc.).  
3. **Run** the scripts in sequence to produce `Cyclistic_cleaned_final.rds`.  
4. **Refer** to `report/Cyclistic_Bike-Share_Case_Study.pdf` for the final findings and recommendations.

## References
- [Motivate International Inc. Divvy Data License Agreement](https://www.divvybikes.com/data-license-agreement)

## Contact
If you have questions or feedback, feel free to reach out via [LinkedIn](#) or email me at [your_email@example.com](mailto:your_email@example.com).
