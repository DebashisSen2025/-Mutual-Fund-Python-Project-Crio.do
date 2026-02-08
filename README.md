## Mutual Fund Investment Strategy - Nifty 50 Analysis

A data-driven approach to creating a balanced mutual fund investment portfolio using historical Nifty 50 stock data. This project analyzes risk-return profiles and provides wealth projection using a Step-up SIP (Systematic Investment Plan) model.

## 📊 Project Overview

This analysis helps investors create a balanced mutual fund portfolio by:
- Identifying stocks with high ROI and low volatility
- Analyzing risk profiles across all Nifty 50 companies
- Projecting wealth accumulation using Step-up SIP methodology
- Visualizing stock performance trends

## ✨ Features

- **Risk-Return Analysis**: Evaluate stocks based on volatility (standard deviation) and ROI
- **Smart Portfolio Selection**: Automated filtering for above-median ROI and below-median volatility
- **Interactive Visualizations**: Plotly-based charts for stock trends and performance comparison
- **Wealth Projections**: Calculate future value using Step-up SIP with 10% annual increment
- **Comprehensive Metrics**: Track growth rates, volatility, and ROI for all Nifty 50 stocks

## 🚀 Getting Started

### Prerequisites

```bash
Python 3.7+
```

### Required Libraries

```bash
pip install pandas numpy plotly
```

### Dataset

The analysis requires a CSV file named `nifty50_closing_prices.csv` with:
- First column: `Date` (datetime format)
- Remaining columns: Stock ticker symbols (e.g., RELIANCE.NS, TCS.NS)
- Daily closing prices for Nifty 50 stocks

## 📁 Project Structure

```
mutual-fund-plan/
│
├── mutual_fund_plan__1_.py    # Main analysis script
├── nifty50_closing_prices.csv # Historical stock data (required)
└── README.md                   # Project documentation
```

## 💡 How It Works

### 1. Data Analysis
- Loads and cleans Nifty 50 closing price data
- Converts dates to datetime format
- Identifies null values and data quality issues

### 2. Performance Metrics
- **ROI Calculation**: `((final_price - initial_price) / initial_price) * 100`
- **Volatility Analysis**: Standard deviation of daily closing prices
- **Growth Rate**: Average percentage change across the time period

### 3. Stock Selection Criteria
The mutual fund portfolio selects companies meeting:
- **ROI** > Median ROI across all Nifty 50 stocks
- **Volatility** < Median volatility across all Nifty 50 stocks

### 4. Investment Allocation
- Uses **inverse volatility weighting**
- Lower volatility stocks receive higher allocation
- Formula: `weight = (1/volatility) / sum(1/volatility)`

### 5. Wealth Projection (Step-up SIP)
- Initial monthly investment: ₹5,000
- Annual increment: 10%
- Compounding frequency: Monthly (n=12)
- Time horizons: 1, 3, 5, and 10 years

## 📈 Key Findings

### Risk Profile Analysis
- **Highest Risk Stock**: SHREECEM.NS
- **Lowest Risk Stock**: TATASTEEL.NS

### Top 10 Low Volatility Stocks
1. TATASTEEL.NS
2. ONGC.NS
3. WIPRO.NS
4. POWERGRID.NS
5. BPCL.NS
6. ITC.NS
7. NTPC.NS
8. COALINDIA.NS
9. HINDALCO.NS
10. UPL.NS

### Wealth Projections (Step-up SIP)
Starting with ₹5,000/month with 10% annual increase:

| Time Period | Projected Wealth |
|-------------|------------------|
| 1 Year      | ₹67,214         |
| 3 Years     | ₹2,73,768       |
| 5 Years     | ₹6,22,025       |
| 10 Years    | ₹27,47,307      |

## 📊 Visualizations

The project generates interactive Plotly charts for:
1. **Stock Price Trends** - Top 10 performers by ROI
2. **Loser Companies** - Bottom 10 performers by ROI
3. **Risk Comparison** - Mutual fund vs. high-growth companies
4. **Wealth Growth Projection** - Step-up SIP accumulation over time
5. **Portfolio Allocation** - Investment distribution pie chart

## 🔧 Usage

### Google Colab (Recommended)
```python
from google.colab import drive
drive.mount('/content/drive')

# Upload your CSV file to /content/
# Run the script
```

### Local Environment
```python
# Update file path in the script
file_path = 'path/to/nifty50_closing_prices.csv'

# Run the script
python mutual_fund_plan__1_.py
```

## 📝 Step-up SIP Formula

```python
def calculate_step_up_sip(initial_p, annual_roi, step_up, total_years, n=12):
    total_fv = 0
    r_monthly = annual_roi / n
    for year_idx in range(total_years):
        p_year = initial_p * ((1 + step_up) ** year_idx)
        fv_of_year_contributions = p_year * (((1 + r_monthly)**n - 1) / r_monthly) * (1 + r_monthly)
        fv_at_end = fv_of_year_contributions * ((1 + r_monthly)**(n * (total_years - (year_idx + 1))))
        total_fv += fv_at_end
    return total_fv
```

## 🎯 Investment Strategy Benefits

- **Risk Mitigation**: Focus on low-volatility stocks reduces portfolio swings
- **Consistent Returns**: Above-median ROI ensures growth potential
- **Compounding Power**: Step-up SIP accelerates wealth accumulation
- **Data-Driven**: Objective criteria eliminate emotional decision-making
- **Diversification**: Spread across multiple Nifty 50 companies

## ⚠️ Disclaimer

This project is for **educational and informational purposes only**. It does not constitute financial advice. Past performance does not guarantee future results. Always:
- Conduct your own research
- Consult with a certified financial advisor
- Consider your risk tolerance and investment goals
- Understand that stock markets are subject to volatility

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📧 Contact

For questions or suggestions, please open an issue on GitHub.

## 📜 License

This project is open source and available under the MIT License.

## 🙏 Acknowledgments

- Data source: Nifty 50 historical closing prices
- Visualization: Plotly library
- Analysis framework: Pandas & NumPy
- <img width="1671" height="657" alt="image" src="https://github.com/user-attachments/assets/5697d4e3-cecb-4e53-a33d-180feecda80a" />


---

**Built with Python 🐍 | Data Analysis 📊 | Financial Planning 💰**
