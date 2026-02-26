Project Overview
This project investigates whether daily crypto market sentiment (Fear, Greed, Neutral) meaningfully influences the trading performance and behaviour of on-chain traders on the Hyperliquid perpetuals exchange.
bitcoin_sentiment_analysis/
├── data/
│   ├── fear_greed_index.csv       # Daily Fear & Greed Index (2,644 rows)
│   └── historical_data.csv        # Hyperliquid trade records (211,224 rows)
├── outputs/
│   └── sentiment_analysis_charts.png   # Auto-generated visualisation
├── bitcoin_sentiment_analysis.ipynb    # Main analysis notebook
├── README.md
└── WRITEUP.md                          # Methodology, insights & recommendations

Install all dependencies:(in bash):
    pip install pandas numpy matplotlib seaborn jupyter
    How to Run
1. Clone / download the project
bash git clone https://github.com/your-username/trader_sentiment_analysis.git
cd trader_sentiment_analysis
2. Place your data files
Ensure both CSV files are in the data/ folder:
data/fear_greed_index.csv
data/historical_data.csv
Create the outputs folder if it doesn't exist:
bashmkdir -p outputs
3. Launch the notebook
bashjupyter notebook traderOutputs
After running, you will find:


Console tables — Avg PnL, win rate, trade count, L/S ratio broken down by sentiment label
Trader profile table — Segmentation by frequency and profitability type
outputs/sentiment_analysis_charts.png — 6-panel visualisation dashboard_sentiment_analysis.ipynb
Then run all cells via Kernel → Restart & Run All.
Notes

Only 6 trade-dates overlap between the two datasets — a key limitation. Wider date coverage would strengthen all conclusions.
L/S ratio is computed as BUY count / max(SELL count, 1) to avoid division by zero.
Trader types: Consistent Winner (positive PnL + win-rate ≥ 50%), Lucky Winner (positive PnL + win-rate < 50%), Loser (negative PnL).

