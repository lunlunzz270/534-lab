# Magnificent 7 & Market Concentration Bubble Tracker

An interactive quantitative finance dashboard tracking U.S. mega-cap equity concentration, Equity Risk Premium (ERP), equity duration sensitivity, and market fragility.

**Live GitHub Pages Demo**: [https://lunlunzz270.github.io/534-lab/](https://lunlunzz270.github.io/534-lab/)

---

## 📌 Executive Summary & Key Financial Insights

The U.S. stock market is experiencing its **highest concentration level in over 100 years**:
- **36.0% of the S&P 500** is dominated by just seven companies (Apple, Microsoft, NVIDIA, Alphabet, Amazon, Meta, and Tesla), surpassing the 2000 Dot-Com Bubble (26.8%) and the 1970 Nifty Fifty era (24.5%).
- **Market Breadth Divergence**: S&P 500 Cap-Weighted (SPY) has outpaced S&P 500 Equal-Weighted (RSP) by over **1,030 basis points**, signaling that headline index performance masks underlying broad-market stagnation.
- **Equity Risk Premium (ERP)**: Currently sitting near **0.82%** (a 20-year low), indicating that investors receive historically thin compensation for holding volatile equities instead of risk-free 10-Year U.S. Treasuries.
- **Equity Duration**: Mega-cap growth stocks have an effective equity duration of **~28 years**, making their valuation multiples hyper-sensitive to changes in benchmark yields.

---

## 🛠️ Dashboard Architecture & Modules

The application is deployed as a single-page quantitative terminal:

1. **Concentration Overview**: SPY vs RSP historical divergence, S&P 500 market cap donut breakdown, and historical bubble comparison matrix.
2. **Mag 7 Deep Dive**: Stock-by-stock valuation radar, bubble matrix (Forward P/E vs Expected Growth vs Market Cap), and financial multiples table.
3. **Valuation & Equity Risk Premium**: Historical ERP time series with danger zone thresholds and Top 7 market share growth trajectory.
4. **Interest Rate Sensitivity & DCF**: Interactive live slider allowing users to shift benchmark yields and earnings expectations to see real-time price impacts via equity duration math ($\Delta P / P \approx -D \cdot \Delta y + \Delta g$).
5. **Monte Carlo Simulation**: 12-month Ornstein-Uhlenbeck (Vasicek) mean-reverting simulation of market concentration (3,000 forward paths, fan chart, and 95% Value-at-Risk comparison between Mag 7 and RSP).
6. **Methodology & Financial Glossary**: Core concepts and educational annotations for students and researchers.

---

## 🚀 Local Development & Quickstart

### Option 1: Open Directly
Double-click `index.html` in any browser. It contains an integrated offline fallback dataset, ensuring complete functionality even without internet access or local servers.

### Option 2: Run via Local Web Server
```bash
python3 -m http.server 8000
# Open http://localhost:8000 in your browser
```

### Option 3: Refresh Market Data Pipeline
```bash
# Optional: install dependencies
pip install -r requirements.txt

# Run the data updater to refresh data.json
python3 update_data.py
```

---

## ⚙️ Automated GitHub Actions Workflow
The repository includes `.github/workflows/update-data.yml`, which runs on weekdays after U.S. market close (22:00 UTC) to refresh `data.json` and keep the GitHub Pages live deployment updated.

---

## 📚 Academic Context
Developed for **FinTech 534 (Financial Technology)** lab assignment. Designed for academic research and educational exploration.