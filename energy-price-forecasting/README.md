# Energy Price Forecasting

**Course:** DATA 607, University of Calgary (April 2024) · **Team:** Riki Enquist, Crystal Wai, Niza Ngwira
**Notebook:** [Energy_Price_Forecasting.ipynb](Energy_Price_Forecasting.ipynb)

## Question
Can electricity generation, demand and weather forecast the hourly price of electricity in Spain?

## Data
- About 35,000 hourly records from 2015 to 2018: generation by source (fossil, hydro, nuclear, wind and others), load and actual price.
- Hourly weather for five Spanish cities: temperature, pressure, humidity, wind, rain and cloud cover.

## Approach
1. **Cleaning:** dropped empty columns, linearly interpolated gaps, and removed outliers more than 3 standard deviations from the mean.
2. **Transformation:** min-max scaling, plus a Yeo-Johnson transform on highly skewed features.
3. **Joining:** pivoted the weather data by city and joined it to the energy data on timestamp.
4. **Stationarity:** checked with ACF plots and an augmented Dickey-Fuller test. ADF statistic −7.23, p < 0.001, so the price series is stationary.
5. **Feature selection:** Lasso with 5-fold cross-validation. Test R² improved from 0.12 with a fixed alpha to 0.63 with the tuned alpha.
6. **Models:** trained on the Lasso-selected features and compared on a held-out test set.

## Results

| Model | Test R² |
|---|---|
| Lasso (cross-validated) | 0.63 |
| Decision tree | 0.63 |
| Gradient boosting | 0.75 |
| **LSTM** | **0.89** |

The LSTM performed best because it learns from the order of past observations.

## Limitations and next steps
- The train/test split was random rather than chronological. A time-based split, such as training on 2015–2017 and testing on 2018, would give a more realistic estimate of forecasting accuracy.
- Energy prices also depend on fuel costs and the wider economy, which this data doesn't include.
