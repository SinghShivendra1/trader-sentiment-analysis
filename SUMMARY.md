# Trader Performance vs Market Sentiment Analysis

## Overview
This project analyzes how market sentiment (Fear vs Greed) influences trader behavior and performance on Hyperliquid.

The goal is to identify patterns and derive **actionable trading strategies** using:
- Bitcoin Fear & Greed Index
- Historical trader execution data

---

# Part A - Data Preparation

## Datasets

### 1. Bitcoin Market Sentiment
- Columns: `timestamp`, `value`, `classification`, `date`
- Categories:
  - Fear
  - Extreme Fear
  - Neutral
  - Greed
  - Extreme Greed

### 2. Hyperliquid Trader Data
- ~211,000+ trade records
- Key fields:
  - account
  - execution price
  - size usd
  - side / direction
  - timestamp
  - closed pnl

---

## Data Cleaning

- Standardized column names to lowercase
- Converted timestamps to datetime format
- Extracted daily-level `date` for alignment

---—-------------------------------------

## Data Alignment

- Both datasets were aligned at **daily granularity**
- Sentiment categories were grouped into:

| Original | Group |
|--------|------|
| Extreme Fear, Fear | Fear |
| Greed, Extreme Greed | Greed |
| Neutral | Neutral |

---

## Key Metrics Created

- **Daily PnL per account**
- **Win rate** (PnL > 0)
- **Average trade size (USD)**
- **Number of trades per day**
- **Long/Short ratio**

---—-------------------------------------

# Part B - Analysis

—-------------------------------------

##  1. Performance: Fear vs Greed

### Results

| Metric | Fear | Greed |
|------|------|------|
| Avg Daily PnL | 5185 | 4144 |
| Median Daily PnL | 122 | 265 |
| Total PnL | 4.09M | 4.86M |
| Win Rate | ~35.7% | ~36.2% |
| Drawdown Proxy | Similar (~-8800) | Similar (~-8800) |

---—-------------------------------------

### 💡 Insights

**Insight 1 - Profitability vs Consistency**
- Fear → higher average PnL (driven by large outliers)
- Greed → higher median PnL → more consistent profits

**Insight 2 - Greed markets scale better**
- Higher total PnL due to increased trading activity

**Insight 3 - Risk remains constant**
- Drawdown does not significantly change across regimes

---

##  2. Behavioral Changes

### Trade Size

| Sentiment | Avg Size (USD) |
|----------|---------------|
| Fear | 7182 |
| Greed | 4574 |

 Traders take **larger positions during Fear**

---—-------------------------------------

### Trade Frequency
- More trades occur during **Greed periods**

---—-------------------------------------

### Long/Short Ratio
- Balanced across both regimes  
- No strong directional bias observed

---—-------------------------------------

###  Insights

**Insight 4 - Aggressive behavior in Fear**
- Traders increase position size due to volatility

**Insight 5 - Activity increases in Greed**
- More participation and liquidity

**Insight 6 - Sentiment does not drive direction**
- Traders are not purely following sentiment trends

---—-------------------------------------

##  3. Trader Segmentation

---—-------------------------------------

### 📊 Frequent vs Infrequent Traders

| Segment | Avg PnL (Fear) | Avg PnL (Greed) | Win Rate |
|--------|--------------|----------------|----------|
| Frequent | ~47 | ~41 | ~42% |
| Infrequent | ~62 | **~156** | ~38% |

---—-------------------------------------

### Insights

**Insight 7: Strategy Differences**
- Frequent traders:
  - High activity
  - Stable, lower profits
- Infrequent traders:
  - Low activity
  - High profits in Greed

---—-------------------------------------

**Insight 8 : Greed favors high-risk strategies**
- Infrequent traders benefit most from trending markets

---—-------------------------------------

**Insight 9: Win rate is not the key driver**
- Lower win-rate traders achieve higher profitability

---—-------------------------------------

#  Part C : Actionable Output

—-------------------------------------

##  Strategy 1 : Regime-Based Trading

**Rule:**
- Greed -> fewer, high-conviction trades  
- Fear -> higher-frequency trading  

**Rationale:**
- Greed markets reward trend-following  
- Fear markets reward volatility exploitation  

—----------------------------------

##  Strategy 2 : Dynamic Position Sizing

**Rule:**
- Increase size in Fear  
- Reduce size in Greed  

**Rationale:**
- Fear = higher volatility  
- Greed = directional movement  

—----------------------------------

##  Strategy 3 : Risk-Reward Focus

**Rule:**
- Optimize payoff, not win rate  

**Rationale:**
- High-profit traders often have lower win rates  
- Large winning trades compensate for losses  

---—-------------------------------------

#  Predictive Model

—------------------------------------

##  Objective
Predict whether a trader’s daily PnL is positive

—--------------------------------------

##  Model
- Random Forest Classifier
- Features:
  - sentiment
  - win rate
  - trade frequency
  - average trade size

—--------------------------

##  Results

- Accuracy: **94%**
- Strong recall for profitable trades (0.98)

—------------------------------

##  Interpretation

- Trader behavior + sentiment contains predictive signal
- Model performs better at identifying profitable opportunities

—----------------------------------



# Final Conclusion

Market sentiment influences trader behavior, but performance is primarily driven by:

- trading strategy  
- risk management  
- payoff structure  





