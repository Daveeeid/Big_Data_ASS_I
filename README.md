# Big_Data_ASS_I
# 🚖 Uber Fare Dataset Analysis

## 📌 Project Overview
This project analyzes Uber NYC ride data to uncover fare trends, time-based patterns, and geographic ride distribution using Python and Power BI.

## 🧰 Tools Used
- Python (Pandas, NumPy, Seaborn)
- Power BI Desktop
- GitHub

## 📁 Dataset Summary
- **Source**: Kaggle (Uber Fares NYC)
- **Records**: 200,000 rows
- **Fields**: fare_amount, pickup/dropoff datetime, coordinates, passenger count

## 🧼 Data Cleaning
- Handled missing values
- Removed invalid or extreme fare amounts and coordinates
- Filtered for reasonable geographic bounds (lat/lon around NYC)

## 🛠 Feature Engineering  

![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/new%20columns.jpg?raw=true
)
- Calculated `trip_distance` using Haversine formula
- Extracted `pickup_hour`, `pickup_day`, `pickup_month`, and `pickup_day_of_week`
- Created `peak_time` feature based on ride hour (e.g., 7–9 AM, 4–7 PM)

## 📊 Key Visuals & Insights  
## General Dashboard view  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/dashboard.png?raw=true)
### 💰 Average Fare by Hour of Day
- Fares spike in early morning and late afternoon
- Possible surge pricing effects

### 📈 Ride Volume by Hour
- Most rides occur between 4–7 PM
- Lowest volume between 2–5 AM

### 🔁 Peak vs Off-Peak Ride Share  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/peak%20vs%20off-peak.png?raw=true)
- Over 65% of rides occur during peak hours

### 🔥 Busiest Ride Times Heatmap  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/heat%20map.png?raw=true)
- Fridays between 5–7 PM show the highest ride counts

### 🌍 Pickup Location Map  
![image alt](https://github.com/Daveeeid/Big_Data_ASS_I/blob/main/ass_screanshots/new%20york.png?raw=true)
- Most pickups cluster in Manhattan and Brooklyn

## 🧠 Summary of Findings
- Ride demand follows strong time-of-day and weekday patterns
- Fare amounts vary by hour but stay consistent across weekdays
- NYC traffic rhythms likely impact ride demand

## 💡 Recommendations
- Introduce targeted incentives for drivers during low-volume hours
- Consider price adjustments during peak periods
- Integrate external data (e.g., weather, holidays) for deeper insights

## 📎 Files Included
- `cleaned_uber_fares.csv`
- `enhanced_uber_fares_cleaned.csv`
- `Uber_Fare_Analysis_Dashboard.pbix`
- `screenshots/` folder
- `README.md` (this file)

## 👨‍💻 Author
David Muhirwa – AUCA, INSY 8413 – July 2025
