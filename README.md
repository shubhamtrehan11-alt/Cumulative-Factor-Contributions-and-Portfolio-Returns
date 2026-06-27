# Cumulative-Factor-Contributions-and-Portfolio-Returns
Portfolio Factor Analysis and Return Attribution
This notebook provides a comprehensive framework for analyzing portfolio returns by decomposing them into systematic factor exposures and idiosyncratic alpha. It leverages rolling Ordinary Least Squares (OLS) regressions to capture time-varying factor loadings and then attributes portfolio performance based on these exposures.

Key Components:
1. Rolling OLS Regressions (RollingFactorModel)
This section defines the RollingFactorModel class, which is designed to:

Estimate Time-Varying Factor Loadings: It calculates how a stock's sensitivity (beta) to various market factors (e.g., Market, Size, Value) changes over time using a rolling window OLS regression.
Identify Exposure Drift: This is crucial for detecting shifts in a stock's risk profile and understanding regime changes in its relationship with market drivers.
Output: The model generates a dictionary of DataFrames, where each DataFrame contains the rolling betas for a specific ticker, indexed by date. It also provides a summary DataFrame of the latest rolling betas for all analyzed stocks.
2. Return Attribution (ReturnAttributor)
This section introduces the ReturnAttributor class, which focuses on:

Decomposing Returns: It breaks down portfolio and individual stock returns into contributions from identified systematic factors and an idiosyncratic 'alpha' component (the portion of return not explained by factors).
Understanding Performance Drivers: By attributing returns, users can understand which factors were the primary drivers of portfolio performance and identify the true skill-based alpha.
Output: The class provides daily factor contributions, cumulative attribution paths for each factor and the portfolio, and aggregated monthly/quarterly summaries of these contributions.
Visualizations:
Cumulative Factor Contributions and Portfolio Return
This interactive line plot visualizes the cumulative performance of each factor (Mkt-RF, SMB, HML, RMW, CMA, WML, Alpha) and the Portfolio itself over the investment period. It helps in understanding which factors have been driving the overall portfolio returns cumulatively. Note: If viewing this notebook on GitHub, the interactive Plotly graph might not render. Please click the 'Open in Colab' badge to view the interactive version.

Latest Rolling Betas Heatmap
This heatmap visually represents the LATEST ROLLING BETAS for all the stocks in your portfolio. Each row corresponds to a stock, and each column represents a factor (Alpha, Mkt-RF, SMB, HML, RMW, CMA, WML). The color intensity indicates the magnitude of the factor loading (beta), allowing you to quickly identify which stocks have strong or weak exposures to different factors at a glance.

Monthly Factor Contributions to Portfolio Return
This bar chart visualizes the monthly contributions of each factor to the portfolio's return over time. Each bar represents a month, and the stacked segments within the bar show the individual contribution of each factor (Mkt-RF, SMB, HML, RMW, CMA, WML, Alpha) for that month, providing a granular view of performance drivers over time.
