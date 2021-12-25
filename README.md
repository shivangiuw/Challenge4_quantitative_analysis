# Quantitative Analysis of Portfolio Risk and Return

* To determine the portfolio fund with the most investment potential, quantitative analysis is done based on following key risk-management metrics:
1. Daily returns (to evaluate performance)
2. Standard deviations (to evaluate risk and volatility)
3. Sharpe ratios (to determine risk-return profile)
4. Betas (measures the directional relationship between stock and the broader market for portfolio diversification)

* The analysis is done in a Jupyter notebook using Pandas library,that contains data preparation, analysis, and visualizations for the key risk and return metrics.
---

## Technologies

This analysis leverages python 3.7 with the following packages:

* [pandas] (https://pandas.pydata.org/docs/getting_started/index.html)- for data analysis

* [jupyter lab] (https://jupyterlab.readthedocs.io/en/stable/)- for working with notebooks, code, data and plots

* [path] (https://docs.python.org/3/library/os.path.html) - for CSV file paths to read 

* [matlplotlib] (https://matplotlib.org/stable/users/installing/index.html)- for data visualization 

---

## Installation Guide

```
 conda install pandas
 pip install jupyterlab
 python -m pip install -U matplotlib
 ```
---
## Usage

The quantitative analysis to determine the portfolio fund with the most investment potential has several components that includes the following:

- analyze the Performance
(using Daily returns `.pct_change()` and cumulative returns `.cumprod()`)
- analyze the Volatility
(using `.plot()` to visualize the daily return data )
- analyze the Risk
(using `.std()` for standard deviation and `.rolling` function)
- analyze Risk-return profile
(using Sharpe ratios (annualized_sharpe_ratios = annualized_average_return / annualized_stdev))
- Portfolio diversification
(using variance`.var()`, covariance `.cov()` and Beta (beta= covariance of portfolio with market / market variance))
---
## Analysis Report

During the analysis, we evaluate the 4 portfolios i.e. SOROS FUND MANAGEMENT LLC, PAULSON & CO.INC.,TIGER GLOBAL MANAGEMENT LLC andBERKSHIRE HATHAWAY INC with respect to the market(S&P 500)to determine the fund with the most investment potential based on key risk-management metrics through various steps as mentioned below with observations and analysis therein.

1. Analyze the Performance
Analyze the data to determine if any of the portfolios outperform the broader stock market, which the S&P 500 represents by generating `daily returns`, `cumulative returns` data from NAVs of the portfolios and further plot them to visualize the performance.
`Observation:` The daily return data over the period and its plot shows the high and low spikes of the daily performance of the S&P 500 and the 4 portfolis, where S&P 500 had the most volatility and fluctuations.
Looking  at the the cumulative return data and the visualization plots, none of the four fund portfolios outperform the S&P 500, with cumulative returns of 1.718858. However "BERKSHIRE HATHAWAY INC"  with cumulative returns of 1.236625 performed the best over the period as compared to other portfolios.

2. Analyze the Volatility
Analyze the volatility of each of the four fund portfolios and of the S&P 500 Index by using `box plots` to visualize the daily return data. Further, visualize the daily return data for just the four fund portfolios by using another box plot for a new DataFrame that contains the data for just the four fund portfolios by dropping the S&P 500 column.
`Observation:` The box plot visualization of the four portfolios shows "BERKSHIRE HATHAWAY INC" is the most volatile fund portfolio with the greatest spread which is evident from biggest quartiles and longest whiskers whereas "TIGER GLOBAL MANAGEMENT LLC" is the least volatile portfolio with the smallest spread.

** Here evaluation of each portfolio uses rolling statistics to track the risk-reward behavior over time.

3. Analyze the Risk
Evaluate the risk profile by using the `standard deviation` and `annualized standard deviation` for each of the four portfolios and for the S&P 500. Using the daily returns DataFrame and a `21-day rolling window` to plot the rolling standard deviations of the four fund portfolios with the S&P 500 index. Also, plot the rolling standard deviations of only the four fund portfolios.
`Observation:` Looking at the annualized standard deviation data for S&P 500 and the four portfolios, S&P 500 has highest annualized standard deviation of 0.183345 whereas all the portfolios have lesser annualized standard deviation than S&P 500. So none of the portfolio pose more risk than S&P 500.   
Further looking at 21 days rolling standard deviation data and its plot for the portfolios and market, we see that the change in risk of the market(S&P 500) brings the change in risk of portfolios as well, but the increase in risk of S&P 500 does not always leads to increase in the risk of portfolios, and on many intances portfolios' risk decreased with increase in market risk.
The 21 day rolling standard deviations of only the fund portfolios show that "BERKSHIRE HATHAWAY INC" is the most volatile portfolio amongst the four which means it poses the most risk, which is evident from the box plot as well where it has bigger quartiles and longer whiskers than other portfolios.

4. Analyze the Risk-Return Profile
To determine the overall risk of an asset or portfolio, we consider not only its risk metrics but also its risk-return profile. Using the daily return DataFrame to calculate `the annualized average return data` for the four fund portfolios and for the S&P 500, calculate the `Sharpe ratios` for the four fund portfolios and for the S&P 500.Review the resulting Sharpe ratios, sorted from lowest to highest. Visualize the Sharpe ratios for the four funds and for the S&P 500 in a bar chart.

`Observation:` Out of the four portfolios "BERKSHIRE HATHAWAY INC" offers the best risk-return profile with highest Sharpe Ratio of 0.717512 which is even higher than that of the market(S&P 500) i.e. 0.589612. "PAULSON & CO. INC." offers worst risk-return profile with a negative Sharpe Ratio of -0.189998. Further we can see from the plot that "TIGER GLOBAL MANAGEMENT LLC" also has fair risk-return profile with a positive Sharpe ratio.
From the analysis done so far, for Performance, Volatility, Risk & Risk-return profile of the 4 Portfolios relative to the broader market, we see the two portfolios that offer higher daily returns, cumulative returns and annualized average returns are "BERKSHIRE HATHAWAY INC" and "TIGER GLOBAL MANAGEMENT LLC" which are also more volatile and responsive to change in market as compared to other portfolios. Also, both of these portfolios have positive Sharpe ratios i.e. better risk-return profile than other portfolios which have negative Sharpe ratios. Thus, we shortlist these two portfolios for further analysis.

** Shortlisting the portfolios:
From the analysis done so far for Performance, Volatility, Risk & Risk-return profile of the 4 Portfolios relative to the broader market, we see the two portfolios that offer higher daily returns, cumulative returns and annualized average returns are Berkshire Hathaway Inc and Tiger Global Management LLC which are also more volatile and responsive to change in market as compared to other portfolios. Also, both of these portfolios have positive Sharpe ratios i.e. better risk-return profile than other portfolios which have negative Sharpe ratios. Thus, we shortlist these two portfolios for further analysis.

5. Diversify the Portfolio
Evaluate how the portfolios react relative to the broader market, by calculating the `variance` of the S&P 500 by using a 60-day rolling window and visualize the last five rows of the variance of the S&P 500.For each of the two portfolios, using the 60-day rolling window, the daily return data, and the S&P 500 returns, calculate the `covariance`. Review the last five rows of the covariance of the portfolio.
Calculate the beta of the portfolio`(beta= covariance of the portfolio/the variance of the S&P 500)`. Calculate the average value of the 60-day rolling beta of the portfolio using mean function.Plot the 60-day rolling beta. 
`Observation:` Beta measures how much an asset's return value is likely to change relative to changes in the overall market’s return value. Here in our analysis, we see that BERKSHIRE HATHAWAY INC has higher 60 day rolling beta of 0.2214 than TIGER GLOBAL MANAGEMENT LLC which has beta of 0.03093. Thus BERKSHIRE HATHAWAY INC is more sensitive to movements in S&P 500 as compared to TIGER GLOBAL MANAGEMENT LLC.

Looking at the analysis done in previous sections, we had shortlisted the two portfolios, wherein  i.e.BERKSHIRE HATHAWAY INC  had higher standard deviation (volatility)but higher sharpe ratio, and TIGER GLOBAL MANAGEMENT LLC. had lower standard deviation (volatility) and lower sharpe ratio. 
Further we deepened our analysis on these two portfolios by using covariance, beta calculations and overlay visualization of the 60-day rolling betas of the portfolios.It shows that BERKSHIRE HATHAWAY INC with higher beta is more sensitive to movements in S&P 500 exhibiting persistently higher market risk as compared to TIGER GLOBAL MANAGEMENT LLC.
`TIGER GLOBAL MANAGEMENT LLC. seems to be trading with a beta that is closest to the market, and could be the investment choice if looking to invest in conservative of the two portfolios.`
