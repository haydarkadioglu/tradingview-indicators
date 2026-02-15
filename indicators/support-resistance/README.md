# Support & Resistance Levels Indicator

## 📊 Overview

This TradingView Pine Script indicator automatically detects and displays **support** and **resistance** levels on your chart using pivot point analysis.

## ✨ Features

- ✅ **Automatic Level Detection**: Uses pivot point algorithm
- 📍 **Horizontal Lines**: Clear visual markers for key levels
- 🎯 **Smart Management**: Shows only top N levels (not cluttered)
- 🔔 **Price Alerts**: Get notified when price touches levels
- ⚙️ **Customizable**: All parameters adjustable

## 🎯 How It Works

### Pivot Point Detection

**Support Levels (Green Lines)**:
- Detected at pivot lows (local price bottoms)
- Areas where buyers typically step in
- Price bounces up from these levels

**Resistance Levels (Red Lines)**:
- Detected at pivot highs (local price tops)
- Areas where sellers typically step in
- Price bounces down from these levels

### Algorithm

```
Pivot High (Resistance):
  High[N] > High of surrounding candles
  
Pivot Low (Support):
  Low[N] < Low of surrounding candles
```

## 📥 Installation

1. Go to [TradingView](https://www.tradingview.com/)
2. Open Pine Editor (Alt + E)
3. Copy content from `support_resistance_indicator.pine`
4. Paste into Pine Editor
5. Click "Save" and "Add to Chart"

## ⚙️ Parameters

### Detection Settings
- **Pivot Length**: Number of bars to check (default: 5)
  - Higher = stronger but fewer levels
  - Lower = more levels but weaker
- **Lookback Bars**: How far back to scan (default: 100)

### Level Management
- **Max Support Levels**: Maximum green lines (default: 3)
- **Max Resistance Levels**: Maximum red lines (default: 3)

### Visual Settings
- **Show Support/Resistance**: Toggle visibility
- **Line Width**: Thickness of lines (1-4)
- **Colors**: Customize support/resistance colors

## 💡 Usage Tips

### ✅ Best Practices

- **Identify Key Zones**: Use levels for entry/exit planning
- **Set Stop Losses**: Place stops below support / above resistance
- **Wait for Confirmation**: Don't trade solely on levels
- **Multiple Timeframes**: Check levels on different timeframes

### 📈 Trading Strategies

**Bounce Strategy**:
1. Price approaches support level
2. Wait for bounce confirmation
3. Enter long position
4. Set stop below support

**Breakout Strategy**:
1. Price breaks through resistance
2. Wait for retest
3. Enter long on successful retest
4. Old resistance becomes new support

## 🎨 Visual Elements

- **Green Horizontal Lines**: Support levels
- **Red Horizontal Lines**: Resistance levels
- **Small Triangles**: Show where pivots were detected
  - Green ▲ = Support pivot
  - Red ▼ = Resistance pivot

## 🔔 Alerts

### Price at Support
Triggers when price comes within 0.2% of a support level

### Price at Resistance
Triggers when price comes within 0.2% of a resistance level

**Setup**:
1. Right-click chart → "Add Alert"
2. Select "Price at Support" or "Price at Resistance"
3. Configure notifications
4. Click "Create"

## 📊 Recommended Timeframes

- ✅ **15 minutes**: Intraday scalping levels
- ✅ **1 hour**: Day trading levels
- ✅ **4 hours**: Swing trading levels (recommended)
- ✅ **1 day**: Long-term investment levels

## 🔧 Customization Examples

### Conservative (Fewer, Stronger Levels)
```
Pivot Length: 10
Max Support Levels: 2
Max Resistance Levels: 2
```

### Aggressive (More Levels)
```
Pivot Length: 3
Max Support Levels: 5
Max Resistance Levels: 5
```

## ⚠️ Important Notes

- Levels are based on **historical pivots** (slight delay)
- Not all levels will hold (price can break through)
- Use with other indicators for confirmation
- Adjust parameters based on your trading style

## 🚀 Future Enhancements

Planned features:
- [ ] Zone visualization (filled areas)
- [ ] Fibonacci levels
- [ ] Volume-weighted levels
- [ ] Breakout detection alerts
- [ ] Level strength indicators

## ⚠️ Disclaimer

This indicator is for **educational and analysis purposes only**. Not financial advice. Support and resistance levels are not guaranteed to hold. Always use proper risk management.

## 💬 Support

For questions or suggestions, use GitHub Issues.

---

**Happy Trading! 📈📉**
