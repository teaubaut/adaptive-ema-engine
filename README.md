# Adaptive EMA Strategy Pro

> **A precision-engineered PineScript v5 strategy for TradingView**  
> Combines multi-EMA channel logic, ATR-based stop management, and dynamic risk-adjusted leverage control — built for disciplined algorithmic execution in crypto, FX, and equities.

---

## 📈 Overview

This strategy automates high-probability entries based on **EMA channel alignment** while managing exits and position sizing with **ATR volatility data** and **account risk constraints**.  
It’s designed to capture trending market phases while maintaining consistent risk exposure, even under varying leverage or collateral limits.

---

## ⚙️ Core Features

- **Multi-EMA Channel System**
  - Dual channel EMAs define structure and bias (fast and slow channels).
  - Optional line EMAs for higher-timeframe confirmation.

- **ATR-Based Stop & Take-Profit**
  - Dynamic stop-loss and take-profit based on real-time volatility.
  - Supports both ATR and EMA-based stop options.
  - Optional 1-tick buffer for precision stop placement.

- **Risk-Based Position Sizing**
  - Calculates position size automatically based on:
    - Account collateral allocation (`max collateral per trade`)
    - Maximum leverage allowed
    - Entry price and stop distance  
  - Ensures consistent R-multiple targets across trades.

- **Dynamic Leverage Engine**
  - Automatically adjusts leverage to maintain defined risk %.
  - Prevents over-exposure during high volatility.

- **Regime & Volatility Filters**
  - Optional ADX and Bollinger width filters to avoid chop zones.
  - Configurable thresholds for trend confirmation.

---

## 🧮 Inputs Summary

| Parameter | Description |
|------------|-------------|
| **Channel 1 EMA Length (High/Low)** | Fast trend structure |
| **Channel 2 EMA Length (High/Low)** | Slow trend structure |
| **Line 1 / Line 2 EMA Lengths** | Higher-timeframe directional filters |
| **Take Profit (R multiple)** | Multiplier of stop distance for TP |
| **Stop Basis** | Choose between Line-EMA or ATR for SL |
| **ATR Length / Multiplier** | Volatility basis for SL & TP |
| **Use Stop Buffer** | Adds 1 tick buffer above/below stop line |
| **Collateral / Leverage Inputs** | Used for automatic position sizing |

---

## 💡 Example Configuration

| Setting | Value |
|----------|-------|
| Channel 1 EMA | 9 |
| Channel 2 EMA | 21 |
| Line 1 EMA | 50 |
| Line 2 EMA | 200 |
| ATR Length | 14 |
| ATR Multiplier | 2.0 |
| Take Profit | 1.5R |
| Max Collateral | $10 |
| Max Leverage | 10x |

---

## 🧠 Strategy Logic (Simplified)

1. Identify trend via EMA alignment (fast > slow → bullish; fast < slow → bearish).  
2. Confirm volatility and regime filters.  
3. Calculate stop distance (ATR or EMA basis).  
4. Compute position size from risk % and available collateral.  
5. Place entry order with auto-adjusted leverage.  
6. Manage exits at defined R-multiple TP and SL levels.

---

## 🛠️ Requirements

- **TradingView** (v5 compatible)
- **Broker / exchange simulator** for backtesting leverage
- (Optional) Real-time data subscription for intraday use

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](./LICENSE) file for details.  
Feel free to fork, modify, or integrate with attribution.

---

## 🤝 Contributing

Pull requests are welcome!  
If you have ideas for filters, regime logic, or risk-model enhancements, open an issue or PR.

---

## 💬 Author

**Nathan Blair**  
Algorithmic trading enthusiast, DeFi systems builder, and technical strategy designer.  

---

### ⭐ Support
If you find this project useful, please consider giving it a ⭐ on GitHub to help others discover it.
