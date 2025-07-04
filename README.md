# Energia Group Trading Strategy Optimization

## Project Overview

In this project, I analysed forecast data, including wind and demand predictions, to understand market behaviour and optimise energy procurement strategies. My aim was to identify pricing trends and derive actionable insights to enhance cost efficiency in energy trading.

## Author

Bhagyaprasad Vastrad

## Introduction

The energy market is influenced by demand, generation, and external factors such as weather conditions. Accurate forecasting plays a crucial role in predicting demand and generation trends, enabling better decision-making for energy procurement. In this analysis, I focused on market behaviours using forecast data to derive strategies that minimise costs and risks for energy trading firms.

## Objectives

- To analyse forecast-based data and identify meaningful patterns.
- To study market characteristics such as price volatility and demand fluctuations.
- To establish baseline metrics including Net Demand and Forecast Error for market analysis.

## Dataset Description

### Input Data

- **Forecasts:** Predictions of wind generation and energy demand.
- **Actuals:** Real-time data on generation and consumption.
- **Market Prices:** Data for Day-Ahead Market (DAM) and Balancing Market (BM).

### Derived Features

- **Net Demand Calculation:** Difference between predicted demand and forecasted generation.
- **Forecast Error Metrics:** Quantification of errors in wind and demand forecasts.

## Methodology

### Data Cleaning and Pre-processing

- I handled missing values by forward-filling.
- I standardised the data for consistent analysis.

### Exploratory Data Analysis

- I created time-series plots using Power BI to detect trends in DAM pricing.

![image](https://github.com/user-attachments/assets/46e998e1-761a-4b4b-8c15-78e31eacd033)


### Feature Engineering

- I developed custom metrics to evaluate forecast reliability.

### Tools Used

- **Python:** For data pre-processing, analysis, and feature generation.
- **Power BI:** For interactive visualisations and market trend insights.

## Key Analysis and Insights

### Market Prices Over Time

- BM prices were highly volatile with both very high and very low spikes.
- DAM and IDA prices were relatively smoother and more predictable.
- Buying all power from BM was risky due to unpredictability, whereas DAM and IDAs offered safer, stable prices.

### DAM Price vs DAM Net Demand

- The wind forecast error distribution was roughly centred around zero, indicating forecasts were unbiased on average.
- Most errors were within -200 MW to +200 MW, but occasionally forecast errors reached 400–600 MW, causing market shocks.

![image](https://github.com/user-attachments/assets/0c95b191-43c5-4cd6-9aa4-5a76591203e1)


### Meaning for Strategy

- Forecast errors can significantly impact prices, especially when wind is under-predicted, leading to BM price spikes.

## Basic Strategy Simulation

| Strategy            | Total Cost (€) | Insights                                         |
|---------------------|----------------|--------------------------------------------------|
| Buy All in DAM      | 41,210,532     | Stable but more expensive.                      |
| Buy All in BM       | 37,953,163     | Cheaper overall, but risky due to price spikes. |
| Buy 50% DAM + 50% BM| 39,581,848     | Balanced risk and cost, better than DAM only.   |

### Key Observations

1. Buying only in BM was the cheapest historically (April–September 2019), but risky due to price volatility.
2. BM prices were unpredictable with random spikes over €400.
3. The 50/50 split strategy performed better than all-in DAM, capturing low BM prices while reducing risk.

### Meaning for Energia's Strategy

- Blindly buying 100% from DAM was not optimal.
- Flexibility in purchasing, such as splitting between DAM and BM, could save millions while managing risk.

### Power Bi Dashboard

![image](https://github.com/user-attachments/assets/9db3b76d-fabb-47d7-8867-50cb08aa0529)


## Conclusion

Based on my analysis of historical data between April 1st and September 30th, 2019:

- The cheapest strategy would have been buying all electricity in the Balancing Market (BM), costing approximately €37.95 million, compared to €41.21 million if buying fully in DAM.
- A 50/50 split would have cost €39.58 million, still cheaper than DAM-only but more expensive than full BM.
- Although BM was cheaper overall, its high volatility introduced significant financial risk.
- DAM prices were slightly more expensive but offered price stability, reducing risk exposure.
- Therefore, while buying in BM was optimal based on cost alone, a risk-averse supplier might prefer splitting between DAM and BM for more predictable outcomes.

