Forecasting Electric Power Sector Renewable Energy Consumption

📁 Project Overview:

  -This project forecasts Total Renewable Energy Consumption in the U.S. Electric Power sector using monthly data from 1973–2024. 
  The objective is to evaluate how well different time series models capture long-term growth, seasonality, and structural changes in renewable 
  energy usage, with a focus on forecasts for 2025–2028.

  -The analysis compares Holt-Winters (Exponential Smoothing), ARIMA, and SARIMA models to identify the most accurate and reliable forecasting approach.

🎯 Problem Statement:

  -Renewable energy consumption has increased significantly over time due to policy decisions, technological advances, and environmental factors. Accurate forecasting is          essential for:

    -Grid reliability and capacity planning

    -Resource allocation and optimization

    -Tracking progress toward decarbonization goals

🎯 Objectives:

  -Build a forecasting model with a target MAPE < 5%

  -Identify long-term trends and seasonal patterns in renewable energy consumption

  -Compare Holt-Winters, ARIMA, and SARIMA model performance

  -Generate forecasts for the 2025–2028 period and assess policy implications

📊 Dataset Description:

  -Source: Kaggle – U.S. Renewable Energy Consumption

  -Time Range: January 1973 – December 2024

  -Granularity: Monthly observations by energy sector
  
  -Dataset Size:

    -Total Rows: 3,065

    -Total Columns: 19

  -Key Features:

    -Sectors: Commercial, Industrial, Residential, Transportation, Electric Power

    -Energy Sources: Hydroelectric, Wind, Solar, Geothermal, Biomass, Biofuels, and others

    -Target Variable: Total Renewable Energy Consumption (trillion BTUs)

🔄 Methodology & Workflow:

  -Data Preprocessing:

    -Filtered data to Electric Power sector and Total Renewable Energy

    -Confirmed no missing values

    -Retained outliers to preserve effects of policy changes and extreme events

    -Conducted Augmented Dickey-Fuller (ADF) test for stationarity

    -Applied Box-Cox transformation (λ = −0.418) for ARIMA/SARIMA variance stabilization

  -Data Splitting:

    -Single Train/Test Split

      -Train: Jan 1973 – Dec 2012 (80%)

      -Test: Jan 2013 – Dec 2024 (20%)

    -4-Fold Time Series Cross-Validation:

      -Expanding window with rolling test periods

  -Models Implemented:

    -Holt-Winters: Captures level, trend, and seasonality

    -ARIMA: Models trend via differencing but does not capture seasonality
      
    -SARIMA: Extends ARIMA with seasonal components (12-month seasonality)

📊 Model Evaluation

  -Evaluation Metrics:

    -Mean Absolute Percentage Error (MAPE)

    -Root Mean Squared Error (RMSE)

  | Model        | MAPE (%)  | RMSE      |
  | ------------ | --------- | --------- |
  | Holt-Winters | 19.58%    | 54.78     |
  | ARIMA        | 26.32%    | 73.25     |
  | SARIMA       | **6.60%** | **18.92** |

📊 Key Findings:

    -SARIMA projects a strong upward trajectory with clear seasonal peaks, closely following historical growth. 
  
    -Holt-Winters forecasts a moderate rise with smoother seasonal cycles, suggesting a conservative expansion. 
  
    -ARIMA inaccurately shows an almost flatline forecast, failing to reflect historical growth or seasonality, which emphasizes its limitations for this task. 

🎯 Forecast Results (2025–2028):

    -SARIMA: Strong growth with pronounced seasonal patterns

    -Holt-Winters: Moderate growth with smoother seasonal cycles

    -ARIMA: Flat projections inconsistent with historical behavior

These results align with EIA expectations of continued growth in renewable electricity generation, particularly driven by solar expansion.


