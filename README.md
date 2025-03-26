# ML-Based Trading Strategy Using Technical Indicators

This project aims to utilize machine learning-based classification strategy to generate trading signals using technical indicators. It applies supervised learning techniques on stock price data to classify future returns into buy, sell, or hold signals.

---

## Strategy Overview

- **Asset:** US Equities
- **Objective:** Predict next-day return classification and backtest a signal-driven trading strategy.
- **Target Labels:**
  - `1` → Buy (Top 34% future returns)
  - `0` → Hold
  - `-1` → Sell (Bottom 34% future returns)

---

## Feature Engineering

Features were created from common technical indicators:

| Feature | Type | Description |
|--------|------|-------------|
| RSI | Momentum | Relative Strength Index |
| SMA | Trend | Simple Moving Average |
| Corr | Trend Strength | Correlation between Close & SMA |
| SAR | Reversal | Parabolic SAR |
| ADX | Trend Strength | Average Directional Index |
| OO | Price Action | Open - Previous Open |
| OC | Price Action | Open - Previous Close |
| Lagged Returns | Return Patterns | Last 4 days of future returns |

---

## Modeling & Evaluation

### Base Models Comparison
- Logistic Regression
- Linear Discriminant Analysis
- k-NN
- Decision Trees
- Random Forest
- Gradient Boosting
- AdaBoost
- Naive Bayes
- Support Vector Machine (SVM)

All models were evaluated using **Time Series Cross-Validation** and **accuracy** as the scoring metric.

### Sample Model
- **Model:** SVC (RBF kernel)
- **Hyperparameter Tuning:** GridSearchCV with time-series split

---

## Backtesting & Performance

The best model was used to simulate trading returns:

- 🔁 Signal: `Buy` (+1), `Hold` (0), `Sell` (-1)
- 📊 Strategy Return: 141.81%
- 📉 Max Drawdown: -38.81%
- 📈 Sharpe Ratio: 1.66

> These metrics are computed over the out-of-sample test set.

---

## 📊 Visualizations

- Close Price vs ML-Generated Signals
- Model Accuracy Comparison (Boxplot)
- Confusion Matrix
- Strategy Cumulative Returns vs Market Returns
- Strategy Drawdowns

---

