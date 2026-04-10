# XAU/USD Systematic Backtest — PA Engulf + MACD + EMA50

Systematic trading strategy backtest on XAU/USD (Gold) using Price Action, MACD, and EMA trend filter.

---

## Live Dashboard

[View Backtest Dashboard](https://supanutdear.github.io/xauusd_backtest_pa_engulf_macd_ema50/)

---

## Strategy Overview

| Component | Detail |
|-----------|--------|
| Instrument | XAU/USD (Gold Spot) |
| Timeframe | 15-minute |
| Data Period | 2021 – 2025 |
| Signal | Price Action Engulf + Wick Grab |
| Filter 1 | MACD (10/30/9) — momentum confirmation |
| Filter 2 | EMA50 — trend direction filter |

### Entry Logic

**BUY** — All 3 conditions must be true simultaneously:
- Bullish engulfing candle — wick grabs the low and close engulfs the high of the previous 2 bars
- MACD Line > Signal Line
- Price closing above EMA50

**SELL** — Mirror conditions for short entries.

### Risk Management

| Parameter | Value |
|-----------|-------|
| Initial Capital | $10,000 |
| Risk per Trade | 3% (compound) |
| RR Ratio | 1 : 1 |
| Max SL Filter | 0.4% of price |
| Position Sizing | Fixed fractional |

---

## Backtest Results

| Metric | Value |
|--------|-------|
| Final Capital | $34,621 |
| Total Return | +246.2% |
| Annual Return | ~51.5%/year |
| Win Rate | 54.0% (346W / 295L) |
| Profit Factor | 1.13 |
| Max Drawdown | 38.53% |
| Max Win Streak | 9 trades |
| Max Loss Streak | 7 trades |

### Annual Breakdown

| Year | Trades | Win Rate | Return |
|------|--------|----------|--------|
| 2021 | 154 | 53.9% | +33.7% |
| 2022 | 130 | 54.6% | +35.2% |
| 2023 | 119 | 57.1% | +57.9% |
| 2024 | 98 | 49.0% | -9.9% |
| 2025 | 140 | 54.3% | +34.6% |

---

## Risk-Adjusted Metrics

| Metric | Value | Note |
|--------|-------|------|
| Sharpe Ratio | 0.90 | Trade-based annualized (~129 trades/year) |
| Sortino Ratio | 0.90 | Downside deviation only |
| Calmar Ratio | 1.28 | 51.5% annual return / 38.53% max DD |

> **Methodology note:** Sharpe and Sortino are annualized using actual trade frequency (~129 trades/year) rather than the conventional daily assumption (√252). This more accurately reflects the strategy's true risk-adjusted performance given that not every trading day has an active position.

---

## Files

| File | Description |
|------|-------------|
| `xauusd_backtest_pa_engulf_macd_ema50.ipynb` | Full backtest code with outputs |
| `tradelog.csv` | Complete trade log (entry, exit, PnL, capital) |

---

## Disclaimer

> This project is for educational and portfolio purposes only.
> All results are based on historical backtesting and do not guarantee future performance.
> This is not financial advice.
