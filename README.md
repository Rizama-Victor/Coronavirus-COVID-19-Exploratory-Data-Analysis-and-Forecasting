# Coronavirus (COVID-19) 🧬 Exploratory Data Analysis 📊 and Forecasting
This repository contains the implementation of my project titled _"COVID-19 Exploratory Data Analysis and Forecasting"_, at the National Centre for Artificial Intelligence and Robotics (NCAIR), Nigeria.

---

## 🧠 Overview

This project explored global COVID-19 data covering `confirmed`, `recovered`, and `death` cases recorded between January 2020 and May 2021, categorized by country and province. The dataset provided key metrics reflecting the pandemic’s progression and its varying impact across regions. 
Using this data, the project aimed to perform an in-depth analysis and develop a forecasting model to forecast future death cases in each province or state for every country.

---

## 🎯 Project Objectives

- To develop a forecasting model using the COVID-19 data spanning January 2020 to May 2021.
- To perform an in-depth exploratory analysis of the dataset to uncover key insights and patterns related to the pandemic’s spread and impact.

---

## 🤖 Tools and Technologies Used

| Category | Tools / Libraries | Description |
|-----------|------------------|--------------|
| **Programming Language** | Python | Core language used for data analysis, visualization, and forecasting. |
| **Data Handling** | pandas, numpy | Used for data cleaning, transformation, and manipulation. |
| **Visualization** | matplotlib, seaborn, plotly (express & graph_objects), powerBI | Assisted in creating both static and interactive visualizations for data exploration. |
| **Statistical Analysis** | scipy (zscore, boxcox) | Used for outlier detection and transformation of skewed data. |
| **Forecasting Model** | Prophet | Used for time-series forecasting of COVID-19 cases and deaths. |
| **Machine Learning Utility** | sklearn.preprocessing (LabelEncoder) | Encoded categorical data for model compatibility. |
| **Country Mapping** | pycountry | Mapped ISO country codes to country names for geographical analysis. |
| **Model Evaluation** | prophet.diagnostics (cross_validation) | Used to evaluate model performance and accuracy. |

----

## 🔬 Step-by-Step-Procedure

1. **Data acquisition:**  
   The raw COVID-19 dataset covering **January 2020 – May 2021** was loaded into the notebook (`pandas.read_csv` was used for CSV import).

2. **Initial inspection:**  
   The data was inspected for shape, missing values, column names, and basic statistics using functions like `head()`, `info()`, and `describe()`. Date columns were parsed into the `datetime` type.

3. **Data cleaning:**  
   Missing or malformed rows and irrelevant columns were removed or corrected. Date/time formats were unified, and duplicate records were dropped to ensure consistency.

4. **Data type conversion & encoding:**  
   Numerical columns were converted to numeric types where necessary, while categorical fields were encoded using `LabelEncoder` from `sklearn.preprocessing`.

5. **Outlier detection & transformation:**  
   Outliers and skewed distributions were detected using statistical methods (e.g., `zscore` from `scipy.stats`) and corrected with appropriate transformations such as Box-Cox where needed.

6. **Aggregation & grouping:**  
   The data was then aggregated by **country** and **province/state**, and resampled to consistent time intervals (daily counts), creating time series for confirmed, recovered, and death cases.

7. **Country code mapping:**  
   Country identifiers were normalized and mapped to full country names using the `pycountry` library to maintain uniform geographic labels.

8. **Exploratory data analysis (EDA):**  
   Visual and numeric EDA was conducted using `matplotlib`, `seaborn`, and `plotly` to analyze trends, seasonal patterns, growth rates, and regional variations.

9. **Feature preparation for forecasting:**  
   Columns were restructured to match the Prophet model’s input format (e.g., `ds` for date and `y` for target values). Missing dates were filled or forward-filled to maintain time continuity.

10. **Transformations & seasonality checks:**  
    The data was tested for seasonality and stationarity, and transformations were applied where necessary to stabilize variance and improve model fitting.

11. **Model selection & setup:**  
    The **Facebook Prophet** model was chosen for time-series forecasting. Model parameters were tuned to account for trend, weekly, and yearly seasonal effects.

12. **Model training:**  
    The Prophet model was trained on historical data up to May 2021 for each province/country to predict death cases.

13. **Cross-validation & evaluation:**  
    Model accuracy was evaluated using Prophet’s built-in cross-validation utilities (`prophet.diagnostics.cross_validation`) to calculate forecasting error and stability.

14. **Forecast generation:**  
    The trained models generated future forecasts for each country/province, including forecast intervals to account for uncertainty.

15. **Visualization of forecasts:**  
    Finally, Forecasts and actual data were visualized using Prophet’s plotting utilities and interactive visualizations to compare forecasts against historical trends.

---
## 📈 Evaluation Metrics

| **Metric** | **Value** |**Remarks** |
|-------------|-------------|-------------|
| **Mean Absolute Error (MAE)** | 122.02 |Indicated that, on average, the model’s forecasted COVID-19 death counts deviated by about 122 cases from the actual values, a relatively small error given the large dataset and global scale of analysis. |
| **Mean Absolute Percentage Error (MAPE)** | 32.77% |Showed that the model achieved a moderate level of forecasting accuracy, with forecasts deviating by roughly 33% from true values. |
| **Coefficient of Determination (R²)** | 0.989 |Reflected an excellent model fit, meaning approximately **98.9%** of the variance in observed COVID-19 deaths was accurately captured by the forecasting model, demonstrating strong forecastive capability. |

---

<p align="center">
    <img src="Visualization of the COVID-19 Exploratory Analysis on PowerBI Dashboard.png" alt="Visualization of the COVID-19 Exploratory Analysis on PowerBI Dashboard" width="1500"/>
    <br>
    <em> Visualization of the COVID-19 Exploratory Analysis on PowerBI Dashboard</em>
</p>

---
## 💡 Key Findings

- **Global trend:** COVID-19 cases and deaths showed a sharp rise between **March 2020 and February 2021**, with multiple peaks corresponding to major outbreak waves.  
- **Regional variation:** Countries such as **the United States, India, and Brazil** recorded the highest confirmed and death counts, while smaller nations showed comparatively lower impact.  
- **Recovery rates:** Regions with earlier implementation of health measures (e.g., lockdowns, vaccination campaigns) recorded higher recovery trends and slower growth in new cases.  
- **Temporal patterns:** Time-series plots revealed strong **weekly and monthly seasonality**, indicating periodic fluctuations in reported cases and deaths.  
- **Forecast performance:** The **Prophet model** accurately captured the underlying trend and seasonal effects, producing reliable forecasts with minimal prediction error across most provinces.  
- **Future projections:** The forecasting model projected a **gradual decline** in death rates toward mid-2021, reflecting the impact of containment and vaccination measures.  
- **Data reliability:** Some inconsistencies were observed in underreported regions, emphasizing the importance of improved data collection and standardization across countries.  


---

## 📌 Note

Please kindly note that this README file is a summarized version of the full implementation of this project. The complete implementation can be accessed via the [program script](COVID-19-Exploratory-Data-Analysis-and-Forecasting.ipynb) and analysis [visualization](COVID-19-Exploratory-Data-Analysis-(PowerBI-Visualization).pbix).

---
