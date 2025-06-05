# Value-at-Risk-VaR-and-Stress-Testing-in-Python
This project presents a comprehensive analysis of financial risk using three methods of Value at Risk (VaR) estimation, combined with stress testing based on real historical data from Yahoo Finance.
Overview

The goal is to assess the potential loss in a portfolio containing:
1. Apple (AAPL)
2. Microsoft (MSFT)
3. SPDR S&P 500 ETF (SPY), and
4.iShares 20+ Year Treasury Bond ETF (TLT)

We use daily adjusted closing prices from 2020-01-01 to 2024-12-31.

Project Steps
1. Data Collection

   a. Download historical stock prices using yfinance

   b. Extract adjusted close prices

   c. Calculate daily returns

2. Portfolio Definition (Manually assigned)

   a. Assign portfolio weights: [0.3, 0.3, 0.2, 0.2]

   b. Compute daily portfolio returns

3. Value at Risk (VaR) Estimation
  A. Method 1: Historical VaR

  a. Uses empirical quantiles of portfolio returns

  b. 95% and 99% confidence levels

  B. Method 2: Parametric (Normal) VaR

  a. Assumes returns are normally distributed

  b. Uses portfolio return mean and standard deviation

  C. Method 3: Monte Carlo Simulation

  a. Generates synthetic returns using normal distribution

  b. Also explores removing COVID spike to stabilize volatility estimates

4. Stress Testing

   a. Historical stress: Calculate cumulative portfolio loss during COVID crash (2020-03-01 to 2020-04-30)

   b. Hypothetical shock: Apply a uniform 10% drop across all assets

5. Results Summary
A. VaR
   Method	              VaR 95%	  VaR 99%
a. Historical 	        ~2.05%	  ~3.48%
b. Parametric(Normal)	  ~2.13%	  ~2.92%
c. Monte Carlo          ~3.66%    ~3.88%
d. Monte Carlo          ~2.64%    ~2.69%
(excluding COVID spike)
*** Monte Carlo predicts higher VaR due to COVID spike volatility	
B. Stress Test
a. COVID spike	~ 10.94% cumulative returns	
b. Hypothetical Shock	~-10.00%

6. Plots
a. Time series of historical and simulated returns
b. Return distributions for:
A. Historical data
B. Monte Carlo simulations (with and without COVID volatility)
C. Stress period (COVID crash)

7. Python Technologies Used
a. NumPy, Pandas
b. SciPy, Matplotlib, Seaborn
c. yfinance for real-time data

8. Insights
a. VaR estimates are significantly impacted by recent high-volatility events like COVID.
b. Monte Carlo simulations tend to overestimate risk if based on volatile historical periods.
c. Stress testing gives a clearer picture of tail-risk events compared to standard VaR.

9. Files
a. VaR_Stresstest_project.ipynb: Complete Python script
b. README.md: Project overview

10. Connect
 Feel free to reach out if you’d like to collaborate on financial risk modeling or quantitative finance projects.
