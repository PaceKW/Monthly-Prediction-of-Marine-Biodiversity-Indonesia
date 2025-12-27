# Monthly Prediction of Marine Biodiversity Observation Intensity Using Sea Surface Temperature
## Indonesia (2015 – 2025)


## Project Overview

This project aims to estimate **monthly marine biodiversity observation intensity** using **sea surface temperature (SST)** as an environmental predictor.  
The analysis focuses on demonstrating how environmental data can support estimation and exploratory analysis in **data-limited marine monitoring scenarios**.

The project does **not** attempt to predict true species abundance. Instead, it estimates patterns in **recorded biodiversity observations**, which are influenced by sampling effort and reporting availability.

---

## Why This Project Matters

From a data analysis and machine learning standpoint, this project demonstrates the ability to:

- Work with **marine biodiversity datasets** (OBIS)
- Integrate **biological and environmental data**
- Apply **machine learning** in a responsible and interpretable manner
- Handle **temporal data** using industry-standard practices
- Communicate scientific limitations clearly

---

## Datasets Used

### 1. Marine Biodiversity Observations (OBIS)

- **Source:** Ocean Biodiversity Information System (OBIS)
- **Spatial coverage:** Indonesia
- **Temporal coverage:** 2015–2025
- **Data type:** Species occurrence records
- **Field used:** `eventDate`

OBIS records represent presence-only observations and are influenced by survey effort.  
Monthly aggregated counts are interpreted as **observation intensity**, not population size.

---

### 2. Sea Surface Temperature (SST)

- **Source:** NOAA / regional SST product
- **Data type:** Environmental time series
- **Temporal resolution:** Daily (aggregated to monthly mean)
- **Fields used:** `time`, `sst`

SST is used as an environmental explanatory variable and aggregated to match the temporal resolution of biodiversity observations.

---

## Methodology  
1. Aggregate OBIS observation counts into monthly time series.  
2. Aggregate SST into monthly mean values.  
3. Merge biodiversity and SST data using year and month.  
4. Apply a train/test split (temporal) to avoid leakage.  
5. Train a simple Linear Regression model using SST as the feature.  
6. Evaluate using Root Mean Squared Error (RMSE) and visual comparison.

---

## Machine Learning Model

- **Model:** Linear Regression
- **Input Feature:** Monthly mean sea surface temperature
- **Target Variable:** Monthly biodiversity observation count

The model is intentionally simple to prioritize interpretability and reduce overfitting risks associated with limited temporal data.

---

## Key Findings  

- SST contains temporal signals that relate to observed marine biodiversity intensity.  
- The model captures broad temporal patterns but cannot fully explain variability.  
- Results are *estimates of data-limited observation patterns*, not ecological forecasts.



---

## Limitations

- Biodiversity observation intensity reflects recording activity rather than actual species abundance.
- SST alone cannot capture complex ecological drivers.
- The model is exploratory and not suitable for predictive ecological inference.
- Results depend on data availability and temporal coverage.

---

## Intended Use  

This project supports:  
- Exploratory pattern analysis  
- Research discussion and hypothesis generation  
- Preliminary modelling of data-limited marine monitoring scenarios


---

## Tools & Technologies

- Python (Pandas, NumPy, Matplotlib, Seaborn)  
- Jupyter Notebook (Kaggle)  
- Open marine biodiversity and environmental datasets  

---

## Author

**Henry Kevin**  
Background: Information Systems | Data Science | Machine Learning  
Focus: Environmental Data Analysis & Marine Biodiversity

_Notes: This analysis reflects a **junior-level, research-oriented approach** emphasizing transparency, responsible interpretation, and rigorous documentation._