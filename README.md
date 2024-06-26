# MetaTrader5 Intraday Renko MACD Trading Strategy

This Python script leverages the MetaTrader5 (MT5) API to implement an automated trading strategy based on Renko bricks and the Moving Average Convergence Divergence (MACD) indicator for selected currency pairs. It is designed for intraday trading with dynamic adjustments to take positions based on real-time market data.

## Features

- **Automated Trading**: Automatically executes buy and sell orders based on Renko and MACD signals.
- **Dynamic Strategy**: Utilizes real-time ATR for brick size calculation and MACD for trading signals.

## Requirements

- Python 3.12
- **MetaTrader 5**: Ensure that MetaTrader5 is installed and accessible on your machine.

# Strategy Description
- Renko charts are utilized in this strategy to filter minor price fluctuations and emphasize significant price movements. Each Renko block's size is dynamically determined based on the Average True Range (ATR), adapting to changing market conditions. A new Renko block is formed only when price movements surpass the threshold set by the ATR.
- The Moving Average Convergence Divergence (MACD) serves as a trend-following momentum indicator. It is derived by subtracting the 26-period Exponential Moving Average (EMA) from the 12-period EMA, resulting in the MACD line. An additional nine-day EMA of the MACD, known as the "signal line," is plotted over the MACD line to act as a trigger for buy and sell decisions.

## Signals
- Buy Signal: A buy signal is activated when at least two consecutive Renko blocks signal an uptrend, and this is accompanied by the MACD line crossing above the signal line. Confirmation is sought through the increasing slope of the MACD line relative to the signal line, indicating a buildup of upward momentum.
- Sell Signal: A sell signal is generated when at least two consecutive Renko blocks display a downtrend, coupled with the MACD line crossing below the signal line. The validity of this signal is reinforced if the slope of the MACD line decreases relative to the signal line, suggesting a downward momentum.

## Position Management
This strategy includes an exit mechanism that triggers when an opposite signal occurs or when Renko blocks revert to a neutral position, effectively minimizing potential losses due to abrupt market changes.

# How It Works
- Data Downloading: The script fetches historical intraday data for selected stocks using the yfinance library.
- Renko Chart Calculation: Calculates Renko charts for each stock to determine significant price movements.
- MACD Calculation: Computes the MACD.
- Signal Processing: Analyzes the data from Renko charts and the MACD to produce buy and sell signals.
- Performance Evaluation: Evaluates the strategy's performance by calculating CAGR, Sharpe ratio, and maximum drawdown.

# Author

Muykheng Long - https://github.com/muykhenglong/


