### Map
```
var triggerMap= map.new<string,float>()
triggerMap.put("MOIL",545)
triggerMap.put("GMDCLTD",404)
triggerMap.put("TRIVENI",398)
triggerMap.put("MANGLMCEM",928)
triggerMap.put("CHAMBLFERT",524)
triggerMap.put("JINDALSTEL",1064)
triggerMap.put("IONEXCHANG",665)
triggerMap.put("QUICKHEAL",543)
triggerMap.put("TRACXN",99)
triggerMap.put("OLECTRA",1866)
triggerMap.put("JBMA",2200)
triggerMap.put("KIOCL",483)
triggerMap.put("ACE",1550)
triggerMap.put("ICEMAKE",920)
triggerMap.put("NEWGEN",1028)

//Trigger Calculation
float trigger=triggerMap.contains(syminfo.ticker)?triggerMap.get(syminfo.ticker):0
```
### Custom Types
```
type Trade
    float BuyPrice
    float Stoploss

var holdingMap= map.new<string,Trade>()
holdingMap.put("IREDA",Trade.new(181.6,219))
holdingMap.put("HBLPOWER",Trade.new(518.6,531))
holdingMap.put("OLECTRA",Trade.new(1903.35,1815.85))

float buyPrice=holdingMap.contains(syminfo.ticker)?holdingMap.get(syminfo.ticker).BuyPrice:0
float sellPrice=holdingMap.contains(syminfo.ticker)?holdingMap.get(syminfo.ticker).Stoploss:0

```