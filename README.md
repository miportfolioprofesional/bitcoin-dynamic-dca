# Bitcoin Dynamic DCA: A Data-Driven Accumulation Strategy

**A real-world project developed for an academic Bitcoin accumulation challenge.**
This repository contains the complete analysis, model development, backtesting process, and final reports of a project developed for a client.

---

## 🧠 What problem does this solve?

Many long-term Bitcoin investors use **Dollar Cost Averaging (DCA)** to reduce timing risk.

However, traditional DCA treats every day equally — investing USD 100 on Monday and USD 100 on Friday, regardless of whether Bitcoin is trading at USD 20,000 or USD 60,000.

**The real question:**
Can we improve DCA by investing more during periods of undervaluation and less during periods of overvaluation?

**The challenge:**

* Traditional on-chain metrics (hash rate, active addresses, transaction count) **do not predict short-term returns** (R² < 0.2%).
* Predictive signals do exist, but they are **subtle and regime-dependent**.
* Many "simple rules" (e.g., buying when price < MA200) **have significant detection lag** and fail to consistently outperform DCA.

**What this project delivers:**
A **rigorous and reproducible framework** for testing any accumulation hypothesis against a real benchmark — uniform DCA — with comprehensive backtesting, win-rate analysis, and statistical honesty (including negative results).

---

## 📊 What you'll find here

| File / Folder             | Description                                                                              |
| ------------------------- | ---------------------------------------------------------------------------------------- |
| `model_integration.ipynb` | Main notebook: data loading, feature engineering, sequential allocation, and backtesting |
| `outputs/`                | CSV files containing backtest results, signals, allocations, and regime distributions    |
| `Final Report.docx`       | Complete final report (paper format, aligned with the blog)                              |
| `Presupuesto...docx`      | Original project proposal (transparency regarding scope and costs)                       |

---

## 🔍 Key Findings

### 1. On-chain metrics are coincident, not predictive

Hash rate, active addresses, transaction count, and volume show **correlations below 0.04** with 30-day forward returns.

They describe the *present*, not the future.

### 2. Volatility is persistent and regime-dependent

The ACF of squared returns decays slowly over 20–30 lags (ARCH effects).

30-day rolling volatility clusters around major market cycles (2013, 2017, 2020, 2022).

**Predictive signals behave differently depending on the volatility regime (low/medium/high).**

### 3. Polymarket signals have predictive power — although modest

Political and macroeconomic probabilities Granger-cause Bitcoin returns (p < 0.01 and p < 0.05).

Crypto-specific signals are marginal (p ≈ 0.09).

**Correlations become stronger during medium-volatility regimes** (political: 0.136 vs. -0.013 during low volatility).

### 4. The Jump Model (price < MA200) fails due to detection lag

A simple contrarian rule ("bear market = buy more") allocated 13% more capital during market downturns. However, **the delay in detecting regime changes** caused the model to buy near the bottom, missing the best discount opportunities.

**Result:** -0.27% difference vs. DCA, with a 12% win rate.

### 5. Negative results also have scientific value

Not every hypothesis works.

This analysis **honestly documents what did not work**, avoiding the overfitting of false narratives.

For the 2019–2026 period, uniform DCA proved surprisingly difficult to outperform using this set of signals.

---

## 🛠️ Technical Stack

* **Python** (pandas, numpy, polars, matplotlib, seaborn, statsmodels)
* **Jupyter Notebook** (model integration, EDA)
* **GitHub** (version control and portfolio-ready documentation)

---

## 📈 What does this mean for you as a client?

If you need someone who can:

* Turn a **vague business problem** into a **testable quantitative framework**
* Work with **real-world, messy data** (Polymarket parquet files, CoinMetrics CSVs, manual merges)
* Build **backtesting engines** that respect no-look-ahead constraints, budget limitations, and rolling windows
* Document **both successful and unsuccessful approaches** with intellectual honesty
* Communicate results to **technical and non-technical audiences** through executive summaries, presentations, and final reports

…**this is the kind of work I deliver.**

---

## 📁 Repository Structure
