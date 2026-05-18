# Data Analysis Project - Portfolio Performance Analytics Project
*By Jaden Tam*

## Table of Contents

- [Project Overview](#project-overview)
- [Data Pipeline Architecture](#data-pipeline-architecture)
- [Some Example Metrics](#some-example-metrics)
- [Analytics Solution Preview](#analytics-solution-preview)
- [Code Preview](#code-preview)

## Project Overview

| Tool | Purpose |
|---|---|
| Python | Data extraction and financial calculations |
| Jupyter Notebook | Development environment |
| Pandas / NumPy | Data transformation and analytics |
| yFinance | Historical market data retrieval |
| SQLite | Structured data storage |
| SQL | Analytical querying |
| Power BI | Dashboard visualization |

The purpose of this project is to create an end-to-end investment portfolio analytics solution, utilizing Python, SQL, and Power BI to evaluate portfolio performance, benchmark-relative returns, rolling volatility, drawdowns, asset-level returns, etc. 

To accomplish this, various Python libraries such as NumPy, Pandas, and yFinance were utilized to obtain, store and transform ticker price data when given a specific frame of time. Additionally, portfolio composition, intitial investment value and the target weights are required to provide total portfolio value and asset-level returns analysis.  

SQLite was also utilized to further transform the data and create relevant analysis using SQL queries within the Jupyter Notebook environment. Afterwards, the fact and analyses tables are exported and linked to the analytics dashboard to provide accurate reporting on individual returns and analyses. 

Through exporting the data, the dashboard can be updated to reflect initial investment, portfolio composition, and timeline changes based on the variables inputted within the simulation. Additionally, the dashboard itself provides many features, such as highlighting specific periods of time within the data, differentiating portfolio or benchmark contributions with a focus on asset-level contribution analysis at the end, and provides summary metrics (such as α, β, or Sharpe Ratio) to improve and streamline portfolio analysis.

## Data Pipeline Architecture 

```text
yFinance API
     ↓
Python Data Pipeline (utilizing Pandas)
     ↓
Portfolio Return & Risk Calculations Functions
     ↓
SQLite / Exporting CSV Analytical and Date Tables
     ↓
Power BI Dashboard
```

## Some Example Metrics
**Daily Asset Return** measures the percent change in asset price from one trading day to the next
<br><br>
$$r_t = \frac{P_t}{P_{t-1}} - 1$$
<br><br>
**Portfolio Return** measures the weighted return of the portfolio across all assets
<br><br>
$$R_{p,t} = \sum_{i=1}^{n} w_i r_i$$
<br><br>
**Annualized Return** measures the compounded yearly growth rate of the portfolio (assuming 252 trading days)
<br><br>
$$\text{Annualized Return} =
    \left(
    \frac{V_{\text{end}}}{V_{\text{start}}}
    \right)^{\frac{252}{n}} - 1$$
<br><br>
**Annualized Volatility** measures the annualized standard deviation of portfolio returns
<br><br>
$$\sigma_{\text{annual}} =
    \sigma_{\text{daily}} \times \sqrt{252}$$
<br><br>
**Rolling Volatility** measures how portfolio risk evolves over time using a rolling window
<br><br>
$$\text{Rolling Volatility} =
\text{STD}(r_t)_{252} \times \sqrt{252}$$
<br><br>
**Beta (β)** measures portfolio sensitivity relative to the benchmark
<br><br>
$$\beta = \frac{\text{Cov}(R_p, R_b)}{\text{Var}(R_b)}$$
<br><br>
**Alpha (α)** measures portfolio return in excess of expected benchmark-adjusted return
<br><br>
$$\alpha = R_p -\left[R_f + \beta(R_b - R_f)\right]$$
<br><br>
**Sharpe Ratio** measures risk-adjusted return relative to volatility
<br><br>
$$\text{Sharpe Ratio} =\frac{R_p - R_f}{\sigma_p}$$

## Analytics Solution Preview

![Dashboard Page 1](./screenshots/Report1.png)
<br>
*First page of the Portfolio Performance Analysis Dashboard, focusing on Portfolio Value, Rolling Returns, and Rolling Volatility*
<br><br>

![Dashbaord Page 2](./screenshots/Report2.png)
<br>
*Second page of the Portfolio Performance Analysis Dashboard, focusing on the Annual Performance Value of the Portfolio*
<br><br>

![Dashbaord Page 3](./screenshots/Report3.png)
<br>
*Third page of the Portfolio Performance Analysis Dashbaord, focusing on the Monthly Returns and Drawdowns*
<br><br>

![Dashbaord Page 4](./screenshots/Report4.png)
<br>
*Final page of the Portfolio Performance Analysis Dashboard, focusing on Summary Metrics and Asset-Level Analysis*
<br>

## Code Preview

**Data Extraction File**
<br>
*Note. Portfolio variables such as portfolio composition, target weights, market variables, and timeline changes can be made here*
<br><br>
![Data Extraction](./screenshots/Extraction1.png)
<br>
![Data Extraction](./screenshots/Extraction2.png)
<br><br>

**Returns Calculations File**
<br>
*This is where the Return Metrics are computed*
<br><br>
![Returns Calc](./screenshots/Return1.png)
<br>
![Returns Calc](./screenshots/Return2.png)
<br>
![Returns Calc](./screenshots/Return3.png)
<br><br>

**Risk Metrics Calculation File**
<br>
*This is where the Risk Metrics are computed*
<br><br>
![Risk Metrics Calc](./screenshots/Risk1.png)
<br>
![Risk Metrics Calc](./screenshots/Risk2.png)
<br>
![Risk Metrics Calc](./screenshots/Risk3.png)
<br><br>

**SQL Queries and Exportation**
<br>
*This is where the SQL Queries are performed for the relevant analysis and exported*
<br><br>
![SQL Files](./screenshots/query1.png)
<br>
![SQL Files](./screenshots/query2.png)
<br>
![SQL Files](./screenshots/query3.png)
<br>
![SQL Files](./screenshots/query4.png)
<br>
![SQL Files](./screenshots/query5.png)
<br>
![SQL Files](./screenshots/query6.png)
<br>
![SQL Files](./screenshots/query7.png)
<br>
![SQL Files](./screenshots/query8.png)
<br>
![SQL Files](./screenshots/query9.png)
