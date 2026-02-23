# Portfolio Optimization Project

## Environment and Required Packages
This project leverages Python libraries to download, process, analyze, and visualize historical financial data:
- **yfinance**: historical market data retrieval.
- **pandas** & **numpy**: tabular data management and numerical computations.
- **scipy** & **scikit-learn**: optimization and machine learning techniques.
- **matplotlib** & **seaborn**: data visualization.
- **statsmodels** & **arch**: time series modeling and conditional volatility (GARCH).
- **joblib**: storage and retrieval of large objects (models, matrices, results).

**Note:** Installing all dependencies prior to running the project is recommended to ensure full reproducibility.

## Project Folder Structure
The project follows a clear and reproducible structure:



## Asset Universe and Study Period
The project includes 17 representative assets across multiple classes:
- **Equity ETFs**: SPY, QQQ, IWM, EEM
- **Bond ETFs**: TLT, IEF, AGG
- **Gold ETF**: GLD
- **Mega-cap Stocks**: AAPL, MSFT, GOOG, AMZN, NVDA

**Study period:** January 1, 2015 – September 21, 2025  
All raw data is stored in `data/raw` to guarantee reproducibility.

## Historical Data Download and Processing
Daily historical prices for each asset are obtained via `yfinance` with adjustments for dividends and splits. The data is saved in a structured manner to enable complete reproducibility. All CSV files are consolidated into main DataFrames for prices and volumes, and cleaned to ensure:
- Numeric values for computations
- Datetime indices for time series analysis
- Removal of missing or invalid entries
- Computation of simple daily returns

The resulting cleaned datasets serve as the foundation for portfolio optimization and backtesting.

## Portfolio Optimization: Sharpe Ratio Maximization
The portfolio is optimized using a Sharpe ratio framework under realistic constraints:
- **Long-only**: No short positions allowed; each asset has a maximum allocation of 30%.
- **Full investment**: Total portfolio weights sum to 100%.

These constraints ensure practical implementability while reflecting real-world limitations such as liquidity and diversification. The optimized portfolio naturally concentrates capital in assets with the highest historical risk-adjusted returns, assigning zero weight to others as a feature of strict optimality conditions.

### Optimization Interpretation
- The optimizer emphasizes assets with strong standalone performance and diversification benefits.
- Zero-weight assets indicate binding constraints rather than inefficiency.
- The outcome reflects both theoretical optimality and practical feasibility in real markets.

## Backtesting and Performance Evaluation
After optimization, the portfolio’s historical performance is evaluated via backtesting:
- **Buy-and-hold strategy:** Portfolio weights remain fixed throughout the period.
- **Daily returns:** Computed from cleaned adjusted prices.
- **Benchmark comparison:** Evaluated against a passive benchmark (SPY) to measure relative performance.

**Performance metrics** include:
- Total Return
- Annualized Volatility
- Annualized Sharpe Ratio
- Maximum Drawdown

Backtesting results show that despite a concentrated allocation, the portfolio achieves strong risk-adjusted performance, maintains acceptable drawdown levels, and outperforms the benchmark in terms of Sharpe ratio. Concentration emerges naturally from the data rather than arbitrary allocation rules.

## Monte Carlo Risk Simulation
To complement historical backtesting and assess potential future outcomes, a Monte Carlo simulation is conducted:
- **Modeling assumption:** Portfolio returns follow a Gaussian stochastic process estimated from historical data.
- **Simulation:** Thousands of independent price paths are generated over a one-year horizon under a buy-and-hold strategy.
- **Risk metrics:** Expected final portfolio value, downside risk (5th percentile), upside potential (95th percentile), and probability of capital loss.

Monte Carlo analysis provides a probabilistic assessment of portfolio behavior, quantifying tail risk and the likelihood of loss while evaluating the robustness of the optimized allocation. This framework strengthens portfolio evaluation by combining empirical historical performance with potential future outcomes.

### Interpretation
- Optimization under realistic constraints produces a concentrated yet implementable portfolio.
- Backtesting confirms the strategy achieves superior risk-adjusted returns relative to the benchmark.
- Monte Carlo simulation highlights potential future variability, including both downside risk and upside potential.
- Overall, this methodology validates the portfolio as a credible, research-grade investment strategy that balances theoretical optimality with practical execution.
