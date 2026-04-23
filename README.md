# DSA210 Project – Bitcoin Correlation Analysis

Analyzing the relationship between Bitcoin, the S&P 500, and Gold using data-driven techniques.

## Overview

This project explores the relationship between Bitcoin (BTC), the S&P 500 index, and Gold. Over the past decade, Bitcoin has been discussed both as a high-risk speculative asset and as a potential store of value, similar to gold. This study aims to examine these claims using data-driven analysis.

The primary objective is to understand whether Bitcoin behaves more like a traditional risk asset (such as equities) or a safe-haven asset (such as gold), and how this behavior changes over time.

---

## Motivation

With the increasing integration of cryptocurrencies into global financial markets, understanding Bitcoin’s role has become important for investors, researchers, and policymakers. By comparing Bitcoin with established financial benchmarks like the S&P 500 and Gold, this project seeks to provide insights into its economic behavior.

As a student interested in both data science and financial markets, this project also serves as an opportunity to apply data analysis techniques to a real-world problem.

---

## Research Questions

This project will focus on the following key questions:

* Does Bitcoin show stronger correlation with the S&P 500 or with Gold?
* How does the correlation between Bitcoin and these assets change over time?
* Can Bitcoin be considered a hedge or diversification asset in financial markets?

---

## Data Sources

The data for this project will be obtained from publicly available financial sources using Python-based financial APIs, specifically Yahoo Finance via the yfinance library.

The dataset will include:

Bitcoin price data (BTC-USD)
S&P 500 index data (^GSPC)
Gold price data (GC=F or XAU/USD)

The analysis will utilize historical daily price data spanning the period from January 1, 2020, to March 31, 2026. This time range is selected to capture multiple market conditions, including post-pandemic recovery, inflationary periods, and shifts in global economic sentiment.

The estimated sample size is approximately 1,500–1,600 daily observations for each asset before preprocessing. After aligning the datasets by date and removing missing values, the final dataset is expected to contain approximately 1,400–1,500 observations.

---

## Methodology

The project will follow a structured data science workflow:

1. **Data Collection**

   * Retrieve historical price data for all assets using Python-based financial APIs
   * Visual inspection of price trends may be supported using platforms such as TradingView to better understand market behavior

2. **Data Preparation**

   * Clean and align datasets
   * Compute daily returns

3. **Exploratory Data Analysis (EDA)**

   * Visualize price trends
   * Analyze return distributions

4. **Statistical Analysis**

   * Compute correlation coefficients
   * Analyze rolling correlations over time

5. **Further Analysis (Planned)**

   * Investigate behavior during major market events
   * Apply basic machine learning models (if applicable)

  
All quantitative analysis and data processing will be conducted using Python to ensure reproducibility and consistency.

---

## Project Structure

The repository is organized as follows:

* `data/` – raw and processed datasets
* `notebooks/` – Jupyter notebooks for analysis and visualization
* `src/` – Python scripts for data processing and analysis
* `requirements.txt` – list of Python dependencies

---

## Tools and Technologies

* Python
* pandas, numpy
* matplotlib, seaborn
* yfinance

---

## Current Status

This repository has been created as part of **Phase 1** of the DSA210 project. Initial structure and planning have been completed. Data collection and analysis will be implemented in subsequent phases.

---

## Reproducibility

To reproduce this project:

1. Install the required dependencies:

   ```
   pip install -r requirements.txt
   ```

2. Run the scripts or notebooks in the repository.

Further instructions will be added as the project progresses.

---
