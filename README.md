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
- Time independent autocovariance

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

# Forecasting the Time Series

## ARIMA Model (Auto-Regressive Integrated Moving Averages)

- **Auto-Regression (AR)**: A time series model that uses observations from previous time steps as input to a regression equation to predict the value at the next time step.
- **Moving Average (MA)**: A moving-average model is conceptually a linear regression of the current value of the series against current and previous (observed) white noise error terms or random shocks.

So ARIMA is a model that uses
- The dependent relationship between an observation and some number of lagged observations.
- Differencing of raw observations (e.g. subtracting an observation from an observation at the previous time step) in order to make the time series stationary.
- The dependency between an observation and a residual error from a moving average model applied to lagged observations.

The ARIMA forecasting for a stationary time series is nothing but a linear (like a linear regression) equation. The predictors depend on the parameters (p,d,q) of the ARIMA model:

1. Number of AR (Auto-Regressive) terms (p)
2. Number of MA (Moving Average) terms (q)
3. Number of Differences (d)

### Determining value of P & Q

Following 2 plots are used to determine these numbers:

1. **Autocorrelation Function (ACF)**: It is a measure of the correlation between the the time series with a lagged version of itself.
2. **Partial Autocorrelation Function (PACF)**:  This measures the correlation between the time series with a lagged version of itself but after eliminating the variations already explained by the intervening comparisons.

In the above two plots,

- **P**: Lag value where PACF chart crosses upper confidence intervals.
- **Q**: Lag value where ACF chart crosses upper confidence intervals.
