# TradingView Scripts Collection

Professional indicators and strategies written in Pine Script for the TradingView platform.

## 📁 Folder Structure

```
tradingview/
├── indicators/          # Trading indicators
│   └── buy-sell-signals/
│       ├── buy_sell_indicator.pine
│       └── README.md
└── strategies/          # Trading strategies (coming soon)
```

## 📊 Available Indicators

### 1. [Buy/Sell Signals - Multi-Condition](./indicators/buy-sell-signals/)

An indicator that generates reliable buy/sell signals by combining multiple technical indicators.

**Features**:
- ✅ RSI + EMA + Volume analysis
- 📍 Visual markers on candles
- 🔔 Automatic alert system
- ⚙️ Customizable parameters

[Detailed Documentation →](./indicators/buy-sell-signals/README.md)

### 2. [Support & Resistance Levels](./indicators/support-resistance/)

Automatically detects and displays key support and resistance levels using pivot point analysis.

**Features**:
- ✅ Automatic pivot detection
- 📍 Horizontal lines for key levels
- 🎯 Smart level management (top 3 each)
- 🔔 Price touch alerts
- ⚙️ Fully customizable

[Detailed Documentation →](./indicators/support-resistance/README.md)

### 3. [ML Price Predictor (KNN)](./indicators/ml-predictor/) 🤖

Machine learning-inspired indicator that predicts future price movements using K-Nearest Neighbors pattern matching.

**Features**:
- 🤖 Pattern recognition & historical analysis
- 🎯 Price direction & target prediction
- 💯 Confidence scoring (0-100%)
- 📊 Buy/Sell signals with high accuracy
- ⚙️ Customizable feature weights

[Detailed Documentation →](./indicators/ml-predictor/README.md)

### 4. [ML Decision Tree Classifier](./indicators/ml-decision-tree/) 🌳

Rule-based machine learning classifier that predicts price direction using interpretable decision tree logic.

**Features**:
- 🌲 5-level decision tree (Trend→RSI→Volume→S/R→MACD)
- 🔍 Decision path visualization (see WHY predictions are made)
- 📊 UP/DOWN/SIDEWAYS classification
- 💯 Confidence scoring (40-85%)
- ⚙️ Fully customizable rules and thresholds

[Detailed Documentation →](./indicators/ml-decision-tree/README.md)

### 5. [Ensemble ML Predictor](./indicators/ml-ensemble/) 🎯

**The most powerful ML indicator!** Combines three algorithms (KNN, Linear Regression, Decision Tree) using weighted voting for maximum accuracy.

**Features**:
- 🤖 3 algorithms in 1 (KNN + LinReg + DTree)
- 🗳️ Weighted voting system (customizable weights)
- 💯 Consensus scoring (algorithm agreement %)
- 📊 Dual visualization (ensemble + individual votes)
- 🎯 Highest accuracy (60-75% expected)
- ⚙️ Fully optimizable for any market

[Detailed Documentation →](./indicators/ml-ensemble/README.md)

## 🚀 Quick Start

### Loading Scripts to TradingView

1. Open the `.pine` file of your desired indicator
2. Copy the content
3. Open [TradingView](https://www.tradingview.com/) Pine Editor (Alt + E)
4. Paste the code and click "Save"
5. Add to chart with "Add to Chart"

### Local Development

```powershell
# Clone the repository
git clone <repo-url>
cd tradingview

# Edit an indicator
code indicators/buy-sell-signals/buy_sell_indicator.pine
```

## 📚 Indicator Development Guide

### Adding a New Indicator

1. Create a new folder in `indicators/`:
   ```powershell
   mkdir indicators/my-new-indicator
   ```

2. Create Pine Script file:
   ```powershell
   New-Item indicators/my-new-indicator/my_indicator.pine
   ```

3. Add README:
   ```powershell
   New-Item indicators/my-new-indicator/README.md
   ```

### Pine Script v5 Best Practices

- ✅ Use `@version=5` directive
- ✅ Group input parameters
- ✅ Organize code into sections (calculations, signals, visuals)
- ✅ Make alert messages descriptive
- ✅ Optimize performance (avoid unnecessary calculations)

## 🎯 Future Plans

### Indicators
- [ ] RSI Divergence Detector
- [ ] Support/Resistance Levels
- [ ] Volume Profile
- [ ] Fibonacci Auto-Retracement
- [ ] Market Structure (HH/HL/LL/LH)

### Strategies
- [ ] Grid Trading Bot
- [ ] Mean Reversion Strategy
- [ ] Breakout Strategy
- [ ] DCA (Dollar Cost Averaging) Strategy

## 📖 Resources

- [Pine Script Documentation](https://www.tradingview.com/pine-script-docs/)
- [TradingView Community Scripts](https://www.tradingview.com/scripts/)
- [Pine Script Reference](https://www.tradingview.com/pine-script-reference/v5/)

## ⚠️ Disclaimer

All scripts in this repository are **for educational and analysis purposes only**. Not financial advice. Use at your own risk and responsibility.

## 📝 License

MIT License - See LICENSE file for details.

## 💬 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

---

### 5. 📊 Trend Strength Signals [Enhanced]

**Dynamic trend detection with visual strength gauge**

- **Purpose**: Bollinger Bands-based trend momentum indicator
- **Method**: Statistical deviation analysis with visual feedback
- **Output**: Trend direction, strength gauge, TP signals
- **Features**:
  - Real-time trend strength visualization
  - Dynamic cloud with gradient coloring
  - Automatic take profit signals
  - Multi-timeframe compatible

[📖 Read Full Documentation](indicators/trend-strength/README.md)

---

**Happy Coding & Trading! 🚀📈**
