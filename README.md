# Trader Performance vs Market Sentiment

## Overview
This project analyzes how market sentiment (Fear vs Greed) impacts trader behavior and performance on Hyperliquid.

The goal is to uncover patterns that can inform **smarter trading strategies** by combining:
- Bitcoin Fear & Greed Index
- Historical trader execution data

---

## Datasets

1. **Bitcoin Market Sentiment (Fear/Greed)**
   - Columns: timestamp, value, classification, date  
   - Labels: Fear, Extreme Fear, Neutral, Greed, Extreme Greed  

2. **Hyperliquid Trader Data**
   - Fields: account, coin, execution price, size, side, timestamp, closed pnl, etc.  
   - ~211,000+ trade records  

---

## Setup

Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
