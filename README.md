# Chicago Crime Analysis Project

An interactive Tableau dashboard designed to analyze and visualize crime patterns, temporal trends, and geographical distributions in Chicago during 2001.

## Key Features
* **Crime by Day of Week:** Visualizes the distribution of crimes across different days.
* **Top Crime Types:** Identifies the top 10 most prevalent crimes with responsive interactive action filters.
* **Crime Locations:** Map visualization highlighting high-density crime hot-spots.
* **KPI Cards & Navigation:** Executive summary layout with clear call-to-actions.

## Dashboard Preview
![Main Dashboard](dashboard.png)

## Interactive View
You can interact with the live version of this dashboard here:
[View Live Tableau Dashboard](https://public.tableau.com/app/profile/doha.al.nabahin/viz/project_17842089936580/MainDashboard?publish=yes)

## Author
* **Daha AL_Naba...**


# 🚔 Chicago Crime Time Series Analysis

![Python](https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge\&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-purple?style=for-the-badge\&logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?style=for-the-badge)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-teal?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)

---

## 📌 Project Overview

This project analyzes reported crime incidents in **Chicago from 2001 to 2022** using **time series analysis** techniques.

The main goal is to answer stakeholder questions for a **local newspaper reporter** and provide clear, visual, and data-supported insights about crime trends across:

* 🗓️ Years
* 🏙️ Police districts
* 🚦 Rush hours
* 🎉 Holidays

Unlike a classical machine learning workflow, this project does **not** focus on building a predictive model.
Instead, it focuses on **exploratory time series analysis, feature engineering, aggregation, and visual storytelling**.

---

## 🎯 Business Understanding

The stakeholder is a local newspaper reporter who wants to better understand crime patterns in Chicago.

This analysis helps answer questions such as:

* Which police districts had the most and least crimes in 2022?
* Is reported crime increasing or decreasing over time?
* Are crimes more common during AM or PM rush hour?
* Which holidays had the highest number of reported crimes?
* What crime types are most common during these time periods?

---

## 🗂️ Dataset

The dataset contains reported crime incidents in Chicago from **2001 to 2022**.

Each row represents **one reported crime incident**.

The dataset includes:

* 🕒 Crime date and time
* 🚨 Primary crime type
* 🏙️ Police district
* 👮 Arrest status
* 🏠 Domestic indicator
* 📍 Latitude and longitude
* 🗺️ Ward and location details

The data was provided as yearly CSV files and combined into one dataset for analysis.

---

## 🔄 Project Workflow

The workflow below summarizes the steps used in this project.

📍 **Image location:** `project_workflow.png.png`

![Project Workflow](project_workflow.png)

---

## 🧹 Data Preparation

The following steps were applied before analysis:

1. Loaded yearly crime files from **2001 to 2022**.
2. Combined all files into one DataFrame.
3. Converted the `Date` column into datetime format.
4. Set `Datetime` as the time series index.
5. Sorted the data by time.
6. Created time-based features:

   * Year
   * Month
   * Month Name
   * Hour
   * Day of Week
   * Rush Hour Period
   * Holiday Name

A daily resampled version was also created where each row represents one day and the value represents total reported crimes.

---

## 📊 Stakeholder Questions Analyzed

This project analyzes **four main topics**:

| Topic       | Focus                      |
| ----------- | -------------------------- |
| 🏙️ Topic 1 | Comparing Police Districts |
| 📉 Topic 2  | Crimes Across the Years    |
| 🚦 Topic 3  | AM vs PM Rush Hour         |
| 🎉 Topic 4  | Comparing Holidays         |

---

# 🏙️ Topic 1: Comparing Police Districts

## ❓ Question

Which police district had the most crimes in 2022?
Which district had the least?

## ✅ Result

In **2022**, **District 8** had the highest number of reported crimes with **14,805 crimes**.

**District 31** had the lowest number of reported crimes with only **15 crimes**.

📍 **Image location:** `Comparing_Polic_Districts.png`

![Police District Crimes](Comparing_Polic_Districts.png)

## 💡 Insight

Crime distribution was not equal across Chicago police districts.
Some districts had much higher crime counts than others, which may be related to population size, area activity, reporting patterns, or district boundaries.

---

# 📉 Topic 2: Crimes Across the Years

## ❓ Question

Is the total number of crimes increasing or decreasing across the years?
Are there any individual crimes moving in the opposite direction?

## ✅ Result

Total reported crimes in Chicago decreased from **485,886 crimes in 2001** to **238,858 crimes in 2022**.

This represents a decrease of **247,028 crimes**, or about **50.84%**.

📍 **Image location:** `Crimes_Across_the_Years.png`

![Crimes Across Years](Crimes_Across_the_Years.png)

Although overall crime decreased, some crime types increased over the same period.

The largest increases included:

* 🚨 Weapons Violation
* 🚨 Criminal Sexual Assault
* 🚨 Deceptive Practice
* 🚨 Stalking
* 🚨 Homicide

📍 **Image location:** `Opposite_Crime_Trends.png`

![Opposite Crime Trends](Opposite_Crime_Trends.png)

## 💡 Insight

The overall crime trend decreased significantly, but not every crime category followed the same pattern.
Some crime types increased despite the overall decline, which highlights the importance of analyzing both total crime and individual crime categories.

---

# 🚦 Topic 3: AM vs PM Rush Hour

## ❓ Question

Are crimes more common during AM rush hour or PM rush hour?

For this project:

* 🌅 **AM Rush Hour:** 7:00 AM to before 10:00 AM
* 🌆 **PM Rush Hour:** 4:00 PM to before 7:00 PM

## ✅ Result

Crimes were more common during **PM Rush Hour**.

| Rush Hour Period | Reported Crimes |
| ---------------- | --------------: |
| 🌅 AM Rush Hour  |         770,651 |
| 🌆 PM Rush Hour  |       1,206,353 |

📍 **Image location:** `AM_vs_PM_Rush_Hour.png`

![Rush Hour Comparison](AM_vs_PM_Rush_Hour.png)

The top 5 crimes during **AM Rush Hour** were:

1. Theft
2. Battery
3. Criminal Damage
4. Burglary
5. Other Offense

The top 5 crimes during **PM Rush Hour** were:

1. Theft
2. Battery
3. Criminal Damage
4. Narcotics
5. Assault

📍 **Image location:** `The_top_5_crimes.png`

![Top Rush Hour Crimes](The_top_5_crimes.png)

Motor Vehicle Theft was also more common during **PM Rush Hour**:

| Period          | Motor Vehicle Theft Cases |
| --------------- | ------------------------: |
| 🌅 AM Rush Hour |                    41,578 |
| 🌆 PM Rush Hour |                    53,716 |

📍 **Image location:** `Motor_Vehicle_Theft.png`

![Motor Vehicle Theft Rush Hour](Motor_Vehicle_Theft.png)

## 💡 Insight

PM rush hour had higher crime activity than AM rush hour.
Theft was the most common crime in both periods, and Motor Vehicle Theft was also higher during PM rush hour.

---

# 🎉 Topic 4: Comparing Holidays

## ❓ Question

What are the top 3 holidays with the largest number of crimes?
For each holiday, what are the top 5 most common crimes?

## ✅ Result

The top 3 holidays with the highest number of reported crimes were:

| Holiday               | Reported Crimes |
| --------------------- | --------------: |
| 🎆 New Year's Day     |          32,725 |
| 🇺🇸 Independence Day |          22,672 |
| 👷 Labor Day          |          22,164 |

📍 **Image location:** `Comparing_Holidays.png`

![Holiday Crimes](Comparing_Holidays.png)

For **New Year's Day**, the top crimes were:

* Theft
* Battery
* Criminal Damage
* Deceptive Practice
* Offense Involving Children

For **Independence Day**, the top crimes were:

* Battery
* Theft
* Criminal Damage
* Assault
* Narcotics

For **Labor Day**, the top crimes were:

* Battery
* Theft
* Criminal Damage
* Narcotics
* Assault

📍 **Image location:** `Top_Holiday_Crimes.png`

![Top Holiday Crimes](Top_Holiday_Crimes.png)

## 💡 Insight

**New Year's Day** had the highest number of reported crimes among holidays.
Theft was the most common crime on New Year's Day, while Battery was the most common crime on Independence Day and Labor Day.

---
---

# 🔮 Part 2: Crime Forecasting for Resource Allocation

## 📌 Forecasting Objective

In the second phase of this project, the goal was to help Chicago law enforcement allocate resources for the next **6 months** by forecasting future monthly crime counts.

Two crime types were selected for forecasting:

* 🧾 **Theft**
* 💊 **Narcotics**

The purpose of this phase is to compare the expected future trends for these two crimes and provide a recommendation for resource planning.

---

## 📈 Monthly Crime Count Time Series

The original crime-level dataset was transformed into monthly crime counts using `.resample("MS").size()`.

Each row in the new time series represents one month, and the value represents the number of reported crimes during that month.

📍 **Image location:** `Monthly_Theft_vs_Narcotics.png`

![Monthly Theft vs Narcotics](Monthly_Theft_vs_Narcotics.png)

### Insight

The monthly time series shows that **Theft consistently had higher monthly counts** than Narcotics. Theft also shows a clear seasonal pattern, while Narcotics shows a strong long-term decreasing trend.

---

## 🔍 Seasonality and Decomposition

Seasonal decomposition was used to separate each time series into trend, seasonal, and residual components.

For **Theft**, the seasonal component represented about **32.08%** of the total variation, indicating a meaningful yearly seasonal pattern.

For **Narcotics**, the seasonal component represented about **9.76%** of the total variation, which is weaker than Theft but still shows some repeating yearly pattern.

📍 **Image location:** `Theft_Decomposition.png`

![Theft Decomposition](Theft_Decomposition.png)

📍 **Image location:** `Narcotics_Decomposition.png`

![Narcotics Decomposition](Narcotics_Decomposition.png)

### Model Decision

Since the data is monthly and both crime types showed seasonal behavior, a seasonal model was explored using a 12-month seasonal period:

**m = 12**

---

## ⚙️ Model Development

For both Theft and Narcotics, the following forecasting workflow was applied:

1. Created monthly crime count time series.
2. Checked for missing values.
3. Performed seasonal decomposition.
4. Determined differencing values:

   * Theft: `d = 1`, `D = 0`
   * Narcotics: `d = 1`, `D = 0`
5. Used ACF and PACF plots to estimate initial orders.
6. Split the data into training and testing sets.
7. Used the last **6 months** as the test set.
8. Fit a manual SARIMA model.
9. Tuned using `auto_arima`.
10. Compared the models using MAE, RMSE, and MAPE.
11. Selected the final model.
12. Generated true future forecasts for January 2023 to June 2023.

The initial manual model used for both crime types was:

**SARIMA(1,1,1)(1,0,1,12)**

---

## 🧪 Manual SARIMA vs Auto ARIMA

The manual SARIMA model and auto_arima model were compared using evaluation metrics.

| Crime Type | Selected Model |    MAE |   RMSE |   MAPE |
| ---------- | -------------- | -----: | -----: | -----: |
| Theft      | Manual SARIMA  | 200.67 | 241.69 |  3.92% |
| Theft      | Auto ARIMA     | 211.59 | 269.82 |  4.27% |
| Narcotics  | Manual SARIMA  |  51.58 |  60.59 | 14.82% |
| Narcotics  | Auto ARIMA     |  89.64 | 104.44 | 25.67% |

### Final Model Selection

The **manual SARIMA model** was selected as the final model for both Theft and Narcotics because it produced lower MAE, RMSE, and MAPE compared to auto_arima.

---

## 📊 Forecast vs Test Data

The final manual SARIMA model was evaluated by comparing its forecast against the actual test data.

📍 **Image location:** `Theft_Forecast_vs_Test.png`

![Theft Forecast vs Test](Theft_Forecast_vs_Test.png)

📍 **Image location:** `Narcotics_Forecast_vs_Test.png`

![Narcotics Forecast vs Test](Narcotics_Forecast_vs_Test.png)

### Insight

The Theft model performed very well with a low MAPE of **3.92%**.
The Narcotics model had a higher MAPE of **14.82%**, mainly because Narcotics has much lower monthly counts, making percentage errors more sensitive.

---

## 🔮 6-Month Future Forecast

After selecting the final model, the manual SARIMA model was refit using the full dataset and used to forecast the next 6 months beyond the dataset:

**Forecast period:** January 2023 to June 2023

📍 **Image location:** `Theft_6_Month_Future_Forecast.png`

![Theft Future Forecast](Theft_6_Month_Future_Forecast.png)

📍 **Image location:** `Narcotics_6_Month_Future_Forecast.png`

![Narcotics Future Forecast](Narcotics_6_Month_Future_Forecast.png)

---

## 📌 Future Forecast Results

| Crime Type | Forecast Start | Forecast End | Starting Value | Final Value | Net Change | Percent Change |
| ---------- | -------------- | ------------ | -------------: | ----------: | ---------: | -------------: |
| Theft      | Jan 2023       | Jun 2023     |       4,120.41 |    4,771.85 |    +651.44 |        +15.81% |
| Narcotics  | Jan 2023       | Jun 2023     |         406.55 |      266.02 |    -140.54 |        -34.57% |

📍 **Image location:** `Forecasted_Final_Month_Count.png`

![Forecasted Final Month Count](Forecasted_Final_Month_Count.png)

📍 **Image location:** `Forecasted_Percent_Change.png`

![Forecasted Percent Change](Forecasted_Percent_Change.png)

---

## ✅ Forecasting Insights

* **Theft** is forecasted to have the highest monthly count at the end of the forecast period.
* **Theft** is forecasted to have the highest net increase, with about **651 additional crimes**.
* **Theft** is expected to increase by **15.81%**.
* **Narcotics** is expected to decrease by **34.57%**.
* Although Narcotics has a larger percentage change in magnitude, it is decreasing, while Theft is increasing.

---

## 🧭 Final Recommendation

Based on the 6-month future forecasts, law enforcement should prioritize additional resources toward **Theft-related prevention and response**.

Theft is expected to increase from approximately **4,120 crimes in January 2023** to approximately **4,772 crimes in June 2023**, representing a predicted increase of **651 crimes**.

In contrast, Narcotics is forecasted to decrease during the same period.

Therefore, the main recommendation is to increase focus on Theft prevention, especially during the months leading into summer 2023. This may include increased patrols in high-theft areas, targeted public awareness campaigns, and closer monitoring of locations with historically high theft activity.

---


## 🔑 Key Findings

* 📉 Reported crime in Chicago decreased by about **50.84%** from 2001 to 2022.
* 🏙️ **District 8** had the highest number of reported crimes in 2022.
* 🚦 Crimes were more common during **PM Rush Hour** than AM Rush Hour.
* 🧾 **Theft** was one of the most common crimes across multiple analyses.
* 🎆 **New Year's Day** had the highest number of reported crimes among holidays.
* ⚠️ Some crime types increased even though the overall crime trend decreased.
* 🔮 In the forecasting phase, **Theft** was predicted to increase by **15.81%** over the next 6 months.
* 💊 **Narcotics** was predicted to decrease by **34.57%** over the next 6 months.
* 🧭 The final recommendation is to prioritize law enforcement resources toward **Theft prevention and response**.


---

## 🛠️ Tools and Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Holidays
* Statsmodels
* Pmdarima
* Google Colab

---

## 📁 Repository Structure

```text
chicago-crime-time-series-analysis/
│
├── README.md
├── Project3_Part1_Chicago_Crime.ipynb
│
├── images/
│   ├── Project_Workflow.png
│   ├── Comparing_Polic_Districts.png
│   ├── Crimes_Across_the_Years.png
│   ├── Opposite_Crime_Trends.png
│   ├── AM_vs_PM_Rush_Hour.png
│   ├── The_top_5_crimes.png
│   ├── Motor_Vehicle_Theft.png
│   ├── Comparing_Holidays.png
│   ├── Top_Holiday_Crimes.png
│   ├── Monthly_Theft_vs_Narcotics.png
│   ├── Theft_Decomposition.png
│   ├── Narcotics_Decomposition.png
│   ├── Theft_Forecast_vs_Test.png
│   ├── Narcotics_Forecast_vs_Test.png
│   ├── Theft_6_Month_Future_Forecast.png
│   ├── Narcotics_6_Month_Future_Forecast.png
│   ├── Forecasted_Final_Month_Count.png
│   └── Forecasted_Percent_Change.png
│
└── data/
    └── README.md
```
---

## ▶️ How to Run

1. Clone this repository.
2. Open the notebook in Google Colab or Jupyter Notebook.
3. Mount Google Drive or update the data path.
4. Run the notebook cells in order.

---

## 👩‍💻 Author

**Doha Samir**

Data Science & Machine Learning Learner
Palestine 🇵🇸

---

## ✅ Project Status

Completed as part of **Project 3: Chicago Crime Time Series Analysis and Forecasting**.
