# Primetrade.ai Data Science Intern Assignment: Trader Performance vs Market Sentiment

## Setup & How to Run
1. Clone this repository.
2. Ensure you have Python installed along with `pandas`, `numpy`, and `matplotlib`.
3. The raw data files (`fear_greed_index.csv` and `historical_data.csv`) were provided via Google Drive links in the assignment prompt. Place them in the root directory if running locally.
4. Run the Jupyter Notebook `trader_behavior_analysis.ipynb` cell-by-cell.

## Part A: Methodology
* **Data Alignment:** Merged the 2,644-row Bitcoin Market Sentiment dataset with the 211,224-row Hyperliquid historical data by parsing timestamps to a standard daily date format.
* **Metric Engineering:** Calculated Daily PnL, Trade Frequency, Win Rate, Average Position Size (USD), and Long/Short Ratios per account per day to build a comprehensive behavioral profile.

## Part B: Key Insights
1. **Performance Variance:** The Average Daily PnL is higher on Fear days ($5,185) compared to Greed days ($4,144), but the Median Daily PnL is much higher on Greed days ($265 vs $122). Greed days offer stable profitability, while Fear days produce extreme "fat-tail" winners.
2. **Behavioral Shifts:** During Fear days, traders panic-trade—daily trade count jumps from ~77 to >105. Counter-intuitively, average position sizes also increase during Fear ($8,529 vs $5,954), and the Long/Short ratio spikes to 8.3, showing aggressive "dip-buying".
3. **Trader Segmentation:** * *Frequent Traders* thrive during Fear, capitalizing on volatility. 
   * *Infrequent Traders* suffer heavily during Fear; they irrationally double their average position size (to >$10,800) but yield lower returns.

## Part C: Actionable Strategy Recommendations
* **Rule 1: "Volatility-Scaled Sizing for Retail"** - During Extreme Fear days, dynamically cap maximum position sizes and leverage for infrequent/retail traders to protect them from over-exposure and poor risk management.
* **Rule 2: "Aggressive Alpha Allocation"** - During Fear days, allocate higher capital or loosen trade-frequency limits for Frequent/Consistent-Winning segments. Data shows these traders systematically extract alpha during market dislocations by successfully dip-buying.
