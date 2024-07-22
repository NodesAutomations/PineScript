### Script 
```js
//@version=5
indicator("Test",overlay = true)
//Inputs
horizontalLineLocation=input(2000,"Horizontal Line Location")
//Plot Horizontal Line to Existing Chart
hline(horizontalLineLocation)
//Plot line connecting closing price of chart
closingPlot=plot(close,color = color.red)//close is closing price and open is for open price
openingPlot=plot(open,color = color.green)//close is closing price and open is for open price
//Fill part between two plot
fill(openingPlot,closingPlot,color = color.white)
```
- `//@version=5`
    - This is a compiler annotation telling the compiler the script will use version 5 of Pine Script.
- `indicator("Test",overlay = true)`
    - Defines the name of the script that will appear on the chart as “Test”.
    - overlay (const bool) If true, the indicator will be displayed over the chart. If false, it will be added in a separate pane. Optional. The default is false.
-   `horizontalLineLocation=input(2000,"Horizontal Line Location")`
    - Adds an input to the Inputs tab of your script's Settings, with default value
-  `hline(horizontalLineLocation)`
    - Plot Horizontal Line with 2000 Yaxis value to Existing Chart
- `closingPlot=plot(close,color = color.red)`
    - Plot graph using closing price
- `fill(openingPlot,closingPlot,color = color.white)`
    - Fill Part between two plots


### Study vs Strategy
- both can be used to plot  inforamtion on chart
- both can contain calcution
- Study
    - Put alerts using Study
    - Can't do back testing
- Strategy
    - Used for back testing
    - Can't put alerts
>Note: Study is not indicator type in version 5
 