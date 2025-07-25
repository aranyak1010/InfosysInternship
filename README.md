# Electricity Demand and Price Forecasting

This project analyzes historical electricity data to forecast future demand and predict the Regional Reference Price (RRP). The analysis is performed in a Jupyter Notebook (`Electricity_Forecasting_And_Price_Prediction.ipynb`).

## Project Overview

The goal of this project is to understand the key drivers of electricity demand and price and to build machine learning models for forecasting. This can help energy providers optimize supply, manage costs, and ensure grid stability. Based on the analysis, several solutions are proposed to manage energy consumption and pricing effectively.

## What I've Done

This project demonstrates a complete data science workflow:

-   **Exploratory Data Analysis (EDA):** Investigated the relationships between variables like temperature, rainfall, holidays, and seasons with electricity demand and price. Visualizations were created to identify trends, seasonality, and correlations.
-   **Data Preprocessing & Feature Engineering:**
    -   Handled missing values using median imputation.
    -   Encoded categorical features (`school_day`, `holiday`) into numerical format.
    -   Created new time-based features like `day_of_week`, `month`, and `season`.
    -   Engineered lag and rolling window features for time-series modeling.
-   **Time Series Decomposition:** Decomposed the demand and RRP time series into trend, seasonal, and residual components to better understand their underlying patterns.
-   **Model Building and Evaluation:**
    -   **Prophet:** Used Facebook's Prophet model to forecast electricity demand and RRP, accounting for holidays and custom seasonalities.
    -   **Linear Regression:** Built a regression model to predict RRP based on demand and positive RRP values.
    -   **LightGBM:** Implemented a gradient boosting model (LightGBM) with time-series features for more accurate RRP prediction.
    -   Evaluated models using metrics like Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).
-   **Actionable Insights & Solutions:** Proposed solutions based on the analysis, such as implementing dynamic pricing, investing in energy storage, and promoting energy efficiency.

## Getting Started

To run this project locally, you'll need a Python environment with Jupyter Notebook and the required libraries installed.

### Prerequisites

-   Python 3.x
-   Jupyter Notebook or JupyterLab
-   Required libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`, `prophet`, `scikit-learn`, `lightgbm`.

### Installation & Running

1.  Clone the repository or download the source code.
2.  Navigate to the project directory:
    ```bash
    cd InfosysInternship
    ```
3.  Install the required libraries:
    ```bash
    pip install pandas numpy matplotlib seaborn statsmodels prophet scikit-learn lightgbm jupyter
    ```
4.  Start Jupyter Notebook:
    ```bash
    jupyter notebook
    ```
5.  Open the `Electricity_Forecasting_And_Price_Prediction.ipynb` file from the Jupyter interface and run the cells.
      expo start
      ```
