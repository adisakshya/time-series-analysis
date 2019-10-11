# Time Series Analysis & Forecast

This project is an implementation of a powerful model known as ARIMA, that is a widely used statistical method for time series forecasting that can help understand and predict the behaviour of dynamic systems from experimental or observational data, mainly used for modelling and forecasting of economic, financial, and biological systems.

# What is a Time Series ?

Time Series is a collection of data points collected at **constant time intervals**. These data points are then analyzed to deterine the long tern trend to forecast the future.

- Time Series is **time dependent**.
- Most Time Series have some form of **seasonality trends**, i.e., variations that are specific to particular time period or frame. Example, sales of mango are higher in summer seasons.

# Checking stationary of a Time Series ?

A Time Series is said to be stationary when its **statistical properties** remain constant over time, we can say that if a time series has a particular behaviour over time, there is a very high probability that it will follow the same in the future.

For practical purposes we can assume the series to be stationary if it has constant statistical properties over time, ie. the following:

- Constant mean
- Constant variance
- An autocovariance that does not depend on time.

we can check stationarity using the following:

- **Rolling Statistics**: We plot the moving average or moving variance and see if it varies with time.
- **Dickey-Fuller Test**: This is one of the statistical tests for checking stationarity. Here the null hypothesis is that the time-series is non-stationary. The test results comprise of a Test Statistic and some Critical Values for difference confidence levels. If the ‘Test Statistic’ is less than the ‘Critical Value’, we can reject the null hypothesis and say that the series is stationary.

# Making a time series stationary

Time series are non-stationary because of following 2 reasons:

- **Trend**: Mean vary over time.
- **Seasonality**: Variations are seen at specific time-frames.

1. The principle is to model or estimate the trend and seasonality in the time series and remove those from the series to get a stationary series.

2. Then implement statistical forecasting techniques on this series.

3. Convert the forecasted values into the original scale by applying trend and seasonality constraints back.

## Estimating Trend

- **Aggregation**: Taking average for specific time period.
- **Smoothing**: Taking rolling averages.
- **Polynomial Fitting**: Fitting regression model.

## Eliminating Trend & Seasonality

- **Differencing**: Take the difference of the observation at a particular instant with that at the previous instant.
- **Decomposition**: Both trend and seasonality are modeled separately and the remaining part of the series is returned.
