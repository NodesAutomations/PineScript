```
//@version=5
indicator(title="Test", overlay=true,timeframe = "1D")

// GetChartHighest() returns the highest value of the given argument
// for the entire chart. That `dataSeries` argument is optional and
// defaults to the bar high prices when not set.
// Note: call this function on every bar for calculation consistency.
// Also, function's output depends on how many bars TradingView loaded
// on chart.
GetChartHighest(dataSeries = high) =>
    var chartHighest = dataSeries
    if dataSeries > nz(chartHighest, -1e10)
        chartHighest := dataSeries
    chartHighest


// GetAllTimeHigh() returns the all-time highest value for the given
// series.
// Call this function on every bar for calculation consistency.
// The function's result depends on how much historical data
// TradingView has for the instrument and exchange combination.
GetAllTimeHigh(dataSeries = high) =>
    highestHTF = request.security(syminfo.tickerid, "D", 
         GetChartHighest(dataSeries)[1], lookahead=barmerge.lookahead_on)
    highestChartTF = GetChartHighest(dataSeries)
    math.max(highestHTF, highestChartTF)


// Get and plot the all-time high
plot(series=GetAllTimeHigh(), color=color.white, linewidth=1,title="All-Time High")

ma(source, length, type) =>
    type == "SMA" ? ta.sma(source, length) :
     type == "EMA" ? ta.ema(source, length) :
     type == "SMMA (RMA)" ? ta.rma(source, length) :
     type == "WMA" ? ta.wma(source, length) :
     type == "VWMA" ? ta.vwma(source, length) :
     na

show_10d   = input(true, "10 Day")
plot(show_10d ?  ma(close, 10, "EMA") : na, color = #ef2a57, title="10 Day")
 
show_21d   = input(true   , "21 Day" )
plot(show_21d ?  ma(close, 21, "EMA") : na, color = #fc941a, title="21 Day")

show_50d   = input(true   , "50 Day" )
plot(show_50d ? ma(close, 50, "EMA") : na, color = #4eaf53, title="50 Day")

show_100d   = input(false   , "100 Day" )
plot(show_100d ? ma(close, 100, "EMA") : na, color = #3768fd, title="100 Day")

show_200d  = input(false   , "200 Day" )
plot(show_200d ?  ma(close, 200, "EMA") : na, color = #fde947, title="200 Day")
```