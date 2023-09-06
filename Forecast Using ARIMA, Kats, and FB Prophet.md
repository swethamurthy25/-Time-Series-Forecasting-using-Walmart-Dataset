# Forecast Using ARIMA, Kats, and FB Prophet

```python
# Import necessary libraries and load your dataset
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.statespace.sarimax import SARIMAX
from fbprophet import Prophet
from kats.consts import TimeSeriesData
from kats.tsfeatures.tsfeatures import TsFeatures

# Load your Walmart weekly revenue dataset (assuming it's in a variable called 'df')
# Ensure your dataset has a 'Date' column and 'WeeklyRevenue' column

# Perform time-series analysis with ARIMA
def arima_forecast(df):
    model = SARIMAX(df['WeeklyRevenue'], order=(p, d, q), seasonal_order=(P, D, Q, S))
    results = model.fit()
    forecast = results.predict(start=len(df), end=len(df) + n_forecast - 1, dynamic=False)
    return forecast

# Perform time-series analysis with FB Prophet
def prophet_forecast(df):
    model = Prophet()
    model.fit(df[['Date', 'WeeklyRevenue']].rename(columns={'Date': 'ds', 'WeeklyRevenue': 'y'}))
    future = model.make_future_dataframe(periods=n_forecast)
    forecast = model.predict(future)
    return forecast['yhat'][-n_forecast:]

# Perform time-series analysis with Kats
def kats_forecast(df):
    ts_data = TimeSeriesData(df[['Date', 'WeeklyRevenue']].rename(columns={'Date': 'time', 'WeeklyRevenue': 'value'}))
    tsfeatures = TsFeatures()
    tsfeatures.load(ts_data)
    model = tsfeatures.compute()
    forecast = model[0]['value'].values[-n_forecast:]
    return forecast

# Assuming you have chosen the values of p, d, q, P, D, Q, S, and n_forecast

# Generate forecasts for ARIMA, Prophet, and Kats
arima_results = arima_forecast(df)
prophet_results = prophet_forecast(df)
kats_results = kats_forecast(df)
```

## Visualization and Calculation of MAPE

```python
# Plot actual vs. forecasted values for ARIMA
plt.figure(figsize=(12, 6))
plt.plot(df['Date'], df['WeeklyRevenue'], label='Actual', color='blue')
plt.plot(df['Date'].iloc[-1:], arima_results, label='ARIMA Forecast', color='green')
plt.xlabel('Date')
plt.ylabel('Weekly Revenue')
plt.title('ARIMA Forecast vs. Actual')
plt.legend()
plt.show()

# Plot actual vs. forecasted values for Prophet
plt.figure(figsize=(12, 6))
plt.plot(df['Date'], df['WeeklyRevenue'], label='Actual', color='blue')
plt.plot(df['Date'].iloc[-1:], prophet_results, label='Prophet Forecast', color='orange')
plt.xlabel('Date')
plt.ylabel('Weekly Revenue')
plt.title('Prophet Forecast vs. Actual')
plt.legend()
plt.show()

# Plot actual vs. forecasted values for Kats
plt.figure(figsize=(12, 6))
plt.plot(df['Date'], df['WeeklyRevenue'], label='Actual', color='blue')
plt.plot(df['Date'].iloc[-1:], kats_results, label='Kats Forecast', color='red')
plt.xlabel('Date')
plt.ylabel('Weekly Revenue')
plt.title('Kats Forecast vs. Actual')
plt.legend()
plt.show()

# Calculate MAPE for each model
def calculate_mape(actual, forecast):
    return np.mean(np.abs((actual - forecast) / actual)) * 100

mape_arima = calculate_mape(df['WeeklyRevenue'].iloc[-n_forecast:], arima_results)
mape_prophet = calculate_mape(df['WeeklyRevenue'].iloc[-n_forecast:], prophet_results)
mape_kats = calculate_mape(df['WeeklyRevenue'].iloc[-n_forecast:], kats_results)

print(f'MAPE for ARIMA: {mape_arima:.2f}%')
print(f'MAPE for Prophet: {mape_prophet:.2f}%')
print(f'MAPE for Kats: {mape_kats:.2f}%')
```

## Discussion and Conclusion

In the project documentation, provide a thorough discussion and conclusion based on the MAPE results, visualizations, and the importance of achieving a MAPE of 9% for 
Walmart's sales forecasting. Explain any challenges faced during the implementation of forecasting algorithms and how they were addressed.

By following these steps, you will implement the analysis, visualization, and discussion of ARIMA, Kats, and FB Prophet forecasts in your project, showcasing the achievement of a MAPE of 9% and its significance for Walmart's business operations.
