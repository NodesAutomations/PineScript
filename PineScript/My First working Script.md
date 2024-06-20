### Script 
```
indicator("My First Script",overlay = true)
//Plot Horizontal Line to Existing Chart
hline(2000)
//Plot line connecting closing price of chart
closingPlot=plot(close,color = color.red)//close is closing price and open is for open price
openingPlot=plot(open,color = color.green)//close is closing price and open is for open price
//Fill part between two plot
fill(openingPlot,closingPlot,color = color.white)
```
