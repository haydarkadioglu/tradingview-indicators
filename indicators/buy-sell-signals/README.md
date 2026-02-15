# Buy/Sell Signals Indicator

## 📊 Overview

This TradingView Pine Script indicator generates reliable buy and sell signals by combining multiple technical indicators. **Signals are not random** - each signal requires 4 different technical conditions to be met simultaneously.

## ✨ Features

- ✅ **Multi-Condition Signals**: RSI, EMA, Trend and Volume analysis
- 📍 **Clear Visual Markers**: Arrow markers above/below candles
- 🔔 **Alert System**: Automatic notifications
- ⚙️ **Customizable Parameters**: All settings are adjustable
- 🎨 **Clean Appearance**: Background colors and EMA lines

## 🎯 Signal Logic

### 🟢 BUY Signal

**All conditions must be TRUE simultaneously:**

1. ✅ **RSI < 30** - Oversold zone
2. ✅ **Price crosses above EMA20** - Price gained upward momentum
3. ✅ **EMA20 > EMA50** - Uptrend confirmed
4. ✅ **Volume > Average × 1.5** - High volume confirmation

**Visual**: Green ▲ arrow + "BUY" label **below** the candle

### 🔴 SELL Signal

**All conditions must be TRUE simultaneously:**

1. ✅ **RSI > 70** - Overbought zone
2. ✅ **Price crosses below EMA20** - Price gained downward momentum
3. ✅ **EMA20 < EMA50** - Downtrend confirmed
4. ✅ **Volume > Average × 1.5** - High volume confirmation

**Visual**: Red ▼ arrow + "SELL" label **above** the candle

## 📥 Installation

### 1. Load Script to TradingView

1. Go to [TradingView](https://www.tradingview.com/)
2. Open Pine Editor (Alt + E)
3. Copy the content of `buy_sell_indicator.pine` file
4. Paste into Pine Editor
5. Click "Save" button
6. Add to chart with "Add to Chart"

### 2. Alternative: Direct Copy-Paste

```pine
// Code: Copy from buy_sell_indicator.pine file
```

## ⚙️ Parameters

### RSI Settings
- **RSI Length**: Default 14 (RSI calculation period)
- **RSI Oversold**: Default 30 (threshold for buy signal)
- **RSI Overbought**: Default 70 (threshold for sell signal)

### EMA Settings
- **Fast EMA Period**: Default 20 (fast moving average)
- **Slow EMA Period**: Default 50 (slow moving average)
- **Show EMA Lines**: Show/hide EMA lines

### Volume Settings
- **Volume Multiplier**: Default 1.5 (how many times average volume required)

### Visual Settings
- **Show Buy/Sell Labels**: Show/hide signals
- **Label Size**: Arrow marker size (tiny/small/normal/large)

## 🔔 Alert Setup

1. Right-click on chart → "Add Alert"
2. Condition: "Buy Signal Alert" or "Sell Signal Alert"
3. Select notification method from "Notifications" tab
4. Click "Create" button

Alert messages automatically show which conditions were met.

## 📈 Usage Recommendations

### ✅ Successful Usage

- **Multiple Timeframes**: Confirm on different timeframes
- **Trend Following**: Only consider signals in the direction of the trend
- **Risk Management**: Don't forget to use stop-loss
- **Backtesting**: Test on historical data

### ⚠️ Important Considerations

- May be misleading in sideways markets
- Reliability decreases in low-volume coins
- Technical analysis may be insufficient during news events
- **This is not investment advice!**

## 🎨 Visual Features

- **Green/Red Arrows**: Main signals
- **Blue EMA20 / Orange EMA50**: Trend lines
- **Green Background**: RSI oversold zone (< 30)
- **Red Background**: RSI overbought zone (> 70)

## 🔧 Customization

You can adjust parameters according to your own strategy:

**Fewer Signals (Conservative)**:
- RSI Oversold: 20
- RSI Overbought: 80
- Volume Multiplier: 2.0

**More Signals (Aggressive)**:
- RSI Oversold: 40
- RSI Overbought: 60
- Volume Multiplier: 1.2

## 📊 Tested Timeframes

- ✅ 1 minute (scalping)
- ✅ 5 minutes
- ✅ 15 minutes
- ✅ 1 hour (recommended)
- ✅ 4 hours (recommended)
- ✅ 1 day (swing trading)

## 🚀 Future Updates

Planned features:
- [ ] Multiple timeframe analysis
- [ ] Fibonacci retracement levels
- [ ] Support/Resistance detection
- [ ] Risk/Reward ratio display
- [ ] Win rate statistics

## 📝 Version History

- **v1.0** (2026-02-10): Initial release
  - Multi-condition buy/sell signals
  - Customizable parameters
  - Alert system
  - Visual indicators

## ⚠️ Disclaimer

This indicator is for educational and analysis purposes only. **Not investment advice.** Seek professional advice before making financial decisions. Past performance does not guarantee future results.

## 💬 Support

You can use GitHub Issues for questions or suggestions.

---

**Happy Trading! 📈📉**
