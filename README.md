# Machine-Learning-Return-predictions



This project applies linear regression to predict next-day stock returns from historical market features.

The goal is not to claim strong predictive power, but to build a clean and reproducible pipeline for:

- feature engineering on financial time series
- supervised learning for return prediction
- out-of-sample evaluation
- simple strategy backtesting


## Objective

We model the next-day return:

r_{t+1} = f(X_t)

where X_t includes lagged returns, rolling volatility, and moving-average-based signals.


## Features

- Lagged returns
- Rolling volatility
- Moving average ratios
- Volume change


## Model

- Linear Regression
- Train / test split with chronological order
- No random shuffling to avoid leakage


## Backtest Logic

- Go **long** when predicted return > 0
- Stay **flat** otherwise

Strategy return:

- position_t = 1 if prediction_t > 0 else 0
- strategy_return_t = position_{t-1} * actual_return_t

## Metrics

- Mean Squared Error
- R²
- Directional Accuracy
- Cumulative Return
- Sharpe Ratio
- Max Drawdown


## How to Run

- `ml_return_prediction.ipynb` → main notebook
