### Daily Values 
- Current timeframe
    - use can use `open`, `close`, `high`,`low ` variable to get ohlc values of last candle
    - use use `open[1]`, `close[1]`, `high[1]`,`low[1]` to get ohlc value of second last candle
    - in short use Array [] with different index to get value of previous candles
    - Same concept with `volume`, `volume[1]`
- Fixed or Specific time frame
    - use `request.security()` function to get chart value using specific time frame
    - `daylow=request.security(syminfo.tickerid, "1D", low)` for day low
    - `predaylow=request.security(syminfo.tickerid, "1D", low[1])` for previous day low
    - `weeklow=request.security(syminfo.tickerid, "1W", low)` for weekly low



### Weekly values

Sample code to get weekly values
```js
weeklyHigh = request.security(syminfo.tickerid, "W", high)
weeklyLow = request.security(syminfo.tickerid, "W", low)
weeklyClose = request.security(syminfo.tickerid, "W", close)
```