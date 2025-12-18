# Cross-Asset Portfolio Optimization

A comprehensive portfolio optimization system implementing multiple quantitative strategies for cross-asset allocation across cryptocurrencies, equities, indices, and commodities.

## 📊 Project Overview

This project develops and backtests systematic portfolio optimization strategies on real historical market data, focusing on maximizing risk-adjusted returns while maintaining robust drawdown controls.

### Asset Universe
- **Cryptocurrencies:** Bitcoin (BTC), Ethereum (ETH)
- **Equities:** Apple, Amazon, Microsoft, NVIDIA, Tesla, Meta
- **Index:** NASDAQ 100
- **Commodities:** Gold, Silver, Crude Oil

## 🎯 Optimization Strategies

### 1. Mean-Variance Optimization (Markowitz)
- Maximizes Sharpe ratio using quadratic programming
- Position limits: 0-30% per asset
- Nobel Prize-winning framework (1990)

### 2. Risk Parity
- Equal risk contribution from each asset
- More diversified allocation
- Better stability across market regimes

### 3. Equal Weight Baseline
- Simple 1/N allocation for benchmarking
- No optimization error

## 🔧 Technical Implementation

### Core Technologies
- **Python 3.14** with scientific computing stack
- **Pandas/NumPy** for data manipulation
- **SciPy** for mathematical optimization
- **Scikit-learn** for covariance estimation & regime detection
- **Matplotlib/Seaborn** for visualization

### Key Features
- Ledoit-Wolf shrinkage for stable covariance estimation
- Market regime detection using K-Means clustering
- Quarterly rebalancing with quarterly frequency (63 trading days)
- Comprehensive risk metrics (Sharpe, Sortino, Calmar, VaR, CVaR)
- Transaction cost modeling (default 0%)

## 📈 Performance Metrics

The system evaluates strategies across multiple dimensions:

- **Return Metrics:** Annualized return, cumulative return
- **Risk Metrics:** Volatility, maximum drawdown, VaR, CVaR
- **Risk-Adjusted:** Sharpe ratio, Sortino ratio, Calmar ratio
- **Stability:** Rolling Sharpe, win rate, drawdown recovery

## 🚀 Getting Started

### Installation

```bash
# Clone repository
git clone <repository-url>
cd PortfolioBuilding

# Create virtual environment
python -m venv .venv
.venv\Scripts\activate  # Windows
source .venv/bin/activate  # Linux/Mac

# Install dependencies
pip install -r requirements.txt
```

### Running the Notebook

```bash
jupyter lab portfolio_optimization.ipynb
```

Execute cells sequentially from top to bottom. The notebook will:
1. Load and clean all 12 datasets
2. Calculate returns and risk metrics
3. Detect market regimes
4. Optimize portfolio weights
5. Backtest all strategies
6. Generate comprehensive visualizations
7. Display performance comparison

## 📁 Project Structure

```
PortfolioBuilding/
├── portfolio_optimization.ipynb  # Main analysis notebook
├── requirements.txt              # Python dependencies
├── .gitignore                    # Git exclusions
├── README.md                     # This file
└── PortfolioBuilding/            # Data folder
    ├── BTC_USD Bitfinex Historical Data.csv
    ├── ETH_USD Binance Historical Data.csv
    ├── Apple Stock Price History.csv
    ├── Amazon.com Stock Price History.csv
    ├── Microsoft Stock Price History.csv
    ├── NVIDIA Stock Price History.csv
    ├── Tesla Stock Price History.csv
    ├── Meta Platforms Stock Price History.csv
    ├── Nasdaq 100 Historical Data.csv
    ├── Gold Futures Historical Data.csv
    ├── Silver Futures Historical Data.csv
    └── Crude Oil WTI Futures Historical Data.csv
```

## 🎓 Methodology

### Data Preprocessing
1. Load OHLCV data from CSV files
2. Clean and standardize price formats
3. Handle missing values (forward/backward fill)
4. Align all assets to common date range
5. Calculate daily and log returns

### Feature Engineering
1. **Correlation Analysis:** Identify asset relationships
2. **Covariance Matrix:** Ledoit-Wolf shrinkage estimation
3. **Regime Detection:** K-Means clustering on volatility patterns
4. **Rolling Metrics:** 30-day volatility, moving averages

### Optimization
- **Objective:** Maximize Sharpe ratio or minimize risk concentration
- **Constraints:** Weights sum to 1, no short-selling, position limits
- **Method:** Sequential Least Squares Programming (SLSQP)

### Backtesting
- **Period:** Full available historical data
- **Rebalancing:** Quarterly (every 63 trading days)
- **Initial Capital:** $100,000
- **Costs:** 0% transaction costs (competition default)

## 📊 Key Results

All strategies are evaluated on:
- Out-of-sample performance
- Risk-adjusted returns (Sharpe > 1.0 target)
- Maximum drawdown < 30%
- Consistent performance across market regimes

See notebook for detailed performance comparison and visualizations.

## 🏆 Competition Requirements ✓

- [x] Full implementation in Jupyter Notebook
- [x] All 8 required sections (Introduction → Conclusion)
- [x] Mathematical formulas with LaTeX
- [x] Comprehensive visualizations (equity curves, drawdowns, distributions)
- [x] All mandatory metrics (Sharpe, Sortino, Max DD, Volatility)
- [x] Professional documentation and explanations
- [x] Uses only provided datasets
- [x] Reproducible and runs end-to-end

## 🔮 Future Enhancements

- Dynamic regime-switching allocation
- Transaction cost modeling
- Factor-based risk models (Fama-French)
- Machine learning return prediction
- CVaR optimization for tail risk
- Walk-forward optimization
- Monte Carlo stress testing

## 👤 Author

**Abhinav Shukla**  

