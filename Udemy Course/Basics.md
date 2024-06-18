### Overall Structure of PineScript
Sample Script
```pinescript
//@version

study(title="Name of Script")

src = Close
len = input(14, minval=1, title="Length")
up = rma(max(change(src),0),len)
down = rma(-min(change(src),0),len)
rsi = down == ? 100 : up == 0 ? 0 : 100 - (100/(1+1+ up/down))

plot(rsi, color=color.purple)
```
- Version
    - First part indicate version of pine script
    - latest version is 5
    - Different version have different syntax or api so it's not back compatible
- Study
    - So there only two types of pine script
    - it's either study or strategy depending on usecase
    - You can find more details about them below

### Study vs Strategy
- both can be used to plot  inforamtion on chart
- both can contain calcution
- Study
    - Put alerts using Study
    - Can't do back testing
- Strategy
    - Used for back testing
    - Can't put alerts


### Comments
- `//` used for single line commnet
