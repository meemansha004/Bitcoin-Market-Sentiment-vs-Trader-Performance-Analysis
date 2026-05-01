# Bitcoin Market Sentiment vs Trader Performance Analysis

## Problem Statement

This project analyzes the relationship between Bitcoin market sentiment and trader performance using historical trading data from Hyperliquid and the Bitcoin Fear & Greed Index.

The objective is to identify how market sentiment influences trader profitability, trading activity, trade sizing, and buy/sell behavior in order to uncover patterns that can support smarter trading strategies.

---

## Objective

The analysis focuses on answering the following questions:

1. Does trader profitability change under different market sentiment conditions?
2. Is trader win rate higher during Fear or Greed?
3. How do Buy and Sell trades perform under different sentiment phases?
4. Does trade size vary across market sentiment conditions?
5. Are traders more active during Fear or Greed?

---

## Datasets Used

### 1. Bitcoin Fear & Greed Index Dataset

This dataset provides daily market sentiment classifications based on market psychology.

**Columns:**
- `timestamp`
- `value`
- `classification`
- `date`

**Sentiment Categories:**
- Extreme Fear
- Fear
- Neutral
- Greed
- Extreme Greed

---

### 2. Historical Trader Data (Hyperliquid)

This dataset contains historical trade execution records from traders.

**Columns:**
- `Account`
- `Coin`
- `Execution Price`
- `Size Tokens`
- `Size USD`
- `Side`
- `Timestamp IST`
- `Start Position`
- `Direction`
- `Closed PnL`
- `Transaction Hash`
- `Order ID`
- `Crossed`
- `Fee`
- `Trade ID`
- `Timestamp`

---

## Methodology

### Step 1: Data Loading
Both datasets were loaded into pandas DataFrames.

### Step 2: Data Cleaning
- Converted timestamp columns into datetime format
- Extracted date values for merging
- Standardized date formats

### Step 3: Data Merging
Merged trader data with market sentiment data using the date column.

### Step 4: Feature Engineering
Created new analysis features such as:
- Profitability flag (`is_profit`)
- Sentiment-linked trade records

### Step 5: Exploratory Data Analysis (EDA)
Performed multiple analyses to identify trading behavior patterns across sentiment phases.

---

## Analysis Performed

### 1. Average Closed PnL by Sentiment
Measured trader profitability under different market sentiment conditions.

### 2. Win Rate by Sentiment
Measured percentage of profitable trades.

### 3. Buy vs Sell Performance Analysis
Compared profitability of buy and sell trades across sentiment categories.

### 4. Average Trade Size by Sentiment
Measured how aggressively traders position themselves under different market conditions.

### 5. Trade Frequency Analysis
Measured trading activity across sentiment categories.

### 6. Profit Distribution Analysis
Used boxplots to analyze profit consistency, outliers, and risk distribution.

---

## Visualizations Included

The notebook contains the following visualizations:

- Average Closed PnL by Market Sentiment
- Win Rate by Market Sentiment
- Buy vs Sell Average PnL by Market Sentiment
- Average Trade Size by Market Sentiment
- Number of Trades by Market Sentiment
- PnL Distribution by Market Sentiment

---

## Key Findings

### 1. Extreme Greed showed the highest average profitability
Average Closed PnL was highest during Extreme Greed, indicating strong profit opportunities during bullish market sentiment.

### 2. Win rate was highest during Extreme Greed
Trader success rate was highest during Extreme Greed, supporting profitability consistency.

### 3. Contrarian trading behavior showed stronger results
- Buying during Fear generated stronger buy-side profitability.
- Selling during Extreme Greed generated the highest sell-side profitability.

This suggests that contrarian strategies may outperform momentum-following strategies.

### 4. Fear triggered larger trade sizes
Average trade size was highest during Fear conditions, indicating stronger capital deployment during market uncertainty.

### 5. Trading activity was highest during Fear
Trade volume peaked during Fear phases, suggesting increased trader participation during volatile conditions.

### 6. Profit distributions were highly skewed
A small number of high-profit trades significantly impacted average profitability, highlighting the importance of win rate and risk analysis.

---

## Strategic Insights

Based on the analysis:

- Buying during Fear appears to offer strong upside opportunities.
- Selling during Extreme Greed appears to provide strong profit-taking opportunities.
- Market sentiment can be used as an effective signal for timing trade entries and exits.
- Risk management should be strengthened during Greed phases due to larger downside outliers.

---

## Tech Stack

- Python
- Pandas
- Matplotlib
- Seaborn
- OpenPyXL
- Jupyter Notebook (VS Code)

---

## Project Structure

```text
PRIMETRADE.AI TASK/
│── Data/
│   ├── historical_data.csv
│   ├── fear_greed_index.xlsx
│── analysis.ipynb
│── README.md
│── requirements.txt
```

---

## Installation

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

## Required Libraries

The project uses the following Python libraries:

```text
pandas
matplotlib
seaborn
openpyxl
scipy
```

---

## How to Run

1. Clone or download the project.
2. Install dependencies.
3. Open the notebook.

Run:

```bash
jupyter notebook
```

Then open:

```text
analysis.ipynb
```

Execute all cells in sequence.

---

## Conclusion

The analysis shows that market sentiment significantly affects trader behavior, profitability, and participation.

The findings suggest that sentiment-aware trading strategies, especially contrarian strategies such as buying during Fear and selling during Extreme Greed, may improve trading performance.

This project demonstrates how combining market sentiment data with trader execution data can uncover meaningful behavioral and profitability patterns in crypto trading.