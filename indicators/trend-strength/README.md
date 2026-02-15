# 📊 Trend Strength Signals [Enhanced]

**Bollinger Bands tabanlı trend gücü ve momentum indicator'ı**

Orijinal: AlgoAlpha  
Modified & Enhanced Version

---

## 🎯 Özellikler

### Mevcut Özellikler

- **Dynamic Trend Detection**: Bollinger Bands ile otomatik trend tespiti
- **Visual Gauge**: Trend gücünü görsel olarak gösteren gauge (ölçek)
- **Cloud Visualization**: Trend gücüne göre renklenen bulut gösterimi
- **TP Signals**: Take Profit noktalarını otomatik işaretler
- **Bar Colors**: Trend durumuna göre mum renklendirmesi
- **Multi-timeframe Uyumlu**: Her timeframe'de çalışır

### Sinyal Türleri

1. **Trend Signals**
   - ▲ Yukarı ok: Bullish trend başlangıcı
   - ▼ Aşağı ok: Bearish trend başlangıcı

2. **Take Profit Signals**
   - X (yeşil): Short pozisyon TP
   - X (kırmızı): Long pozisyon TP

---

## 📋 Nasıl Çalışır?

### Temel Mantık

```
Basis = SMA(20)
Upper Band = Basis + StdDev
Lower Band = Basis - StdDev

Trend = UP   if Price > Basis AND Price > Upper Band
Trend = DOWN if Price < Basis AND Price < Lower Band
```

### Trend Strength Calculation

**Gradient Formula:**
```pine
grad = |basis - close| / highest(|basis - close|, 200) * 100
strength = 100 - min(grad, 40)
```

Gauge rengi trend gücünü gösterir:
- **Yeşil gradient**: Güçlü yukarı trend
- **Kırmızı gradient**: Güçlü aşağı trend
- **Soluk renkler**: Zayıf trend

---

## ⚙️ Parametreler

| Parametre | Default | Açıklama |
|-----------|---------|----------|
| **Enable Cloud** | true | Bollinger Bands bulutunu göster/gizle |
| **Period** | 20 | SMA ve StdDev periyodu |
| **StdDev Multiplier** | 2.5 | Take profit için standart sapma çarpanı |
| **Gauge Size** | 25 | Trend gücü ölçeğinin boyutu |
| **Up Color** | #00ffbb | Yukarı trend rengi (turkuaz) |
| **Down Color** | #ff1100 | Aşağı trend rengi (kırmızı) |

---

## 💡 Kullanım Önerileri

### 1. Trend Takibi

```
✅ Bullish Setup:
- Fiyat upper band üzerinde
- Gauge yeşil ve yüksek
- ▲ sinyali görüldü
→ LONG pozisyon aç

✅ Bearish Setup:
- Fiyat lower band altında
- Gauge kırmızı ve yüksek
- ▼ sinyali görüldü
→ SHORT pozisyon aç
```

### 2. Take Profit Kullanımı

**TP Multiplier = 2.5** (default):
- Agresif: 1.5 - 2.0
- Balanced: 2.0 - 3.0
- Conservative: 3.0 - 4.0

### 3. Timeframe Stratejisi

| Timeframe | Kullanım | Period Önerisi |
|-----------|----------|----------------|
| 1m - 5m | Scalping | 10 - 15 |
| 15m - 1h | Intraday | 20 - 30 |
| 4h - 1D | Swing | 30 - 50 |

---

## 🔧 Planlanan Geliştirmeler

### Phase 1: Signal Quality Improvements

- [ ] **RSI Confirmation**: Trend sinyaline RSI filtresi ekle
- [ ] **Volume Filter**: Düşük volume'da sinyal verme
- [ ] **Multi-timeframe Confluence**: Üst timeframe trend onayı
- [ ] **Dynamic TP**: Volatiliteye göre otomatik TP ayarı

### Phase 2: Advanced Features

- [ ] **Divergence Detection**: Price/indicator uyumsuzluğu
- [ ] **Support/Resistance Integration**: S/R seviyelerinde uyarı
- [ ] **Trend Strength Score**: Numeric trend gücü puanı (0-100)
- [ ] **Adaptive Period**: Volatiliteye göre otomatik period ayarı

### Phase 3: ML Integration

- [ ] **Pattern Recognition**: Geçmiş başarılı patternleri öğren
- [ ] **Success Rate Display**: Her sinyalin başarı oranını göster
- [ ] **AI-Enhanced TP**: ML ile optimal TP seviyesi tahmini

---

## 📊 Indicator Kombinasyonları

### Güçlü Setups

**1. Trend Strength + KNN Predictor**
```
Trend Strength: Trend yönünü belirler
KNN: Target fiyatı tahmin eder
→ Kombine sinyal = Yüksek güvenilirlik
```

**2. Trend Strength + Ensemble ML**
```
Trend Strength: Momentum tespiti
Ensemble: ML konsensus
→ Çift onay sistemi
```

**3. Trend Strength + Support/Resistance**
```
Trend Strength: Giriş sinyali
S/R: Entry/Exit seviyeleri
→ Net risk/reward
```

---

## 🎨 Görsel Rehber

### Gauge Yorumlama

```
HIGH (Top 80-100%)     → Çok güçlü trend
MEDIUM (40-80%)        → Orta güçlü trend
LOW (0-40%)            → Zayıf trend / sideways
```

### Cloud Interpretation

```
Koyu renk bulut   → Güçlü trend
Açık renk bulut   → Zayıf trend
Gri bulut         → Trend yok (sideways)
```

---

## ⚠️ Risk Uyarıları

1. **False Signals**: Sideways piyasalarda çok sinyal verebilir
2. **Lagging Nature**: Bollinger Bands gecikme gösterir
3. **Whipsaw Risk**: Volatil dönemlerde hatalı sinyaller
4. **No Stop Loss**: Indicator SL vermez, manuel ekle!

---

## 📈 Performance Tips

### Optimize Settings

**Crypto (Volatile):**
```
Period: 15
StdDev Mult: 2.0
Gauge: 30
```

**Stocks (Stable):**
```
Period: 20
StdDev Mult: 2.5
Gauge: 25
```

**Forex:**
```
Period: 25
StdDev Mult: 3.0
Gauge: 20
```

---

## 🔗 İlgili Indicators

- [ML KNN Predictor](../ml-predictor/README.md) - Pattern-based prediction
- [Ensemble ML Predictor](../ml-ensemble/README.md) - Multi-algorithm consensus
- [Decision Tree Classifier](../ml-decision-tree/README.md) - Rule-based signals

---

**Original Credit:** AlgoAlpha  
**License:** Mozilla Public License 2.0  
**Enhanced By:** Custom ML Trading Project
