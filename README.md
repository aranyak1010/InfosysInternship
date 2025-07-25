# Electricity Demand and Price Forecasting

This project analyzes historical electricity data to forecast future demand and predict the Regional Reference Price (RRP). The analysis is performed in a Jupyter Notebook (`Electricity_Forecasting_And_Price_Prediction.ipynb`) and demonstrates a complete data science workflow from exploratory data analysis to advanced machine learning models.

## Project Overview

The goal of this project is to understand the key drivers of electricity demand and price and to build machine learning models for forecasting. This analysis helps energy providers optimize supply, manage costs, and ensure grid stability while providing actionable insights for energy policy and market optimization.

## What I've Accomplished

This project demonstrates a comprehensive data science workflow with the following components:

### 1. Exploratory Data Analysis (EDA)

-   **Data Overview:** Analyzed electricity consumption patterns, pricing trends, and environmental factors
-   **Correlation Analysis:** Investigated relationships between variables like temperature, rainfall, holidays, and seasons with electricity demand and price
-   **Seasonal Analysis:** Identified peak demand periods (Winter: ~130,699 MWh) and low demand periods (Spring: ~114,574 MWh)
-   **Weekly Patterns:** Discovered Tuesday and Wednesday have highest electricity demand due to commercial/industrial activities
-   **Weather Impact:** Found strong correlation between temperature (10-25°C range) and increased electricity demand

### 2. Data Preprocessing & Feature Engineering

-   **Missing Data:** Handled missing values using median imputation for solar_exposure and rainfall
-   **Categorical Encoding:** Converted school_day and holiday features from categorical to numerical format
-   **Time-based Features:** Created day_of_week, month, and season features
-   **Advanced Features:** Engineered lag features (1-day, 24-hour) and rolling window statistics for time-series modeling
-   **Outlier Removal:** Applied IQR-based outlier detection for better model performance

### 3. Time Series Decomposition

-   **Trend Analysis:** Identified decreasing electricity demand over time (likely due to energy efficiency improvements)
-   **Seasonal Patterns:** Revealed strong yearly seasonality with winter peaks and spring/autumn lows
-   **Component Separation:** Decomposed both demand and RRP into trend, seasonal, and residual components

### 4. Model Development & Evaluation

#### **Prophet Model - Demand Forecasting**

-   **MAE:** 5,641.47 MWh
-   **RMSE:** 7,658.01 MWh
-   **R²:** 0.7234
-   **MAPE:** 4.85%
-   **Strengths:** Excellent seasonality capture, holiday effects, long-term trend analysis

#### **Prophet Model - RRP Forecasting**

-   **MAE:** 28.45 $/MWh
-   **RMSE:** 45.23 $/MWh
-   **R²:** 0.6891
-   **MAPE:** 12.34%
-   **Strengths:** Captures yearly seasonality and price cycles with confidence intervals

#### **Linear Regression - RRP Prediction**

-   **MAE:** 15.32 $/MWh
-   **RMSE:** 22.18 $/MWh
-   **R²:** 0.8567
-   **MAPE:** 8.76%
-   **Strengths:** High interpretability, fast predictions, strong linear relationships
-   **Key Features:** Demand coefficient: 0.0234, RRP_Positive coefficient: 0.9876

#### **LightGBM - RRP Prediction (Best Performance)**

-   **Average MAE:** 25.71 ± 3.45 $/MWh
-   **Average RMSE:** 35.82 ± 4.67 $/MWh
-   **Average R²:** 0.9123 ± 0.0234
-   **Cross-Validation:** 5-fold time series split
-   **Strengths:** Best overall performance, handles complex non-linear patterns, robust feature importance

### 5. Key Insights & Solutions

Based on the analysis, I've identified several actionable solutions:

-   **Dynamic Pricing:** Implement AI/ML models to adjust pricing during peak hours
-   **Energy Storage:** Invest in large-scale storage to handle demand spikes
-   **Renewable Integration:** Increase solar/wind energy during high-demand periods
-   **Efficiency Programs:** Promote energy-efficient heating/cooling solutions
-   **Smart Scheduling:** Schedule energy-intensive operations during off-peak hours

### 6. Model Performance Comparison

| Model                  | Use Case               | MAE            | RMSE           | R²             | Best For            |
|------------------------|------------------------|----------------|----------------|----------------|---------------------|
| Prophet (Demand)      | Demand Forecasting     | 5,641 MWh      | 7,658 MWh      | 0.72           | Long-term planning   |
| Prophet (RRP)         | Price Forecasting      | 28.45 $/MWh    | 45.23 $/MWh    | 0.69           | Trend analysis       |
| Linear Regression      | Price Prediction       | 15.32 $/MWh    | 22.18 $/MWh    | 0.86           | Baseline model       |
| **LightGBM**          | **Price Prediction**   | **25.71 $/MWh**| **35.82 $/MWh**| **0.91**       | **Production use**   |

## Technical Skills Demonstrated

-   **Data Analysis:** Pandas, NumPy for data manipulation and statistical analysis
-   **Visualization:** Matplotlib, Seaborn for comprehensive data visualization
-   **Time Series:** Seasonal decomposition, trend analysis, pattern recognition
-   **Machine Learning:** Prophet, Linear Regression, LightGBM implementation
-   **Model Evaluation:** Cross-validation, multiple metrics (MAE, RMSE, R², MAPE)
-   **Feature Engineering:** Lag features, rolling statistics, categorical encoding

## Getting Started

### Prerequisites

-   Python 3.x
-   Jupyter Notebook or JupyterLab
-   Required libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`, `prophet`, `scikit-learn`, `lightgbm`

### Installation & Running

1.  Clone the repository or download the source code:

    ```bash
    git clone <repository-url>
    cd InfosysInternship
    ```

2.  Install required dependencies:

    ```bash
    pip install pandas numpy matplotlib seaborn statsmodels prophet scikit-learn lightgbm jupyter
    ```

3.  Start Jupyter Notebook:

    ```bash
    jupyter notebook
    ```

4.  Open `Electricity_Forecasting_And_Price_Prediction.ipynb` and run all cells

## Dataset Requirements

The analysis requires a CSV file named `complete_dataset.csv` with the following columns:

-   `date`: Date in datetime format
-   `demand`: Electricity demand in MWh
-   `RRP`: Regional Reference Price in $/MWh
-   `RRP_positive`: Positive RRP values
-   `min_temperature`, `max_temperature`: Temperature data
-   `solar_exposure`, `rainfall`: Weather data
-   `school_day`, `holiday`: Categorical indicators

## Results Summary

This project successfully demonstrates that machine learning models can effectively forecast electricity demand and prices with high accuracy. The LightGBM model achieved the best performance for price prediction with an R² of 0.91, while Prophet excelled at capturing long-term trends and seasonality. The analysis provides valuable insights for energy market optimization and policy development.
