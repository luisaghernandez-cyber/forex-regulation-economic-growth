# forex-regulation-economic-growth
Python-based analysis on the relationship between FX market regulation and long-term economic growth in emerging economies. Includes data exploration, visualizations, regression models, and Google Colab notebooks.
# Forex Regulation & Economic Growth — Python Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/luisaghernandez-cyber/forex-regulation-economic-growth/blob/main/notebooks/forex_regulation_analysis.ipynb)

This repository contains a Python-based empirical analysis exploring the relationship between foreign exchange (FX) market activity, macroeconomic conditions, and long-term economic growth in emerging economies, with a focus on **Colombia**.  
It includes real data sourced directly from the **World Bank API**, full preprocessing steps, time-series visualizations, and an econometric regression model.

The objective is to develop a simple but replicable analytical framework that can later be extended to evaluate the impact of **FX regulation** in emerging markets.

---
 **Project Overview**

Foreign exchange markets play a critical role in economic development, especially in emerging economies where financial openness, capital flows, and regulatory structures strongly influence macroeconomic stability.

This project examines:

- GDP growth (% annual)
- Inflation (% annual)
- Foreign Direct Investment (FDI) as % of GDP  
- FX market activity (approximated using remittances as % of GDP—an academically supported proxy)

The goal is to assess how these variables interact over time and how they might be used to understand the impact of FX market regulations.

---
 **Why This Matters**

FX regulation can influence:

- Capital mobility  
- Exchange rate stability  
- Market liquidity  
- Investor confidence  
- Long-term growth potential  

A lightweight but accurate empirical approach helps reveal baseline correlations before building more complex causal models (e.g., panel data, IV, GMM, structural models).

---
 **Data Sources**

All macroeconomic data is pulled directly from **World Bank Open Data API**:

| Variable | Source | Indicator Code |
|---------|--------|----------------|
| GDP growth (% annual) | World Bank | `NY.GDP.MKTP.KD.ZG` |
| Inflation (% annual) | World Bank | `FP.CPI.TOTL.ZG` |
| FDI (% of GDP) | World Bank | `BX.KLT.DINV.WD.GD.ZS` |
| Remittances (% of GDP) – FX proxy | World Bank | `BX.TRF.PWKR.DT.GD.ZS` |

Why remittances?  
They are commonly used as a **proxy for FX market activity** in emerging economies (high remittance flows imply higher foreign currency conversion volumes).

---
 **Methodology**

 **1. Data Extraction**
All variables are extracted directly via API using the `requests` library:
```python
response = requests.get(url).json()
data = pd.DataFrame(response[1])

**2.Cleaning & Formatting**

The dataset is prepared through the following steps:

- Convert years to integers  
- Drop missing values  
- Sort time series chronologically  
- Merge datasets using an inner join on `year`  

---

## **3. Visualization**

The notebook includes time-series plots for:

- GDP growth  
- Inflation  
- FDI inflows  
- FX activity proxy  

These visualizations help detect trends, volatility patterns, and macroeconomic cycles.

---

## **4. Econometric Model**

A simple OLS model is estimated using the `statsmodels` library:

**Model specification:**

GDP_growth = β0 + β1 * Inflation + β2 * FDI + β3 * FX_Activity + ε

This provides a baseline to observe directional relationships between macroeconomic variables and growth.

## 5. How to Run the Notebook

### Option 1 — Google Colab (Recommended)

Click the badge below to open the notebook directly in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/luisaghernandez-cyber/forex-regulation-economic-growth/blob/main/notebooks/forex_regulation_analysis.ipynb)

This option requires no installation and runs entirely in the cloud.

---

### Option 2 — Run Locally

#### 1. Clone the repository:

git clone https://github.com/luisaghernandez-cyber/forex-regulation-economic-growth.git
cd forex-regulation-economic-growth

2. install required packages : pip install pandas matplotlib requests statsmodels

3. Launch Jupyter notebook: pip install pandas matplotlib requests statsmodels.

## 6. Contact

**Luisa Gabriela Hernández Laverde**  
Bogotá, Colombia  

Business Administration & International Relations — Pontificia Universidad Javeriana  

Areas of interest:  
- Macroeconomics  
- FX Markets  
- Trading & Finance  
- Data Analysis (Python)  
- AI Automation and Workflow Optimization  

If you'd like to collaborate, discuss research, or request additional analyses, feel free to reach out.




