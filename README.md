# Chicago Crime Time Series Analysis

![Python](https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge\&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-purple?style=for-the-badge\&logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)

---

## Project Overview

This project analyzes reported crime incidents in Chicago from **2001 to 2022** using time series analysis techniques.

The goal of this project is to answer stakeholder questions for a local newspaper reporter and provide clear, data-supported insights about crime trends across time, locations, rush hours, and holidays.

Unlike a classical machine learning workflow, this project does not focus on building a predictive model. Instead, it focuses on **exploratory time series analysis**, feature engineering, aggregation, and visual storytelling.

---

## Business Understanding

The main stakeholder is a local newspaper reporter who wants to understand crime patterns in Chicago.

The analysis focuses on answering questions such as:

* Which police districts had the most and least crimes in 2022?
* Is total reported crime increasing or decreasing across the years?
* Are crimes more common during AM or PM rush hour?
* Which holidays had the highest number of reported crimes?

The final goal is to turn raw crime records into clear insights that can support reporting and public understanding.

---

## Dataset

The dataset contains reported crime incidents in Chicago from **2001 to 2022**.

Each row represents one reported crime incident.

The dataset includes information such as:

* Crime date and time
* Primary crime type
* Crime description
* Police district
* Arrest status
* Domestic indicator
* Ward
* Latitude and longitude

The data was provided in yearly CSV files and combined into one dataset for analysis.

---

## Project Workflow

The workflow below summarizes the main steps used in this project.

![Project Workflow](images/workflow.png)

---

## Data Preparation

The following preparation steps were applied:

1. Loaded yearly crime files from 2001 to 2022.
2. Combined all files into one DataFrame.
3. Converted the original `Date` column into a datetime format.
4. Set `Datetime` as the index for time series analysis.
5. Created time-based features:

   * Year
   * Month
   * Month Name
   * Hour
   * Day of Week
   * Rush Hour Period
   * Holiday Name

A daily resampled version of the data was also created to represent total crime counts per day.

---

## Stakeholder Questions Analyzed

This project analyzes four main topics:

1. **Comparing Police Districts**
2. **Crimes Across the Years**
3. **AM vs PM Rush Hour**
4. **Comparing Holidays**

---

## Topic 1: Comparing Police Districts

### Question

Which district had the most crimes in 2022?
Which district had the least?

### Result

In 2022, **District 8** had the highest number of reported crimes with **14,805 crimes**.

**District 31** had the lowest number of reported crimes with only **15 crimes**.

![Police District Crimes](images/police_districts_2022.png)

### Insight

Crime distribution was not equal across police districts. Some districts had much higher crime counts than others, which may be related to population size, area activity, reporting patterns, or district boundaries.

---

## Topic 2: Crimes Across the Years

### Question

Is the total number of crimes increasing or decreasing across the years?
Are there any individual crimes that are doing the opposite?

### Result

Total reported crimes in Chicago decreased from **485,886 crimes in 2001** to **238,858 crimes in 2022**.

This represents a decrease of **247,028 crimes**, or about **50.84%**.

![Crimes Across Years](images/crimes_across_years.png)

Although overall crime decreased, some crime types increased over the same period.

The largest increases were:

* Weapons Violation
* Criminal Sexual Assault
* Deceptive Practice
* Stalking
* Homicide

![Opposite Crime Trends](images/opposite_crime_trends.png)

### Insight

The overall crime trend decreased significantly, but not all crime categories followed the same pattern. Some specific crimes increased despite the overall decline.

---

## Topic 3: AM vs PM Rush Hour

### Question

Are crimes more common during AM rush hour or PM rush hour?

For this project:

* **AM Rush Hour:** 7:00 AM to before 10:00 AM
* **PM Rush Hour:** 4:00 PM to before 7:00 PM

### Result

Crimes were more common during **PM Rush Hour**.

* PM Rush Hour: **1,206,353 crimes**
* AM Rush Hour: **770,651 crimes**

![Rush Hour Comparison](images/rush_hour_comparison.png)

The top 5 crimes during AM Rush Hour were:

1. Theft
2. Battery
3. Criminal Damage
4. Burglary
5. Other Offense

The top 5 crimes during PM Rush Hour were:

1. Theft
2. Battery
3. Criminal Damage
4. Narcotics
5. Assault

![Top Rush Hour Crimes](images/top_rush_hour_crimes.png)

Motor Vehicle Theft was also more common during PM Rush Hour:

* PM Rush Hour: **53,716 cases**
* AM Rush Hour: **41,578 cases**

![Motor Vehicle Theft Rush Hour](images/motor_vehicle_theft_rush_hour.png)

### Insight

PM rush hour had higher crime activity than AM rush hour, both in total reported crimes and in Motor Vehicle Theft.

---

## Topic 4: Comparing Holidays

### Question

What are the top 3 holidays with the largest number of crimes?
For each of the top 3 holidays, what are the top 5 most common crimes?

### Result

The top 3 holidays with the highest number of reported crimes were:

1. **New Year's Day:** 32,725 crimes
2. **Independence Day:** 22,672 crimes
3. **Labor Day:** 22,164 crimes

![Holiday Crimes](images/holiday_crimes.png)

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

![Top Holiday Crimes](images/top_holiday_crimes.png)

### Insight

New Year's Day had the highest number of reported crimes among holidays. Theft was the most common crime on New Year's Day, while Battery was the most common crime on Independence Day and Labor Day.

---

## Key Findings

* Reported crime in Chicago decreased by about **50.84%** from 2001 to 2022.
* **District 8** had the highest number of reported crimes in 2022.
* Crimes were more common during **PM Rush Hour** than AM Rush Hour.
* **Theft** was one of the most common crimes across multiple analyses.
* **New Year's Day** had the highest number of reported crimes among holidays.
* Some crime types increased even though the overall crime trend decreased.

---

## Tools and Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Holidays
* Google Colab

---

## Repository Structure

```text
chicago-crime-time-series-analysis/
│
├── README.md
├── Project3_Part1_Chicago_Crime.ipynb
│
├── images/
│   ├── workflow.png
│   ├── police_districts_2022.png
│   ├── crimes_across_years.png
│   ├── opposite_crime_trends.png
│   ├── rush_hour_comparison.png
│   ├── top_rush_hour_crimes.png
│   ├── motor_vehicle_theft_rush_hour.png
│   ├── holiday_crimes.png
│   └── top_holiday_crimes.png
│
└── data/
    └── README.md
```

---

## How to Run

1. Clone the repository.
2. Open the notebook in Google Colab or Jupyter Notebook.
3. Mount Google Drive or update the data path.
4. Run the notebook cells in order.

---

## Author

**Doha Samir**

Data Science & Machine Learning Learner
Palestine

---

## Project Status

Completed as part of **Project 3 - Part 1: Time Series Analysis**.
