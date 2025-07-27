# Big_Data_ASS_I
Names: MUHIRWA David  
ID:27436, July 2025
#  Uber Fare Dataset Analysis

##  Project Overview
This project analyzes Uber NYC ride data to uncover fare trends, time-based patterns, and geographic ride distribution using Python and Power BI.

##  Tools Used
- Python (Pandas, NumPy, Seaborn)
- Power BI Desktop
- GitHub

##  Dataset Summary
- **Source**: Kaggle (Uber Fares NYC)
- **Records**: 200,000 rows
- **Fields**: fare_amount, pickup/dropoff datetime, coordinates, passenger count

## Loading Data  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/loading_data.jpg?raw=true)

##  Data Cleaning  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/data%20cleaning.jpg?raw=true)
- Handled missing values
- Removed invalid or extreme fare amounts and coordinates
- Filtered for reasonable geographic bounds (lat/lon around NYC)
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/descriptive%20stats.jpg?raw=true)
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/result%20of%20stats.jpg?raw=true)
##  Descriptive Statistics

Using Python, we generated key descriptive statistics to understand the spread and central tendencies of key variables such as fare amounts, trip distance, and passenger count.

- `mean`: Average fare was approximately $10.42
- `median`: The 50th percentile fare is around $8.00
- `standard deviation`: $9.52 (high variability)
- `max fare`: $450 — an outlier worth further inspection

These metrics helped us decide what data to filter and what patterns to explore deeper in Power BI.

![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/fare%20amount%20distrib%20and%20outlier.jpg?raw=true) 
### Histogram of Fare Amounts  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/fare%20amount%20distrib%20results.jpg?raw=true)


We plotted a histogram to explore how Uber fares are distributed across the dataset.

- The majority of fares fall between $5 and $15
- The distribution is **right-skewed**, indicating a few very high fare values (possible long trips or surge pricing)
- Kernel Density Estimate (KDE) helps visualize the overall shape of the distribution

This insight is useful for setting thresholds when identifying outliers and building pricing strategies.
## Outlier Detection
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/outlier%20detect%20result.jpg?raw=true)  

We used the Interquartile Range (IQR) method to detect extreme values in `fare_amount`.

- Q1 (25th percentile): $5.00  
- Q3 (75th percentile): $12.00  
- IQR: $7.00  
- Lower bound: Q1 - 1.5×IQR = -5.50  
- Upper bound: Q3 + 1.5×IQR = $22.50

Any fare below $0 or above $22.50 is considered an outlier.

### Insights:
- Over **XX,000** fare outliers were detected.
- Most outliers are extremely high fares (some over $400).
- These were removed to avoid skewing average calculations and visuals.

A box plot was also created to visually inspect the spread and highlight these extreme values.


##  Feature Engineering  

![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/new%20columns.jpg?raw=true
)
- Calculated `trip_distance` using Haversine formula
- Extracted `pickup_hour`, `pickup_day`, `pickup_month`, and `pickup_day_of_week`
- Created `peak_time` feature based on ride hour (e.g., 7–9 AM, 4–7 PM)

##  Key Visuals & Insights  
## General Dashboard view  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/dashboard.png?raw=true)
###  Average Fare by Hour of Day  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/avg%20fare%20by%20hr.png?raw=true)
- Fares spike in early morning and late afternoon
- Possible surge pricing effects

###  Ride Volume by Hour
- Most rides occur between 4–7 PM
- Lowest volume between 2–5 AM

###  Peak vs Off-Peak Ride Share  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/peak%20vs%20off-peak.png?raw=true)
- Over 65% of rides occur during peak hours

###  Busiest Ride Times Heatmap  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/heat%20map.png?raw=true)
- Fridays between 5–7 PM show the highest ride counts

###  Pickup Location Map  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/new%20york.png?raw=true)
- Most pickups cluster in Manhattan and Brooklyn

##  Summary of Findings
- Ride demand follows strong time-of-day and weekday patterns
- Fare amounts vary by hour but stay consistent across weekdays
- NYC traffic rhythms likely impact ride demand

##  Recommendations
- Introduce targeted incentives for drivers during low-volume hours
- Consider price adjustments during peak periods
- Integrate external data (e.g., weather, holidays) for deeper insights

##📎 Files Included
- `cleaned_uber_fares.csv`
- `enhanced_uber_fares_cleaned.csv`
- `Uber_Fare_Analysis_Dashboard.pbix`
- `screenshots/` folder
- `README.md` (this file)

