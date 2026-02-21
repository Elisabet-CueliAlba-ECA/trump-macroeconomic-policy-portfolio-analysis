# Quantitative Active Portfolio Management: Navigating the 2025 "Liberation Day" Tariff Shock

## Executive Summary & Macroeconomic Context
The implementation of the sweeping reciprocal tariff policies by the Donald Trump administration in April 2025 (often referred to as the "Liberation Day tariffs") introduced an unprecedented macroeconomic shock to the global economy. In such highly disruptive environments characterized by supply chain relocation, geopolitical fragmentation, and inflation resurgence, **passive indexing fails to protect capital efficiently**. 

This project demonstrates that extreme market anomalies require rigorous **active portfolio management**. By leveraging Python for quantitative financial modeling, this repository presents a tactically allocated portfolio designed to beat the market benchmark (MSCI ACWI). The strategy systematically hedges against tariff-induced inflation and geopolitical risks while maintaining a calculated exposure to the secular growth of Artificial Intelligence (AI).

To rigorously validate this tactical allocation, the project implements a comprehensive quantitative framework. The analysis encompasses **benchmark regressions** (Beta vs. MSCI ACWI), a **custom-weighted Global Fama & French factor model**, and sectoral sensitivity mapping. Strategy resilience is further evaluated through **regime-specific historical backtesting** (analyzing ex-ante vs. ex-post returns during recent bear and bull markets) and a **100,000-trajectory Monte Carlo simulation** to quantify forward-looking tail risks (VaR & CVaR).

## Asset Selection & Strategic Allocation
The portfolio is  divided into a **Defensive Core (87%)** for capital preservation and a **Tactical Satellite (13%)** to capture asymmetric upside in emerging markets and technology.

### Protection & Hedging (87%)
* **ITA (20%) - iShares U.S. Aerospace & Defense:** Strategic positioning to capitalize on increased global military spending (e.g., US pressure on NATO members to reach 5% of GDP).
* **XLV (20%) - Health Care Select Sector SPDR:** Historically low-beta sector providing resilient, non-cyclical demand during market downturns.
* **GLD (20%) - SPDR Gold Trust:** The ultimate traditional safe-haven asset, currently at historical peaks, hedging against fiat volatility.
* **TIP (17%) - iShares TIPS Bond ETF:** Direct hedge against unexpected inflationary pressures caused by supply chain disruptions and political pressures on the Federal Reserve.
* **XLP (10%) - Consumer Staples Select Sector SPDR:** Basic consumer goods providing stability against economic cycles.

### Opportunity & AI Exposure (13%)
* **MCHI (5%) - iShares MSCI China ETF:** Capturing baseline growth despite tariff deceleration.
* **INDA (3%) - iShares MSCI India ETF:** Strategic bet on supply chain des-localization and the "Indian alternative" to Chinese manufacturing.
* **TSM (3%) & AVGO (2%) - TSMC and Broadcom:** Undisputed global leaders in semiconductor manufacturing and fabless design. Crucial for the ongoing AI infrastructure build-out, selected over raw materials due to the latter's extreme short-term volatility.

## Quantitative Methodology & Code Structure

### 1. Benchmark Regression (MSCI ACWI)
To establish the portfolio's baseline risk profile, an Ordinary Least Squares (OLS) regression was performed against the MSCI All Country World Index (ACWI).
* **Finding:** The portfolio exhibits a highly significant **Beta of 0.7475** (Adj. R² = 0.855), confirming its defensive, low-volatility nature compared to the global equity market.

### 2. Custom Global Fama & French Factor Analysis
Since standard Fama & French factors do not perfectly align with a globally diversified portfolio, a **custom weighted global factor model** was engineered. Using the MSCI ACWI IMI geographic breakdown (as of Dec 2024), US, Developed ex-US, and Emerging Market factors were aggregated via a weighted average.
* **Finding:** The Market Risk Premium (Mkt-RF) remains the only statistically significant factor (Adj. R² = 0.719), indicating the portfolio's returns are fundamentally driven by the global equity risk premium rather than standard size (SMB) or value (HML) anomalies.

### 3. Sectoral Factor Exposure
A multiple regression against 12 industry portfolios was executed to isolate specific sector sensitivities.
* **Finding:** The model confirmed statistically significant exposures to Manufacturing (`Manuf`), Business Equipment (`BusEq`), and Healthcare (`Hlth`), perfectly validating the initial theoretical allocation (Adj. R² = 0.815).

### 4. Stress Testing & Historical Backtesting
The active strategy was backtested across two distinct recent macroeconomic regimes to evaluate ex-post vs. ex-ante returns:
* **Bear Market (2022):** The portfolio demonstrated superior downside protection, returning **-26.24%** compared to the benchmark's massive **-39.89%** drawdown.
* **Bull Market (2024):** Despite its defensive nature, the portfolio successfully captured the upside, returning **24.96%** and beating the ACWI benchmark (**21.73%**).

### 5. Monte Carlo Risk Simulation
To assess future tail risks, **100,000 simulated trajectories** were generated using Monte Carlo methods.
* **Finding:** The simulation yielded a mean annualized return of approximately 0.0146%. More importantly, the risk metrics highlighted substantial volatility: the **Value at Risk (VaR) at 95% confidence was -0.26**, with an annualized **Conditional VaR (CVaR) of -0.322**, reinforcing the necessity of the heavy defensive weighting in the current high-uncertainty environment.

## Technical Implementation
* **Language:** `Python 3.x`
* **Core Libraries:** `Pandas` (Data wrangling), `NumPy` (Stochastic simulations), `Statsmodels` (OLS Regressions), `Matplotlib` / `Seaborn` (Data visualization), `yfinance` (Data ingestion).
* **Techniques Demonstrated:** Time-series analysis, Beta calculation, Custom weighted factor modeling, Monte Carlo simulation, Risk metric quantification (VaR & CVaR).

---
*Developed by **Elisabet Cueli Alba** — BSc Economics and Finance (UAM) | Specializing in Quantitative Finance & Data Analytics.*
