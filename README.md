
# When Hedges Break: Stress-Testing Crypto Pairs Trading

Jurgen Mezinaj
Erdős Institute — Quantitative Methods in Finance
Quant-Finance bootcamp Fall 2026

This page has the notebooks, the data, and the figures. Open the notebooks in order.

## notebooks

- `01_data_and_crash_periods.ipynb` — the eight coins, the five crash windows, and the gap between coins
- `02_cointegration_diagnostics.ipynb` — which pairs pass the Engle–Granger test
- `03_three_strategies.ipynb` — static, dynamic, and dynamic with a GARCH filter
- `04_historical_crashes.ipynb` — each crash, plus the XMR and ZEC charts
- `05_monte_carlo_stress_tests.ipynb` — 500 simulated paths in each stress scenario
- `06_robustness_and_conclusions.ipynb` — costs, thresholds, and the bootstrap intervals

## data

Coin Metrics Community Data, daily prices and reported spot volume, 1 July 2017 through 23 May 2026. Trading runs from 1 January 2020 through 23 May 2026. Licence CC BY-NC 4.0.

- `prices.csv`
- `volumes.csv`

The coins are BNB, LINK, LTC, TRX, BCH, XLM, XMR, and ZEC. The pair direction uses volume through 31 December 2019, most liquid first: LTC, BCH, TRX, XMR, BNB, ZEC, XLM, LINK.

## figures

- `01_crash_windows.png` — the five crash windows
- `01_garch_filter.png` — the GARCH volatility forecast
- `02_rolling_beta.png` — the rolling hedge ratio
- `02_rolling_share.png` — the share of windows that pass the cointegration test
- `03_equity.png` — the three strategy results
- `03_regimes.png` — crash days and the other days
- `04_single_coin_shocks.png` — hypothetical XMR and ZEC spreads
- `04_spread_deviation.png` — how far the spreads moved in each crash
- `05_position_level.png` — the simulated positions
- `06_gate_filter.png` — the cointegration screen and the GARCH filter

## Results in the notebooks

| Strategy | Net return | Sharpe | 95% interval | Max drawdown | Trades |
|---|---|---|---|---|---|
| Static | −4.4% | −0.07 | [−0.79, 0.55] | 13.9% | 50 |
| Dynamic | −0.7% | 0.00 | [−0.87, 0.79] | 12.7% | 76 |
| Dynamic + GARCH | +6.8% | 0.40 | [−0.32, 1.09] | 4.4% | 58 |

All three intervals contain zero. On the 155 crash days, average correlation goes from 0.54 to 0.84. The unit gap rises by a factor of 1.07. The lagged fitted gap rises by a factor of 1.32.
