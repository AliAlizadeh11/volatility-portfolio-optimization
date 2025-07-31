# Volatility-Based Portfolio Optimization

This project explores portfolio management using **volatility estimation** and **time series analysis**. The main goal is to improve portfolio performance by optimizing asset allocation weights and comparing various volatility forecasting methods.


## 📌 Project Overview

We build a crypto portfolio consisting of **BTC-USD**, **ETH-USD**, **BNB-USD**, and **XRP-USD** using daily historical data from **2023-08-01** to **2024-12-01**. The workflow includes:

1. **Data Collection & Preprocessing**
2. **Volatility Estimation**  
3. **Portfolio Optimization using Black-Litterman model**
4. **Buy and Hold Strategy Backtesting**
5. **Performance Evaluation & Visualization**


## 📊 Step-by-Step Breakdown

### 1. Data Collection

- Historical daily data for the 4 cryptocurrencies.
- Data split:
  - **Training Set**: 2023-08-01 to 2024-08-01
  - **Test Set**: 2024-08-01 to 2024-12-01


### 2. Volatility Estimation

For each asset, and for 7-day and 30-day rolling windows:

#### 🔹 Statistical Models:
- GARCH
- EGARCH
- FIGARCH

#### 🔹 Volatility Proxies:
- Historical Volatility
- Parkinson Estimator
- Garman-Klass Estimator
- Yang-Zhang Estimator

✅ A total of **14 volatility series per asset**.


### 3. Portfolio Optimization (Black-Litterman)

- Volatility estimates are averaged per method (per asset).
- Each average volatility vector is used in a **Black-Litterman optimization**.
- Objective: **maximize Sharpe Ratio** while enforcing **diversification**.

🔸 Output: 7 different sets of optimized weights (one per volatility method group).


### 4. Backtesting Strategy

- Simple **Buy and Hold** strategy.
- Initial capital: **$1000**
- Transaction cost: **2%**
- Backtested separately on **training** and **test** datasets.
- Performance Metrics:
  - Sharpe Ratio
  - Net Profit
  - Max Drawdown


### 5. Results Analysis

- Compare strategies across volatility estimation methods.
- Identify the best-performing approach.
- Visualize:
  - Equity Curve
  - Portfolio Allocation Over Time
  - Volatility Dynamics
  - Confidence Intervals
  - Cumulative Returns


## 📦 Dependencies

- `pandas`
- `numpy`
- `matplotlib`, `seaborn`
- `arch` (for GARCH models)
- `yfinance` or other data providers
- `cvxpy`, `scipy` (for optimization)
- `statsmodels`
- `sklearn` (for evaluation)
