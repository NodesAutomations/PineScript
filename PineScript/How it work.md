### How Pine Scripts are Executed?
- A pine script is not like programs in many programming languages that executes once and then stop
- it's runtime environment, a script runs in the equivalent of an invisible loop where it is executed once on each bar of whatever chart you are on, from left to right
- Chart bars that ave already closed when the script executes on them are called historical bars. when execution reaches the chart's last bar adn the market is open, it is on the realtime bar.
- The script then executes once every tiem a price or volume change is detected, and one last time for that realtime bar when it closes. That realtime bar then becomes elapsed time bar. 
Note that when the script ececutes in realtime, it does not recalculate on all the chart's historical bars on every price/volume update. It has already calculated once on those bars, so it does not need to recalculate then on every chart tick.

### Time series
- the main data strcuture used in pine script is callled a time series
- Time series contain one value for each bar the script executes on, so they continuously expand as the script executes on more bars. 
- For example for closing value of last bar use `close` variable, but if you need previous bar closing value you need to use `close[1]`, last bar will have 0 index

### Events that trigger execution of script
- For complete bars
    - A new symbol or timeframe is loaded on a chart
    - A script is saved or added to chart
    - A value is modified in script settings
    - a browser refresh
- for realtime bar
    - all events of complete bars also applies here
    - when there a change in price or volume detected