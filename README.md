# Trend-Follow-Backtesting-C++

*Strategy - Whenever a stock price increses by X% compared to its minimum price in last Y days, 
we buy a stock and similarly whenever a stock price decreases by X% compared to its maximum price in last Y days, 
we sell the stock.*

Data is pre-downloaded from yahoo finance and stored as csv files.

Multithreading is implemented, each Symbol(stock) is processed on a seprate thread, to speed up the backtesting process.

Variables Used<br />
SYMBOLS  - List of all Stock symbols from yahoo finance we wish to backtest on.<br />
DATA_RANGE - Range of historial data to use, example "5y" represents past 5 year data.<br />
DATA_INTERVAL = Interval of downloaded data, "1d" represents daily price data.<br />
LOOKBACK_PERIOD = Period to compare current price from.<br />
ENTER_TRIGGER_PERCENTAGE = Percentage change that trigger to enter a trade.<br />
EXIT_TRIGGER_PERCENTAGE =  Percentage change that trigger to exit a trade.<br />
TARGET_PERCENTAGE = Target Percentage that trigger to exit a trade.

Results
Average profit per trade, number of total trades and winning trades are displayed for each symbol on std output.

Explanation for all Classes<br />
1. Data - Used to store data for each ticker. (Also handle data parsing from csv logic)
2. DataPoint - This is struct, used to store a row(per day's data).

3. Strategy - Virtual class to define template of trading strategy
4. TrendFollowingStrategy - It implements Strategy, logic specific to the trading strategy is encapsulated here.

4. Backtest - It Takes a Data Object and a Strategy Object and performs backtesting. Logic specific to backtest like evaluation of strategy, displaying results etc is encapsulated here.

5. Driver Class - It Takes Strategy instance, csv files names and number of threads as input. Handles multithreading and executes backtesting of each symbol/ticker on seprate threads.  
