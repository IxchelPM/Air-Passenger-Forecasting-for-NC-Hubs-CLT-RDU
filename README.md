# Forecasting North Carolina Airline Passenger Traffic (Jan 2020 – Jun 2020)

This project forecasts total airline passengers traveling through **Charlotte** and **Raleigh-Durham**, North Carolina’s top two air hubs, using time series methods in **R**. The analysis spans **January 2000 to December 2019**, with forecasts extending to **June 2020**.

---

## Overview

- **Objective**: Predict monthly airline passenger volume using historical data.
- **Airports Analyzed**: Charlotte (CLT) & Raleigh-Durham (RDU)
- **Data Range**: Jan 2000 – Dec 2019
- **Forecast Range**: Jan 2020 – Jun 2020
- **Language**: R
- **Techniques**: ETS, ARIMA, spatial mapping, Shiny dashboard

---

## Data Source & Processing

- **Source**: U.S. Monthly Air Passenger Data (2000–2019)
- **Cleaning**:
  - Filtered for domestic flights involving NC
  - Aggregated monthly passenger counts
  - Top 2 cities selected based on volume
- **Geolocation**: Used Google Maps API to get lat/lon for destinations

---

## Methods

### Benchmark Models
- Naive
- Seasonal Naive
- Drift
- Average

### Advanced Models
- **ETS (A, A, A)**: Additive trend & seasonality
- **ARIMA**:
  - Used Box-Cox transformation, differencing
  - Final model: `ARIMA(1,0,1)(2,1,1)[12]` with drift
  - Evaluated with:
    - KPSS test (stationarity)
    - Ljung-Box test (white noise residuals)
    - RMSE comparison
    - Cross-validation

---

## Final Model

- **Selected**: ARIMA(1,0,1)(2,1,1)[12] with drift
- **Why**:
  - Best RMSE
  - White noise residuals
  - Captured trend and seasonality

---

## Spatial & Visual Analysis
- **Visuals**:
  - Flight volume maps (static + interactive)
  - STL decomposition plots
  - Bar charts, ACF/PACF, forecast plots

---

## Requirements

- R version 4.0.0 or higher
- Required packages: dplyr, fpp2, ggplot2, urca, gridExtra, ggmap,leaflet, shiny