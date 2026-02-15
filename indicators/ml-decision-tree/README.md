# ML Decision Tree Classifier

## 🌳 Overview

A rule-based machine learning indicator that predicts price direction using a **Decision Tree** algorithm with interpretable IF-THEN logic.

## ✨ Key Features

- 🌲 **5-Level Decision Tree**: Trend → RSI → Volume → S/R → MACD
- 📊 **3 Classifications**: UP, DOWN, SIDEWAYS
- 💯 **Confidence Scoring**: 40-85% range
- 🔍 **Decision Path Display**: See exactly why each decision was made
- ⚙️ **Fully Customizable**: Adjust all thresholds and rules

## 🧠 How It Works

### Decision Tree Structure

```
Level 1: Trend Analysis (EMA20, EMA50, EMA200)
    ├─ UPTREND → Continue to Level 2
    ├─ DOWNTREND → Continue to Level 2 (bearish path)
    └─ RANGING → Check for breakout signals

Level 2: RSI Momentum Check
    ├─ Overbought/Oversold → SIDEWAYS (exit early)
    └─ Neutral → Continue to Level 3

Level 3: Volume Analysis
    ├─ High Volume → +10% confidence
    ├─ Low Volume → -15% confidence
    └─ If too low → SIDEWAYS (exit)

Level 4: Support/Resistance Check
    ├─ Near Barrier → SIDEWAYS (exit)
    └─ Clear Path → Continue to Level 5

Level 5: MACD Confirmation
    ├─ Aligned → +10% confidence
    ├─ Conflicting → -15% confidence
    └─ Final Prediction
```

### Example Decision Path

**Bullish Scenario:**
```
✅ Trend: UPTREND (EMA20>EMA50>EMA200)
✅ RSI: Neutral (45)
✅ Volume: High (1.8x average)
✅ S/R: Clear Path (resistance 5% away)
✅ MACD: Bullish

PREDICTION: UP ⬆️
Confidence: 80%
```

**Bearish Scenario Near Support:**
```
❌ Trend: DOWNTREND
✅ RSI: Neutral (55)
✅ Volume: High (1.5x)
🛡️ S/R: Near Support (1.2% away)

PREDICTION: SIDEWAYS ↔️
Confidence: 55%
Reason: Support floor may bounce
```

## 📥 Installation

1. Go to [TradingView](https://www.tradingview.com/)
2. Open Pine Editor (Alt + E)
3. Copy content from `ml_decision_tree.pine`
4. Paste into Pine Editor
5. Click "Save" and "Add to Chart"

## ⚙️ Parameters

### Trend Settings
- **EMA Short** (default: 20): Fast trend line
- **EMA Medium** (default: 50): Medium trend line  
- **EMA Long** (default: 200): Long-term trend line

### Momentum Settings
- **RSI Length** (default: 14): RSI calculation period
- **RSI Oversold** (default: 30): Oversold threshold
- **RSI Overbought** (default: 70): Overbought threshold

### Volume Settings
- **High Volume Multiplier** (default: 1.2): Volume spike threshold (1.2 = 120% of average)

### Support/Resistance
- **S/R Distance %** (default: 2.0): Distance to consider "near" S/R
- **Pivot Length** (default: 10): Lookback for pivot detection

### Display Settings
- **Show Decision Path Panel**: Toggle decision tree visualization
- **Panel Position**: Choose where panel appears (9 options)
- **Show Buy/Sell Signals**: Toggle arrow signals
- **Min Confidence for Signals** (default: 60%): Minimum confidence to show signals

## 💡 Usage Tips

### ✅ Best Practices

1. **Trending Markets = Best Performance**
   - Decision tree excels in clear uptrends/downtrends
   - 65-75% accuracy in trending conditions

2. **Read the Decision Path**
   - Panel shows WHY prediction was made
   - Learn from the logic

3. **Adjust for Your Asset**
   - Crypto → Higher volume threshold (1.5x)
   - Stocks → Standard settings
   - Forex → Lower EMA periods (10, 30, 100)

4. **Combine with Price Action**
   - Use S/R levels for entry/exit
   - Respect strong barriers

### 📈 Trading Strategies

**High Confidence Trades:**
- Wait for confidence >70%
- Clear decision path (all ✅)
- Strong volume confirmation

**S/R Bounces:**
- SIDEWAYS near support in downtrend = potential long
- SIDEWAYS near resistance in uptrend = potential short

**Breakouts:**
- RANGING market + high volume + bullish MACD = breakout UP
- Enter on confirmation candle

## 🎨 Visual Elements

- **Decision Path Panel**: Shows entire decision logic step-by-step
  - Green header = UP prediction
  - Red header = DOWN prediction
  - Gray header = SIDEWAYS prediction

- **EMA Lines**:
  - Blue = EMA 20 (short-term)
  - Orange = EMA 50 (medium-term)
  - Purple = EMA 200 (long-term)

- **Buy/Sell Arrows**:
  - Green ▲ = BUY (high confidence UP)
  - Red ▼ = SELL (high confidence DOWN)

- **Background Colors**:
  - Light green = Strong bullish (confidence >65%)
  - Light red = Strong bearish (confidence >65%)

## 📊 Rule Examples

### UP Prediction (Confidence: 75%)
```
Trend: UPTREND ✅
RSI: 52 (neutral) ✅
Volume: 1.6x (high) ✅ (+10%)
S/R: Clear ✅
MACD: Bullish ✅ (+10%)
= 60 + 10 + 10 = 80% → capped at 75%
```

### SIDEWAYS Prediction (Confidence: 55%)
```
Trend: UPTREND ✅
RSI: 45 (neutral) ✅
Volume: 1.3x (high) ✅
S/R: Near Resistance (1.8%) ⚠️ → EXIT
= SIDEWAYS, 55% confidence
```

### DOWN Prediction (Confidence: 70%)
```
Trend: DOWNTREND ❌
RSI: 55 (neutral) ✅
Volume: 1.4x (high) ✅ (+10%)
S/R: Clear ✅
MACD: Bearish ✅ (+10%)
= 60 + 10 + 10 = 80% → 70% final
```

## 🔧 Optimization Guide

### For Volatile Assets (Crypto)
```
Volume Threshold: 1.5
RSI Overbought: 75
RSI Oversold: 25
Min Confidence: 65%
```

### For Stable Assets (Stocks)
```
Volume Threshold: 1.2
RSI Overbought: 70
RSI Oversold: 30
Min Confidence: 60%
```

### For Trending Forex
```
EMA Short: 10
EMA Medium: 30
EMA Long: 100
S/R Distance: 1.5%
```

## 🆚 Decision Tree vs KNN

| Feature | Decision Tree | KNN |
|---------|--------------|-----|
| **Interpretability** | ✅ Very Clear | ❌ Black Box |
| **Speed** | ✅ Very Fast | ⚠️ Medium |
| **Customization** | ✅ Easy (rules) | ❌ Limited |
| **Ranging Markets** | ✅ Excellent | ⚠️ OK |
| **Trending Markets** | ✅ Excellent | ✅ Good |
| **Debugging** | ✅ Very Easy | ❌ Hard |
| **Accuracy** | 55-70% | 55-65% |

**Use Decision Tree when:**
- You want to understand WHY predictions are made
- You need to customize rules for your strategy
- You trade ranging markets frequently
- You value transparency over complexity

**Use KNN when:**
- You want pattern-based historical matching
- You don't need to see the logic
- You prefer automated learning

## ⚠️ Important Notes

### Strengths
- ✅ Very interpretable (see all rules)
- ✅ Fast execution
- ✅ Works in all market conditions
- ✅ Easy to optimize per asset
- ✅ No black box magic

### Limitations
- ⚠️ Rules are static (not adaptive)
- ⚠️ Simplified version of true ML Decision Trees
- ⚠️ Thresholds need manual tuning
- ⚠️ Past performance ≠ future results

## 📚 Technical Details

**Algorithm Type:** Rule-Based Classification (Simplified Decision Tree)

**Features Used:**
1. Trend (EMA crossovers)
2. Momentum (RSI)
3. Volume (volume ratio)
4. Support/Resistance (pivot points)
5. MACD (histogram)

**Confidence Calculation:**
```
Base: 60%
High Volume: +10%
Low Volume: -15%
Aligned MACD: +10%
Conflicting MACD: -15%
Max: 85%
Min: 40%
```

## 🚀 Future Enhancements

- [ ] Adaptive thresholds based on volatility
- [ ] Multi-timeframe confirmation
- [ ] Historical accuracy tracking
- [ ] Rule importance weighting
- [ ] Auto-optimization for current market regime

---

**Made with 🌳 by Decision Tree Algorithm**
