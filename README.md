# Trader Performance vs Market Sentiment Analysis

## Project Overview

This project analyzes the relationship between Bitcoin market sentiment (Fear vs Greed) and trader behavior/performance on the Hyperliquid trading platform.

The goal is to identify whether market sentiment impacts:
- Trader profitability
- Trading frequency
- Leverage usage
- Position sizing
- Long/Short behavior

The project also explores trader segmentation and provides actionable strategy recommendations based on observed behavioral patterns.

---

# Objectives

The analysis aims to answer the following questions:

1. Does trader performance differ between Fear and Greed market conditions?
2. Do traders change their behavior depending on market sentiment?
3. Which trader segments perform better under different sentiment conditions?
4. What actionable trading insights can be derived from the data?

---

# Datasets Used

## 1. Bitcoin Market Sentiment Dataset

Contains daily Bitcoin market sentiment classification.

### Columns
- Date
- Classification (Fear / Greed)

### Purpose
Used to classify trading activity according to overall market sentiment.

---

## 2. Historical Trader Dataset (Hyperliquid)

Contains historical trading activity from Hyperliquid traders.

### Important Columns
- account
- symbol
- execution price
- size
- side
- time
- start position
- leverage
- closedPnL

### Purpose
Used to analyze:
- Trader profitability
- Trading behavior
- Leverage usage
- Trading frequency

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook / Google Colab

---

# Project Structure

```text
trader-sentiment-analysis/
│
├── data/
│   ├── fear_greed.csv
│   └── historical_data.csv
│
├── notebook/
│   └── analysis.ipynb
│
├── outputs/
│   ├── charts/
│   └── tables/
│
├── README.md
└── requirements.txt
```

---

# Installation & Setup

## Step 1 — Clone Repository

```bash
git clone https://github.com/yourusername/trader-sentiment-analysis.git
```

---

## Step 2 — Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

---

## Step 3 — Launch Notebook

```bash
jupyter notebook
```

Open:
```text
analysis.ipynb
```

---

# Methodology

The project was completed in multiple stages:

---

## 1. Data Loading

Both datasets were loaded using Pandas.

```python
pd.read_csv()
```

---

## 2. Data Cleaning

The following preprocessing steps were performed:
- Checked dataset dimensions
- Identified missing values
- Removed duplicates
- Converted timestamps into datetime format
- Standardized date columns

---

## 3. Dataset Alignment

Trading data and sentiment data were merged using daily date alignment.

### Merge Logic
- Trade timestamps converted to daily format
- Sentiment dataset mapped by date
- Left join used to preserve all trading records

---

## 4. Feature Engineering

Several analytical metrics were created.

### Features Created

#### Daily Trader PnL
Measures trader profitability per day.

#### Win Rate
Calculated as:
```text
Winning Trades / Total Trades
```

#### Trade Frequency
Number of trades executed per day.

#### Average Trade Size
Average position size per trader.

#### Long/Short Ratio
Measures directional bias.

#### Leverage Segmentation
Traders grouped into:
- High leverage
- Low leverage

#### Frequency Segmentation
Traders grouped into:
- Frequent traders
- Infrequent traders

#### Consistency Segmentation
Based on PnL standard deviation.

---

# Exploratory Data Analysis (EDA)

The following analyses were performed:

## Market Sentiment Distribution
- Fear days
- Greed days

## PnL Distribution
Compared profitability under different sentiment conditions.

## Trade Frequency Analysis
Measured changes in trading activity.

## Leverage Distribution
Analyzed leverage behavior during Fear and Greed periods.

## Long vs Short Analysis
Examined directional trading bias.

---

# Key Metrics Analyzed

| Metric | Description |
|---|---|
| closedPnL | Profit/Loss per trade |
| Win Rate | Percentage of profitable trades |
| Trade Count | Number of trades executed |
| Average Trade Size | Mean trade size |
| Leverage | Trader leverage usage |
| Long/Short Ratio | Directional preference |

---

# Trader Segmentation

## 1. High vs Low Leverage Traders

Purpose:
- Compare risk-taking behavior
- Compare profitability patterns

Criteria:
- High leverage: leverage >= 10
- Low leverage: leverage < 10

---

## 2. Frequent vs Infrequent Traders

Purpose:
- Understand behavioral differences

Criteria:
- Based on median trade frequency

---

## 3. Consistent vs Inconsistent Traders

Purpose:
- Identify stable traders

Criteria:
- Based on standard deviation of trader PnL

---

# Visualizations Included

The project contains multiple charts including:

1. PnL Distribution (Fear vs Greed)
2. Trade Frequency by Sentiment
3. Leverage Distribution Histogram
4. Long vs Short Behavior
5. Segment Performance Comparison

---

# Key Insights

## Insight 1
Greed periods generally showed:
- Higher trade frequency
- Larger position sizes
- Increased leverage usage

This indicates increased trader confidence and risk appetite during bullish market sentiment.

---

## Insight 2
High leverage traders achieved larger profits during Greed periods but experienced significantly higher downside volatility during Fear periods.

This suggests that aggressive leverage strategies become highly sensitive to market sentiment changes.

---

## Insight 3
Frequent traders maintained more stable win rates compared to infrequent traders across different market conditions.

This may indicate better adaptability and stronger execution consistency.

---

# Strategy Recommendations

## Recommendation 1
Reduce leverage exposure during Fear periods, especially for traders with historically unstable profitability.

Reason:
- Fear periods showed higher downside volatility and lower win consistency.

---

## Recommendation 2
Momentum-oriented strategies may perform better during Greed periods where trade frequency and position sizing increase significantly.

Reason:
- Bullish sentiment appears to encourage stronger trend-following behavior.

---

# Optional Enhancements

The following optional improvements can be added:

- Machine Learning prediction model
- Streamlit dashboard
- Advanced clustering analysis
- Sharpe ratio calculations
- Drawdown analysis
- Time-series forecasting

---

# Challenges Faced

Some challenges encountered during the project:
- Aligning datasets with different timestamp formats
- Handling skewed PnL distributions
- Segmenting traders meaningfully
- Extracting actionable insights instead of only descriptive statistics

---

# Conclusion

This analysis demonstrates that market sentiment significantly influences trader behavior and risk-taking patterns.

Key findings indicate:
- Greed periods encourage aggressive trading behavior
- Fear periods reduce position sizing and profitability consistency
- Trader segmentation reveals substantial differences in risk-adjusted performance

The project highlights how sentiment-aware trading analysis can support better decision-making and risk management.

---

# Future Improvements

Future extensions may include:
- Real-time sentiment integration
- Predictive profitability models
- Portfolio-level analysis
- Risk-adjusted return optimization
- Automated trading signal generation

---

# Author

Sangeetha Dayalan
Data Science / Analytics Internship Assignment
