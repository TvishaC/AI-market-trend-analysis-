# AI-market-trend-analysis-

## 📌 Problem Overview

Retail businesses need to plan inventory, budgeting, and operations based on future demand. Manual forecasting is slow and inaccurate.  
This project uses AI to forecast monthly sales trends.

**AI Task:** Time-Series Forecasting  
**Goal:** Predict future monthly total sales for the next 4 to 12 months


## 📊 Dataset Description

**Data Source:** Retail invoice dataset (Kaggle)  
**Initial Data:** Invoice-level  
**Final Data:** Monthly aggregated sales

**Feature Engineering performed:**
- Converted InvoiceDate to datetime
- Computed: `TotalSales = Quantity × Price`
- Aggregated by month
- Extracted `year` and `month`
- Created continuous time-series index

**Target Variable:** `Monthly Total Sales`

## 🧠 Models Used

Three models were tested:

1. **Linear Regression (Baseline)**
   - Purpose: establish minimum benchmark
   - Result: high error, weak fit → insufficient for forecasting

2. **Prophet (Attempted)**
   - Pros: seasonality detection
   - Result: over-smoothed patterns → unstable for small dataset

3. **ARIMA (Final Selected Model)**
   - Pros: works well on short time-series
   - Used for both **4-month** and **12-month** predictions

## 🧪 Evaluation Metrics

Model performance evaluated using:
- **MAE (Mean Absolute Error)**
- **RMSE (Root Mean Square Error)**
- **MAPE (Mean Absolute Percentage Error)**

Example test results (4-month forecast): MAE ≈ 434,582
RMSE ≈ 453,798


## 📈 Forecast Results

The ARIMA model produced:
✔ realistic short-term trend continuation  
✔ smooth medium-term forecasts  
✔ plots for both 4 and 12 month horizons  

Residual diagnostics confirmed:
- approximate normality
- no autocorrelation
- no structural patterns remaining  
→ meaning ARIMA was a suitable model

## 🔧 Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Libraries | pandas, numpy, matplotlib, statsmodels, sklearn, prophet |
| Notebook | Jupyter Notebook |
| Version Control | Git + GitHub |



## 📂 Project Structure
notebooks/ <-- experiments + model runs
src/ <-- optional scripts (preprocessing/modeling)
plots/ <-- forecasting images
data/ <-- raw or sample data
README.md <-- documentation
requirements.txt <-- dependencies

## 📈 Forecast Results

The ARIMA model produced:
✔ realistic short-term trend continuation  
✔ smooth medium-term forecasts  
✔ plots for both 4 and 12 month horizons  

Residual diagnostics confirmed:
- approximate normality
- no autocorrelation
- no structural patterns remaining  
→ meaning ARIMA was a suitable model



## 🔧 Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| Libraries | pandas, numpy, matplotlib, statsmodels, sklearn, prophet |
| Notebook | Jupyter Notebook |
| Version Control | Git + GitHub |


## 📂 Project Structure
notebooks/ <-- experiments + model runs
src/ <-- optional scripts (preprocessing/modeling)
plots/ <-- forecasting images
data/ <-- raw or sample data
README.md <-- documentation
requirements.txt <-- dependencies



## 🚧 Limitations

- dataset small (~24-36 months)
- univariate (no holidays, promotions, economy)
- long horizon uncertainty increases after 4 months


## 🚀 Future Improvements

- Include external variables (ARIMAX)
- Use SARIMA for explicit seasonal modeling
- Try LSTM / Transformers for deep learning forecasting
- Deploy via dashboard (Streamlit / Flask)

## 👩‍💻 AI Usage Disclosure

ChatGPT was used for:
✔ report/documentation clarification  
✔ explanation formatting  

All coding, model training, evaluation, and analysis were done manually by the student.

## 📎 Conclusion

The project demonstrates that AI-based forecasting can support business decision-making.  
Among tested models, **ARIMA provided the most reliable short-term forecasts** for retail sales.




