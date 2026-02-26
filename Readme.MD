# Bitcoin Sentiment Analysis

Analyzing how the Crypto Fear & Greed Index influences trader performance on Hyperliquid.

---

## Project Structure
```
bitcoin_sentiment_analysis/
├── data/
│   ├── fear_greed_index.csv
│   └── historical_data.csv
├── outputs/
│   └── sentiment_analysis_charts.png
├── bitcoin_sentiment_analysis.ipynb
├── README.md
└── WRITEUP.md
```

---

## Datasets

| File | Rows | Description |
|------|------|-------------|
| `fear_greed_index.csv` | 2,644 | Daily Fear & Greed Index with classification |
| `historical_data.csv` | 211,224 | Raw trade records from 32 Hyperliquid traders |

---

## Setup

### Requirements
- Python 3.8+
- pandas, numpy, matplotlib, seaborn, jupyter

### Install dependencies
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

---

## How to Run

### 1. Clone the repository
```bash
git clone https://github.com/your-username/bitcoin_sentiment_analysis.git
cd bitcoin_sentiment_analysis
```

### 2. Add your data files
Place both CSV files inside the `data/` folder:
```
data/fear_greed_index.csv
data/historical_data.csv
```

### 3. Create outputs folder
```bash
mkdir -p outputs
```

### 4. Launch the notebook
```bash
jupyter notebook bitcoin_sentiment_analysis.ipynb
```
Run all cells via **Kernel → Restart & Run All**

---

## What the Notebook Does

| Section | Description |
|---------|-------------|
| 1. Data Loading | Loads both CSVs, checks shape, nulls, duplicates |
| 2. Feature Engineering | Parses dates, builds daily per-trader metrics, L/S ratio |
| 3. Sentiment Merge | Aggregates market-level stats and joins with sentiment labels |
| 4. Analysis | Performance by sentiment, trader behavior, trader segmentation |
| 5. Visualizations | 6-panel chart dashboard saved to `outputs/` |

---

## Output Charts

The notebook generates a 6-panel dashboard saved as `outputs/sentiment_analysis_charts.png`:

- Avg PnL by Sentiment
- Avg Win Rate by Sentiment
- Avg Daily Trades by Sentiment
- PnL Distribution: Fear vs Greed (boxplot)
- Avg PnL: Frequent vs Infrequent Traders
- Trader Types (pie chart)

---

## Key Findings

- **Fear days** produced ~8× higher collective PnL than Greed days
- Traders placed **9 long orders per short** during Fear — and still profited
- **78%** of profitable traders are "Lucky Winners" (positive PnL but sub-50% win rate)
- **Frequent traders** earned 3× more on average than infrequent traders

---

## Limitations

Only **6 trading dates** overlap between the two datasets. All findings are directional signals — not statistically conclusive. Wider date coverage would strengthen every conclusion.

---


