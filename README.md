# 📌 OptiRide: Data-Driven Public Transport Optimization

🚍 **OptiRide** is a comprehensive data analysis project aimed at optimizing public transportation based on real-world datasets. This project utilizes **Python, Pandas, Matplotlib, Seaborn**, and **Power BI** to analyze **passenger demand, traffic impact, weather conditions, and peak-hour trends** for improved transit scheduling and efficiency.

---

## 📖 Table of Contents  
- [📊 Data Overview](#-data-overview)  
- [🔍 Exploratory Data Analysis (EDA)](#-exploratory-data-analysis-eda)  
- [📈 Key Insights](#-key-insights)  
- [🚀 Recommendations](#-recommendations)  
- [💻 Code Implementation](#-code-implementation)  
- [📊 Visualization Using Power BI](#-visualization-using-power-bi)  
- [🔮 Future Enhancements](#-future-enhancements)  

---

## 📊 Data Overview  
The dataset contains **passenger demand trends, traffic levels, weather conditions, and timestamps** to help analyze and optimize public transport operations.  

| Column Name         | Description                                      |
|---------------------|--------------------------------------------------|
| `timestamp`        | Date and time of data collection                 |
| `hour`            | Hour of the day (0-23)                            |
| `day_of_week`     | Day of the week (Monday-Sunday)                   |
| `passenger_count` | Number of passengers on board                     |
| `weather`         | Weather condition (Sunny, Cloudy, Rainy)          |
| `traffic_level`   | Traffic congestion (Low, Medium, High)            |

---

## 🔍 Exploratory Data Analysis (EDA)  
### 1️⃣ Data Cleaning  
```python
import pandas as pd

# Load dataset
df = pd.read_csv("OptiRide_Dataset.csv")

# Checking for missing values
print(df.isnull().sum())

# Dropping NaN values if any
df.dropna(inplace=True)
```
✅ **Result:** The dataset is clean with no missing values.  

### 2️⃣ Peak & Off-Peak Hours Analysis  
```python
# Group by hour and calculate average passenger count
hourly_avg = df.groupby("hour")["passenger_count"].mean().reset_index()
print(hourly_avg.sort_values(by="passenger_count", ascending=False).head(10))
```
✅ **Result:** Peak hours are **7 PM - 9 PM** with high passenger counts, while off-peak hours are **3 AM - 6 AM** with low demand.  

---

## 📈 Key Insights  
### ⏳ Peak Hours Analysis  
- **Peak Demand:** **7 PM - 9 PM**, with an average of **18.03 passengers** (vs. overall **15.14**).  
- **Highest Demand:** **9 PM** (**19.28 passengers**).  
- **Recommendation:** Increase bus frequency by **20%** during peak hours.  

### 🌙 Off-Peak Hours Analysis  
- **Lowest Demand:** **3 AM - 6 AM** (average **12.85 passengers**).  
- **Lowest Hour:** **3 AM** (**11.91 passengers**).  
- **Recommendation:** Reduce bus frequency by **15%** to optimize costs.  

### 🌦 Weather Impact  
| Weather | Avg Passenger Count |
|---------|---------------------|
| 🌧 Rainy  | **15.54**  |
| ☁ Cloudy  | **15.27**  |
| ☀ Sunny   | **15.02**  |
- **Observation:** Weather has **minimal impact** on demand.  
- **Recommendation:** Slightly increase frequency (+5%) during rainy **peak hours**.  

### 🚦 Traffic Impact  
| Traffic Level | Avg Passenger Count |
|--------------|---------------------|
| 🟢 Low      | **15.06**  |
| 🟡 Medium   | **15.81**  |
| 🔴 High     | **14.96**  |
- **Observation:** Medium traffic **slightly increases demand**, possibly due to public transport preference.  
- **Recommendation:** Monitor **real-time traffic** and reroute buses dynamically.  

### 📅 Day-of-Week Impact  
| Day         | Avg Passenger Count |
|------------|---------------------|
| 📆 Friday  | **15.43**  |
| 📆 Saturday | **14.71**  |
- **Observation:** Minimal impact on demand between Friday & Saturday.  
- **Recommendation:** No drastic changes required.  

---

## 🚀 Recommendations  
✅ **Increase Frequency During Peak Hours** (+20%)  
✅ **Reduce Frequency During Off-Peak Hours** (-15%)  
✅ **Real-Time Traffic Monitoring & Dynamic Rerouting**  
✅ **Implement Dynamic Pricing Model (Peak Hours +10%, Off-Peak -10%)**  
✅ **Passenger Information Systems for Real-Time Bus Tracking**  
✅ **Partner with Ride-Sharing for Last-Mile Connectivity**  
✅ **Discounts for Off-Peak Travel to Shift Demand**  

---

## 💻 Code Implementation  

### 🔹 Peak & Off-Peak Hour Visualization  
```python
import matplotlib.pyplot as plt

# Plotting passenger count trends
plt.figure(figsize=(10,5))
plt.plot(hourly_avg["hour"], hourly_avg["passenger_count"], marker="o", linestyle="-")
plt.xlabel("Hour of the Day")
plt.ylabel("Avg Passenger Count")
plt.title("Passenger Demand by Hour")
plt.grid(True)
plt.show()
```
✅ **Output:** Graph shows peak demand from **7 PM - 9 PM** and a drop at **3 AM - 6 AM**.  

---

## 📊 Visualization Using Power BI  
*(Placeholder for Power BI images, add screenshots here)*  
🖼️ **Peak Hour Analysis**  
🖼️ **Weather vs. Passenger Count**  
🖼️ **Traffic Impact Visualization**  

---

## 🔮 Future Enhancements  
🚀 **AI-Based Demand Prediction Model** using Machine Learning.  
🚀 **Integration with GPS for Real-Time Bus Tracking.**  
🚀 **Automated Traffic-Based Route Optimization.**  
🚀 **Sustainability Initiatives: Optimizing Electric Buses Deployment.**  

---

## 🎯 Contributing  
Want to improve OptiRide? Feel free to fork this repo, make enhancements, and submit a PR! Contributions are always welcome. 🚀  

---

## 💡 Conclusion  
OptiRide provides **data-driven insights** to optimize public transport operations. By leveraging **peak-hour adjustments, traffic monitoring, and dynamic pricing**, we can **enhance efficiency and reduce costs** while improving passenger convenience.  

---

### ⭐ Like this project? Give it a star! ⭐  

🔗 **Connect with me on [LinkedIn](#) | [GitHub](#)**  
