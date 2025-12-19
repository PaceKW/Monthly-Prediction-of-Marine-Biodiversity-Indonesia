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

1. **Data Preparation**
   - OBIS data are aggregated into monthly observation counts.
   - SST data are aggregated into monthly mean values.

2. **Data Integration**
   - Monthly biodiversity and SST datasets are merged using year and month.

3. **Train–Test Split**
   - Temporal splitting is applied to prevent data leakage.
   - Earlier years are used for training.
   - Recent months are reserved for testing.

4. **Modeling**
   - A Linear Regression model is trained using monthly mean SST as the input feature.
   - Monthly observation count is used as the target variable.

5. **Evaluation**
   - Model performance is assessed using Root Mean Squared Error (RMSE).
   - Observed and predicted values are compared visually.

---

## Machine Learning Model

- **Model:** Linear Regression
- **Input Feature:** Monthly mean sea surface temperature
- **Target Variable:** Monthly biodiversity observation count

The model is intentionally simple to prioritize interpretability and reduce overfitting risks associated with limited temporal data.

---

## Key Findings

- Monthly sea surface temperature contains informative signal related to biodiversity observation intensity.
- The model captures general temporal patterns but does not fully explain observation variability.
- Predictions should be interpreted as **estimates for data-limited periods**, not ecological forecasts.

---

## Limitations

- Biodiversity observation intensity reflects recording activity rather than actual species abundance.
- SST alone cannot capture complex ecological drivers.
- The model is exploratory and not suitable for predictive ecological inference.
- Results depend on data availability and temporal coverage.

---

## Conclusion

This project demonstrates a realistic application of machine learning to estimate marine biodiversity observation intensity using environmental data.  
By operating at a monthly resolution and integrating biological and environmental datasets, the analysis aligns with real-world challenges in marine biodiversity monitoring.

The emphasis of this project is on **responsible modeling, transparent assumptions, and practical relevance**.

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