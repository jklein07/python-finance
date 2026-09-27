# Python Finance

Python projects and coursework for quantitative finance: data analysis, statistical modeling, and backtesting.

## Projects

**Pairs Trading: Out-of-Sample Backtest** ([`projects/pairs_oos.ipynb`](projects/pairs_oos.ipynb))

This is the main pairs trading project. I screened 11,462 same-sector S&P 500 pairs for cointegration using only 2015-2019 data, froze the hedge ratios and spread parameters, and traded the top 5 from 2020 to 2024 with 5 bps costs. The portfolio returned 4.0% a year with a 0.70 net Sharpe and a -10.3% max drawdown, which is positive but not statistically distinguishable from zero over 5 years. Only 1 of the 5 pairs stayed cointegrated out of sample, and that one lost money.

**Pairs Trading Analysis, original version** ([`projects/pair_trading.ipynb`](projects/pair_trading.ipynb))

My first attempt, kept for reference. It tests NVDA/AMD, GLD/SLV, XOM/CVX, and KO/PEP, then backtests KO/PEP from 2015 to 2024. It has look-ahead bias: the hedge ratio, spread mean, and spread std are fit on the same window the strategy trades, so its Sharpe of 0.44 is in-sample. Retested on 2015-2019 alone, KO/PEP isn't cointegrated (p = 0.10). The exit logic also lets positions re-enter without crossing the entry threshold. Both problems are fixed in `pairs_oos.ipynb`.

**S&P 500 Pairs Screener** ([`projects/pairs_screener.ipynb`](projects/pairs_screener.ipynb))

Engle-Granger cointegration across ~117K S&P 500 pair combinations (2020-2023), plus a live z-score signal for BDX/MDLZ. At p < 0.001 about 117 pairs would pass by chance alone, which is part of why the out-of-sample version restricts to same-sector pairs.

**Black-Scholes Pricing & Greeks** ([`projects/black_scholes.ipynb`](projects/black_scholes.ipynb))

Black-Scholes prices and Greeks for European calls and puts, a put-call parity check, and a comparison against Monte Carlo simulation.

## Coursework

`pandas-course/`: Kaggle Pandas course exercises

`data-viz-course/`: Kaggle Data Visualization course exercises

## Stack

- Python 3.x
- pandas, numpy, matplotlib, seaborn
- statsmodels, yfinance

## About

Built over Summer 2026 while working toward quantitative research in finance. I'm a mathematics major (financial mathematics track) at The Ohio State University.
