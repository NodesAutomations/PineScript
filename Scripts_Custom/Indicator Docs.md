# Main Indicator

### What does it contain
- Moving Averages 10/21/50/100/200
- All time high line
- Bull snort Candle marker
- Inside bar candle marker
- Dashboard to help with stock screening it contain
    - % distance from Moving averate
    - % distance form all time high
    - ADR for daily timeframe


### Ema formatting

| Range % | Color | Detail |
| --- | --- | --- |
| [3,) | no color | stock is strongly trading above moving average |
| [0-3) | Green | Stock is close to moving average |
| [-1,0) | Orange | Stock is below moving average but within |
| [,-1) | Red | Stock is trading below moving average |

### ATH formatting

| Range % | Color | Detail |
| --- | --- | --- |
| [-5,0]% | Green | Stock is close to All time high |
| [-15,-5) | no color | stock is withing acceptable range of ATH |
| [-20,-15) | Orange | Stock is on extreme edge of ATH |
| [,-20) | Red | Stock is trading far below ATH |

### ADR formatting

| Range % | Color | Detail |
| --- | --- | --- |
| [5,] | Green | Fast moving stock |
| [3.5,5) | no color | Regular stock |
| [2.5,-3.5) | Orange | Passable Range |
| [,-2.5) | Red | Slow moving stock |

# Helper

### What does it contain
- 