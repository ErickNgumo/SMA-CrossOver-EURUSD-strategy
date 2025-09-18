# Simple Moving Average (SMA) Crossover Backtester

This project implements a simple **backtesting engine** for a Moving Average crossover strategy using **MetaTrader 5**, **Pandas**, and **NumPy**.  
It downloads historical price data directly from MetaTrader 5, applies an SMA 20/50 crossover strategy, and calculates basic performance metrics such as win rate.

---

## 📌 Strategy Logic

1. **Indicators**
   - SMA 20 (fast moving average)
   - SMA 50 (slow moving average)

2. **Trend Detection**
   - Bullish (`trend = 1`) when SMA 20 > SMA 50  
   - Bearish (`trend = -1`) when SMA 20 < SMA 50  

3. **Entry Signals**
   - `"buy"` when the trend shifts from bearish to bullish (`signal = 2`)
   - `"sell"` when the trend shifts from bullish to bearish (`signal = -2`)

4. **Exit Signals**
   - Exit a **buy** when trend flips bearish  
   - Exit a **sell** when trend flips bullish  

5. **Profit/Loss Calculation**
   - A trade is labeled `"profit"` if the exit price moves in favor of the entry direction
   - Otherwise, it is labeled `"loss"`

---

## 📊 Example Metrics Output

-Total Trades: 42
-Wins: 18
-Losses: 24
-Winrate: 42.85%

## 🛠️ Requirements
- Python 3.x  - 
- Pandas (optional, for working with real market data) 
- Metatrader5
- Jupyter Notebook (recommended)

Install dependencies:
```bash
pip install pandas jupyter metatrader5
