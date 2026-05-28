# DSA 210 Project - Analysis of Bitcoin's Relationship with Traditional Financial Assets

---

## 📌 Project Overview

This project investigates the relationship between **Bitcoin (BTC)** and traditional financial assets — the **S&P 500 Index** and **Gold Futures** — using data science and machine learning techniques. The central research question is:

> **Does Bitcoin behave more like a risk asset (similar to stocks) or a safe-haven asset (similar to gold)?**

By analyzing historical price data from January 2020 to March 2026, this study examines correlations, return distributions, volatility patterns, and predictive relationships between these three assets.

---

## 🎯 Motivation

Over the past decade, Bitcoin has emerged as a significant financial asset, attracting attention from investors, researchers, and policymakers. It has been characterized both as a high-risk speculative asset and as a potential store of value comparable to gold. However, there is still ongoing debate regarding its true role within financial markets.

This project aims to provide **data-driven insights** into:
- Whether Bitcoin behaves more like a **stock market asset** or a **safe-haven asset**
- How **stable or unstable** the correlations between Bitcoin and traditional assets are
- Whether traditional asset returns can **predict** Bitcoin's movements
- Whether Bitcoin can be considered a **diversification tool** in financial portfolios

---

## 📊 Dataset

| Feature | Details |
|---------|---------|
| **Source** | [Yahoo Finance](https://finance.yahoo.com/) via the `yfinance` Python API |
| **Assets** | Bitcoin (BTC-USD), S&P 500 (^GSPC), Gold Futures (GC=F) |
| **Period** | January 1, 2020 – March 31, 2026 |
| **Frequency** | Daily |
| **Observations** | ~2,280 trading days |
| **Key Variables** | Close prices, daily percentage returns, log returns |

### Data Enrichment
The raw price data was enriched with:
- **Daily percentage returns** and **log returns**
- **Rolling statistics** (moving averages, rolling standard deviations)
- **Lagged features** for machine learning (1-day, 3-day, 5-day lags)
- **Market regime labels** (bull/bear based on S&P 500 trends)

---

## 🔬 Methodology

The project follows a structured data science workflow:

### 1. Exploratory Data Analysis (EDA)
- Comprehensive statistical analysis of price and return distributions
- **15+ visualizations** including:
  - Price trends and normalized comparisons
  - Cumulative returns analysis
  - Return distribution analysis (histograms, box plots, violin plots, QQ plots)
  - Monthly returns heatmaps and seasonal patterns
  - Rolling volatility and drawdown analysis
  - Correlation analysis (static, rolling, regime-based)
  - Joint distribution plots and scatter analysis
- Statistical hypothesis testing:
  - **Shapiro-Wilk test** for normality
  - **Augmented Dickey-Fuller test** for stationarity
  - **Pearson & Spearman correlation** with significance tests
  - **Granger causality test** for predictive relationships

### 2. Machine Learning Analysis
- **Feature engineering** with lagged returns and rolling statistics
- **Four regression models** compared:
  1. **Linear Regression** — baseline linear model
  2. **Ridge Regression** — regularized linear model
  3. **Random Forest Regressor** — ensemble tree-based model
  4. **Gradient Boosting Regressor** — sequential ensemble model
- Time-series-aware train/test split (80/20, no shuffle)
- **Time-series cross-validation** (5-fold)
- Evaluation metrics: MSE, RMSE, MAE, R²
- Feature importance analysis
- Residual diagnostics

---

## 📈 Key Findings

1. **Bitcoin is highly volatile** — its daily return standard deviation is approximately 3x that of the S&P 500 and Gold, with significant non-normal (fat-tailed) distributions.

2. **Moderate correlation with S&P 500** — Bitcoin shows a moderate positive correlation (~0.3–0.4) with stock market returns, suggesting some risk-asset behavior.

3. **Weak correlation with Gold** — Bitcoin has a weak and unstable correlation with Gold, challenging the "digital gold" narrative.

4. **Time-varying relationships** — Rolling correlation analysis reveals that BTC-SP500 and BTC-Gold correlations shift significantly over time, especially during market stress events.

5. **Low predictability** — All four ML models achieve relatively low R² scores, confirming that traditional asset returns alone are insufficient to predict Bitcoin. The best-performing model explains only a modest fraction of BTC return variance.

6. **Feature importance insights** — Lagged SP500 returns and rolling volatility features show some predictive power, but Bitcoin's price dynamics are largely driven by crypto-specific factors.

7. **Unique asset class** — Bitcoin does not neatly fit into either the "risk asset" or "safe-haven" category. It behaves as a **distinct asset class** with its own unique market dynamics.

---

## 📁 Repository Structure

```
DSA210/
│
├── README.md                                    # Project documentation (this file)
├── requirements.txt                             # Python dependencies
├── DSA210 Project Proposal.pdf                  # Original project proposal
│
├── DSA210_BTC_Correlation_Analysis.ipynb         # Exploratory Data Analysis notebook
│   └── Comprehensive EDA with 15+ figures,
│       statistical tests, and correlation analysis
│
├── DSA210_BTC_ML_Analysis.ipynb                  # Machine Learning Analysis notebook
│   └── 4 ML models with comparison, feature
│       importance, cross-validation, and diagnostics
│
└── figures/                                      # Saved visualization outputs (if applicable)
```

---

## 🚀 How to Reproduce

### Option 1: Google Colab (Recommended)
1. Open the notebooks in [Google Colab](https://colab.research.google.com/)
2. Each notebook includes `!pip install` commands for required packages
3. Run all cells sequentially — data is downloaded automatically via `yfinance`

### Option 2: Local Environment
```bash
# Clone the repository
git clone https://github.com/<your-username>/DSA210.git
cd DSA210

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook
```

### Prerequisites
- Python 3.8 or higher
- Internet connection (for downloading financial data from Yahoo Finance)

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python 3** | Primary programming language |
| **pandas** | Data manipulation and analysis |
| **NumPy** | Numerical computations |
| **matplotlib** | Data visualization |
| **seaborn** | Statistical visualization |
| **yfinance** | Financial data retrieval from Yahoo Finance |
| **scikit-learn** | Machine learning models and evaluation |
| **SciPy** | Statistical hypothesis testing |
| **statsmodels** | Time-series analysis (ADF test, Granger causality) |
| **Google Colab** | Cloud-based notebook environment |

---

## ⚠️ Limitations & Future Work

### Limitations
- The analysis uses only **daily closing prices** — intraday patterns are not captured
- **Yahoo Finance data** may have occasional gaps or inconsistencies
- The ML models use only **two traditional asset returns** as features — many other factors (sentiment, volume, regulatory news, on-chain metrics) influence Bitcoin
- The analysis period (2020–2026) includes exceptional events (COVID-19, 2021 bull run, 2022 crypto winter) that may not be representative of long-term behavior

### Future Extensions
- Incorporate **sentiment analysis** from social media (Twitter/X, Reddit) and news
- Add **on-chain metrics** (hash rate, active addresses, exchange flows) as features
- Experiment with **deep learning models** (LSTM, Transformer) for time-series prediction
- Include additional assets (Ethereum, bonds, real estate indices) for broader comparison
- Perform **regime-switching models** (e.g., Markov switching) to formally identify market regimes
- Extend the analysis to **portfolio optimization** (efficient frontier with Bitcoin)

---

## 📚 References

- Yahoo Finance API: https://finance.yahoo.com/
- Bitcoin historical data: BTC-USD on Yahoo Finance
- S&P 500 Index: ^GSPC on Yahoo Finance
- Gold Futures: GC=F on Yahoo Finance
- scikit-learn documentation: https://scikit-learn.org/
