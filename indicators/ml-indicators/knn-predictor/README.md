# ML Price Predictor Indicator

## 🤖 Overview

A machine learning-inspired TradingView indicator that predicts future price movements using **K-Nearest Neighbors (KNN)** pattern matching and historical analysis.

## ✨ Features

- 🎯 **Price Movement Prediction**: Forecasts direction (UP/DOWN/SIDEWAYS)
- 📊 **Target Price Calculation**: Shows expected price level
- 💯 **Confidence Scoring**: Indicates prediction reliability (0-100%)
- 🔍 **Pattern Matching**: Finds similar historical situations
- 📈 **Buy/Sell Signals**: High-confidence trading signals
- ⚙️ **Customizable Parameters**: Adjust weights and sensitivity

## 🧠 How It Works

### K-Nearest Neighbors (KNN) Algorithm

The indicator analyzes historical price patterns to predict future movements:

```
1. Extract Features → Current market state (RSI, volume, trend, price position)
2. Find Similar Patterns → Search history for similar situations
3. Analyze Outcomes → What happened after those patterns?
4. Make Prediction → Average outcome = prediction
5. Calculate Confidence → Pattern similarity = confidence
```

### Features Analyzed

- **RSI (Relative Strength Index)**: Momentum indicator
- **Volume Ratio**: Volume spike detection
- **Trend Strength**: EMA slope (uptrend/downtrend)
- **Price Position**: Where price is in recent range

### Example

```
Current State:
- RSI: 35 (oversold)
- Volume: 2x average (high)
- Trend: Downtrend slowing
- Price Position: Near 100-bar low

Similar Past Patterns Found: 10
Average Outcome: +5.2% in next 10 bars
Confidence: 73%

PREDICTION: UP ⬆️
Target: $45,280
```

## 📥 Installation

1. Go to [TradingView](https://www.tradingview.com/)
2. Open Pine Editor (Alt + E)
3. Copy content from `ml_price_predictor.pine`
4. Paste into Pine Editor
5. Click "Save" and "Add to Chart"

## ⚙️ Parameters

### Prediction Settings
- **Historical Lookback Bars** (50-200, default: 100)
  - How far back to search for patterns
  - Higher = more data, slower
  
- **K Nearest Neighbors** (5-20, default: 10)
  - Number of similar patterns to analyze
  - Higher = smoother predictions
  
- **Predict N Bars Ahead** (5-30, default: 10)
  - Prediction timeframe
  - Lower = short-term, Higher = long-term

### Feature Weights
Adjust importance of each feature (0.1-2.0):
- **RSI Weight** (default: 1.0)
- **Volume Weight** (default: 0.8)
- **Trend Weight** (default: 1.2) - Most important
- **Price Position Weight** (default: 1.0)

### Display Settings
- **Show Prediction Label**: Info box with direction/target/confidence
- **Show Target Price Line**: Dashed line at predicted price
- **Show Buy/Sell Signals**: Arrows for high-confidence trades
- **Min Confidence for Signals** (30-80%, default: 50%)

## 💡 Usage Tips

### ✅ Best Practices

1. **Higher Timeframes = Better Predictions**
   - 4H/1D charts more reliable than 5m/15m
   - More stable patterns on larger timeframes

2. **Confidence Matters**
   - >70% confidence: High probability
   - 50-70%: Moderate, use caution
   - <50%: Low, avoid trading

3. **Combine with Other Indicators**
   - Use S/R levels for confirmation
   - Check volume for validation
   - Look at trend context

4. **Adjust Weights for Your Market**
   - Crypto: Increase volume weight
   - Stocks: Increase trend weight
   - Forex: Balanced weights

### 📈 Trading Strategies

**High-Confidence Trades**:
- Wait for confidence >65%
- Direction should be STRONG UP/DOWN
- Enter on confirmation candle
- Set stop loss 2% beyond prediction

**Swing Trading**:
- Use 4H or 1D timeframe
- Prediction horizon: 10-20 bars
- Target price as take-profit level

**Scalping** (Advanced):
- Lower timeframes (15m/1H)
- Lower prediction horizon (5-10 bars)
- Increase min_confidence to 60%+

## 🎨 Visual Elements

- **Prediction Label**: Shows direction, target, change %, confidence
- **Target Line**: Dashed line at predicted price level
  - Green = bullish prediction
  - Red = bearish prediction
- **Buy/Sell Arrows**: High-confidence signals
  - Green ▲ = BUY
  - Red ▼ = SELL
- **Background Color**: Light shading for strong predictions
  - Light green = Strong bullish
  - Light red = Strong bearish

## 📊 Prediction Classes

| Prediction | Change % | Meaning |
|-----------|----------|---------|
| STRONG UP 🚀 | >+2% | High bullish momentum |
| UP ⬆️ | +0.5% to +2% | Moderate bullish |
| SIDEWAYS ↔️ | -0.5% to +0.5% | No clear direction |
| DOWN ↘️ | -0.5% to -2% | Moderate bearish |
| STRONG DOWN 📉 | <-2% | High bearish momentum |

## 🔧 Optimization Tips

### Fine-Tuning Parameters

**For Volatile Assets (Crypto)**:
```
K Neighbors: 15
Lookback: 150
Volume Weight: 1.2
Min Confidence: 60%
```

**For Stable Assets (Blue-chip Stocks)**:
```
K Neighbors: 10
Lookback: 100
Trend Weight: 1.5
Min Confidence: 50%
```

**For Ranging Markets**:
```
K Neighbors: 8
Price Position Weight: 1.5
RSI Weight: 1.3
```

## ⚠️ Important Notes

### Limitations

- **Not 100% Accurate**: ML predictions are probabilistic, not guaranteed
- **Past ≠ Future**: Historical patterns may not repeat exactly
- **Computation**: Uses recent history only (Pine Script limitations)
- **No External Data**: Cannot access news, fundamentals, etc.

### Risk Management

- ✅ Always use stop losses
- ✅ Don't risk more than 1-2% per trade
- ✅ Verify predictions with price action
- ✅ Consider market context (news, events)

## 🔬 Technical Details

### Algorithm Complexity
- Time: O(N × K) where N = lookback, K = neighbors
- Space: O(N) for storing distances/outcomes

### Performance
- Typical load time: <2 seconds
- Real-time updates: Every bar close
- Max lookback: 200 bars (Pine Script limit)

## 📊 Recommended Timeframes

- ✅ **1 Day**: Most reliable (long-term predictions)
- ✅ **4 Hours**: Swing trading (good balance)
- ✅ **1 Hour**: Intraday trading (moderate reliability)
- ⚠️ **15 Minutes**: Scalping (lower accuracy, higher noise)
- ❌ **<15 Minutes**: Not recommended (too noisy)

## 🚀 Future Enhancements

Potential improvements:
- [ ] Multi-timeframe analysis
- [ ] Ensemble predictions (multiple algorithms)
- [ ] Dynamic weight adjustment
- [ ] Market regime detection
- [ ] Breakout probability scoring

## ⚠️ Disclaimer

This indicator is for **educational and analysis purposes only**. 

- NOT financial advice
- Past performance doesn't guarantee future results
- Machine learning predictions are probabilistic
- Always do your own research (DYOR)
- Use proper risk management

---

**Happy Trading! 🤖📈**
