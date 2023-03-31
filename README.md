# Trend-Follow-Backtesting-C++

*Strategy - Whenever a stock price increses by X% compared to its minimum price in last Y days, 
we buy a stock and similarly whenever a stock price decreases by X% compared to its maximum price in last Y days, 
we sell the stock.*

Data is pre-downloaded from yahoo finance and stored as csv files.

Multithreading is implemented, each Symbol(stock) is processed on a seprate thread, to speed up the backtesting process.

Funtion backtest_trend_follow_strategy is implemented using states where -<br />
State=0 represents No active buy order or sell order.<br />
State=1 represents Buy order is executed and waiting to exit position.<br />
State=2 represents Sell order is executed and waiting to exit position.<br />

Variables Used<br />
SYMBOLS  - List of all Stock symbols from yahoo finance we wish to backtest on.<br />
DATA_RANGE - Range of historial data to use, example "5y" represents past 5 year data.<br />
DATA_INTERVAL = Interval of downloaded data, "1d" represents daily price data.<br />
LOOKBACK_PERIOD = Period to compare current price from.<br />
ENTER_TRIGGER_PERCENTAGE = Percentage change that trigger to enter a trade.<br />
EXIT_TRIGGER_PERCENTAGE =  Percentage change that trigger to exit a trade.<br />
TARGET_PERCENTAGE = Target Percentage that trigger to exit a trade.

To run the code
Change the variable at top of script and then run python main.py

Results
A table(pandas dataframe) of all trades is printed along with Avg profit and total number of trades executed.