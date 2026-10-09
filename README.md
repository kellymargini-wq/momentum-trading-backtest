# Momentum Trading Strategy Backtest

## Overview

This project tests whether a cross-sectional momentum strategy applied to US sector ETFs could outperform the S&P 500.

The analysis was completed in Python using historical adjusted price data downloaded through Yahoo Finance. The strategy is compared with SPY, an ETF tracking the S&P 500.

## Strategy

At the end of each month, the strategy:

1. Calculates each sector ETF's return over the previous 12 months.
2. Ranks the eleven sectors from strongest to weakest.
3. Selects the three sectors with the highest momentum.
4. Allocates one-third of the portfolio to each selected sector.
5. Holds the portfolio for the following month.
6. Repeats the process monthly.

Portfolio weights are shifted forward by one month to prevent look-ahead bias. Transaction costs of 0.10% are applied to portfolio turnover.

## Results

| Metric | Momentum Strategy | S&P 500 |
|---|---:|---:|
| Annualised return | 17.74% | 15.72% |
| Annualised volatility | 15.42% | 16.42% |
| Sharpe ratio | 1.14 | 0.98 |
| Maximum drawdown | -18.15% | -23.93% |

During the period tested, the momentum strategy generated a higher annualised return, lower volatility and a smaller maximum drawdown than the S&P 500. Historical results do not guarantee future performance.

## Tools

- Python
- pandas
- NumPy
- yfinance
- Matplotlib
- Jupyter Notebook

## Limitations

- The backtest covers a relatively short historical period.
- The strategy uses fixed parameters: a 12-month lookback and three selected sectors.
- Transaction costs are represented by a constant estimate.
- Taxes, bid-ask spreads and market slippage are not modelled separately.
- The analysis is limited to US sector ETFs.
- Results may be sensitive to the chosen period and strategy parameters.

## Running the project

Install the required packages:

```bash
pip install -r requirements.txt 