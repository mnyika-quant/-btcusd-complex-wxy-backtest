# BTCUSD Complex WXY Backtest
### Double Zigzag Corrective Structure | Systematic Short Framework

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mnyika-quant/-btcusd-complex-wxy-backtest/blob/main/BTCUSD_Complex_WXY_Backtest.ipynb)

**By Munyaradzi Nyika | Wave and Code**

📊 Research: [waveandcode.substack.com](https://waveandcode.substack.com)
💻 Code: [github.com/mnyika-quant](https://github.com/mnyika-quant)
📡 Live Signals: [t.me/waveandcodesignals](https://t.me/waveandcodesignals)

---

## Overview

BTCUSD has completed a complex WXY double zigzag corrective
structure on the 4 hour chart. This repository documents the
systematic short framework built on that structure — combining
Elliott Wave market structure identification with RSI momentum
confirmation, ATR based position sizing, automated email alerts,
and a defined re-entry framework.

The framework is **armed and awaiting RSI confirmation** as of
17 March 2026. Both structural entry conditions are met. The RSI
is 1.06 points from its MA trigger.

Capital: $1,000,000 simulated | Risk: $20,000 per trade (2%)

---

## Wave Structure Summary

### Wave W — ABC Structure

| Wave | Start | End | Points |
|------|-------|-----|--------|
| A | 59,930 | 71,768 | +11,838 |
| B | 71,768 | 67,323 | -4,445 |
| C | 67,323 | 72,221 | +4,898 |
| **W Complete** | **59,930** | **72,221** | **+12,291** |

### Wave X — Triangle ABCDE

| Wave | Start | End | Points |
|------|-------|-----|--------|
| A | 72,221 | 62,525 | -9,696 |
| B | 62,525 | 70,107 | +7,582 |
| C | 70,107 | 63,037 | -7,070 |
| D | 63,037 | 68,222 | +5,185 |
| E | 68,222 | 65,079 | -3,143 |
| **X Complete** | **72,221** | **65,079** | **-7,142** |

### Wave Y — WXY Subdivision

| Wave | Start | End | Points |
|------|-------|-----|--------|
| w | 65,079 | 74,035 | +8,956 |
| x | 74,035 | 65,623 | -8,412 |
| y | 65,623 | 76,013 | +10,390 |
| **Y Complete** | **65,079** | **76,013** | **+10,934** |

---

## Fibonacci Confluence

| Level | Price | Significance |
|-------|-------|--------------|
| Smaller y = smaller w | 74,652 | Primary entry trigger |
| Larger Y = Larger W | 77,370 | Re-entry trigger |
| Larger Y = 1.26W | 80,566 | Full invalidation |
| Target | 59,930 | WXY origin |

---

## Trade Framework

| Parameter | Value |
|-----------|-------|
| Direction | SHORT |
| Timeframe | 4 Hour |
| Capital | $1,000,000 |
| Risk per trade | $20,000 (2%) |
| Entry trigger | RSI crosses below RSI MA |
| Stop loss | 76,014 |
| Break even trigger | 68,941 |
| Second trade trigger | 65,558 |
| Second trade stop | 69,595 |
| Re-entry trigger | 77,305 |
| Re-entry stop | 80,566 |
| Target | 59,930 |

---

## Risk to Reward

| Metric | Value |
|--------|-------|
| Entry price | ~74,275 |
| Stop loss | 76,014 |
| Risk | ~1,739 points |
| Reward | ~14,345 points |
| **Risk to Reward** | **1 : 8.25** |
| Risk in dollars | $20,000 |
| Potential profit | $164,996 |
| Return on capital | 16.50% |

---

## Key Features — Version 1

- Complex WXY wave structure hardcoded with all key levels
- RSI momentum confirmation — dual condition entry
- Stop distance based position sizing — exact 2% risk
- Automated email alerts at every key level
- Re-entry framework if primary trade stopped out
- Break even mechanics protecting initial position
- Second trade scaling when Wave Y extends lower

---

## Email Alert Schedule

| Alert | Trigger |
|-------|---------|
| Primary entry executed | RSI cross below MA |
| Break even trigger hit | Price below 68,941 |
| Second trade trigger | Price below 65,558 |
| Re-entry approaching | Price above 77,305 |
| Target approaching | Price within 1,000 of 59,930 |
| Target hit | Price at 59,930 |
| Stop hit | Price above stop level |

---

## Data Source
```python
raw = yf.download('BTC-USD',
    start='2026-01-01', end='2026-03-18',
    interval='1h', auto_adjust=True)
btc = raw.resample('4h').agg({
    'Open': 'first', 'High': 'max',
    'Low': 'min', 'Close': 'last',
    'Volume': 'sum'}).dropna()
```

---

## Performance Status

| Metric | Value |
|--------|-------|
| Status | **ARMED — Awaiting RSI confirmation** |
| Entry date | 17 March 2026 |
| Current price | 74,635 |
| RSI gap to trigger | 1.06 points |
| Risk per trade | $20,000 (2%) |
| Potential profit at target | $164,996 |
| Return at target | 16.50% |

*Performance metrics will be updated when trade closes.*

---

## Repository Structure
```
btcusd-complex-wxy-backtest/
│
├── BTCUSD_Complex_WXY_Backtest.ipynb  — Full backtest notebook
├── README.md                           — This file
└── btc_trade_log.csv                   — Trade execution log
```

---

## How to Run

### Option 1 — Google Colab
Click the **Open in Colab** badge at the top of this README.

### Option 2 — Local
```bash
git clone https://github.com/mnyika-quant/btcusd-complex-wxy-backtest
cd btcusd-complex-wxy-backtest
pip install yfinance pandas numpy matplotlib
jupyter notebook BTCUSD_Complex_WXY_Backtest.ipynb
```

---

## Related Work

- [XAUUSD Elliott Wave Leading Diagonal Backtest](https://github.com/mnyika-quant/xauusd-elliott-wave-backtest) — 32.37% verified return
- [Full Analysis on Wave and Code](https://waveandcode.substack.com)

---

## Disclaimer

This repository is for educational and research purposes only.
It documents a systematic trading framework on a simulated
$1,000,000 paper trading account and does not constitute
financial advice.

---

*Wave and Code — where Elliott Wave structure meets systematic execution*
*waveandcode.substack.com | github.com/mnyika-quant | t.me/waveandcodesignals*
