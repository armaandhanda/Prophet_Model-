# 1. Loading and Preparing Data
Datasets:
Air travel data (tsa).
Stock market data (S&P 500).
Disney wait time data.
Various custom datasets with ds (timestamps) and y (dependent variable values).
Data cleaning and renaming columns to meet Prophet's requirements (ds and y).
# 2. Modeling with Prophet
Basic Prophet Model:

Built and trained models using the default Prophet settings.
Predictions were made for future periods using make_future_dataframe.
Trend Adjustments:

Adjusted model flexibility by tuning the changepoint.prior.scale parameter:
Flexible trend: changepoint.prior.scale = 0.5.
Less flexible trend: changepoint.prior.scale = 0.001.
Seasonality Adjustments:

Explored default and custom seasonal components:
Yearly, weekly, monthly, and daily seasonality.
Enhanced seasonality fit by increasing Fourier orders for higher-frequency adjustments.
Added custom seasonality (e.g., monthly seasonality).
Holiday Effects:

Incorporated holidays and special events as additional features:
Created custom holidays (e.g., playoff games, Superbowl, COVID-19 period).
Added built-in country-specific holidays (e.g., US and UK).
Analyzed the impact of holidays on predictions.
Additional Regressors:

Used additional external features (e.g., NFL Sundays) as regressors to improve forecasting accuracy.
# 3. COVID-19 Adjustment
Task:
Modify the model to incorporate the COVID-19 period (March 2020 to March 2022) as a holiday.
Steps:
Defined the COVID-19 period as a custom holiday and added it to the model.
Re-fitted the model (m11_modified) with the new holiday.
Compared the performance of the original model and the modified model using RMSE.
# 4. Sub-Daily Data
Explored sub-daily data (Disney wait times) and adjusted the freq parameter for finer-grained predictions.
Generated forecasts for hourly intervals.
# 5. Stock Market Analysis
Forecasted stock market prices (S&P 500) using Prophet.
Created future forecasts for 300 days and plotted results.
# 6. Visualization
Plotted:
Forecast trends (overall predictions, components like trend and seasonality).
Holiday effects.
Comparison of observed and predicted values.
Evaluation Metrics
Root Mean Squared Error (RMSE):
Calculated RMSE for both the original and modified models to measure forecasting accuracy.
Compared predictions against the test set (tsa_test) for air travel data.
Key Learnings
Prophet's Versatility:

Supports custom holidays, seasonality adjustments, and additional regressors.
Easily handles sub-daily, weekly, and yearly seasonalities.
Impact of Trend and Seasonality Tuning:

Adjusting changepoint priors and Fourier orders allows the model to better capture changes in the data.
Holiday Effects:

Incorporating holidays significantly improves the model's predictive accuracy for periods with anomalous trends (e.g., COVID-19).
Custom Features:

External features (e.g., NFL Sundays) can enhance model performance.
