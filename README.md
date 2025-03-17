# Cyclistic Bike-Share Capstone  

## Overview  
This repository contains my capstone project analyzing Cyclistic bike-share data in Chicago, aiming to discover strategies to convert casual riders into annual members. The final report outlines the data cleaning process, key findings, and targeted recommendations.

**View the project on Kaggle:**  
- [Full Analysis on Kaggle](https://www.kaggle.com/code/nicolaslevesque/cyclistic-case-study-part-2-analysis-insights)  
- [Data Prep & Cleaning on Kaggle](https://www.kaggle.com/code/nicolaslevesque/cyclistic-case-study-data-prep-cleaning)  

## Repository Structure  
- `scripts/` - R scripts for data cleaning and analysis  
- `report/` - Final PDF of the case study ([Cyclistic_Bike-Share_Case_Study.pdf](report/Cyclistic_Bike-Share_Case_Study.pdf))  
- `README.md` - This document  

## Data Sources  
- **Divvy Trip Data (12 Months)** - Provided by Motivate International Inc. under the [Divvy Data License Agreement](https://www.divvybikes.com/data-license-agreement).  
  - Includes ride start/end times, station info, bike types, and rider types (casual or member).  

## Data Cleaning & Analysis Methods  
### 1. Merging & Initial Prep  
- Combined 12 monthly CSV files into a single dataset in R.  
- Inspected column names, data types, and overall structure.  

### 2. Imputing Missing Locations  
- Used **k-nearest neighbors (FNN in R)** to fill missing station IDs.  
- Filled missing station names by matching the most frequent name per station ID.  

### 3. Standardizing Text Fields  
- Normalized station names (lowercasing, trimming).  
- Ensured consistent mapping between station IDs and names.  

### 4. Fixing Data Types & Duplicates  
- Converted `rideable_type` and `member_casual` columns to **factor variables**.  
- Removed duplicate ride IDs using `distinct()`.  

### 5. Outliers & Final Refinements  
- Computed ride lengths (`ended_at - started_at`) and removed negative durations or rides over 24 hours.  
- Excluded zero/sub-one-minute rides (likely data errors).  
- Capped ride lengths at **2 hours** based on distribution analysis.  
- Saved the final dataset as `Cyclistic_cleaned_final.rds`.  

### 6. Visualization & Insights  
- Created **data visualizations in R** using `ggplot2`.  
- Analyzed **seasonal trends, station preferences, and ride frequencies**.  

## Key Findings  
- Casual riders take **longer but fewer** rides (mostly on weekends/afternoons).  
- Annual members take **shorter, frequent rides** (mostly on weekdays/commute hours).  
- Casual ridership **peaks in summer** and drops significantly in winter.  
- Casual riders **prefer recreational stations**, while members frequent commuter hubs.  

## Recommendations  
- **Target High-Usage Casual Riders**: Personalized incentives for frequent or long-ride users.  
- **Flexible Membership Plans**: Offer weekend/afternoon-focused memberships for leisure riders.  
- **Seasonal Marketing**: Capture casual riders in summer, and provide winter retention perks.  

## Technologies & Tools  
- RStudio  
- R (tidyverse, FNN, ggplot2, dplyr)  
- Markdown (documentation)  

## How to Replicate  
1. **Clone** this repository.  
2. **Check** the `scripts/` folder for data cleaning scripts (`data_cleaning_1.R`, `data_cleaning_2.R`, etc.).  
3. **Run** the scripts in sequence to generate `Cyclistic_cleaned_final.rds`.  
4. **Refer** to `report/Cyclistic_Bike-Share_Case_Study.pdf` for final findings and recommendations.  

## Other Ways to View This Project  
- [Full Analysis on Kaggle](https://www.kaggle.com/code/nicolaslevesque/cyclistic-case-study-part-2-analysis-insights)  
- [Data Prep & Cleaning on Kaggle](https://www.kaggle.com/code/nicolaslevesque/cyclistic-case-study-data-prep-cleaning)  

## Contact  
For questions or feedback, connect with me on **[LinkedIn](www.linkedin.com/in/nicolas-levesque-a7b49833b)** or email me at [your_email@example.com](mailto:your_email@example.com).  
