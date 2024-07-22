### Create Simple Table
```js
indicator("Test",overlay= true)
var dashboard= table.new("top_right",2,10)
//Ignore First Row
table.cell(dashboard,0,0,"Dashboard",text_color = color.white,bgcolor = color.teal)
table.merge_cells(dashboard,0,0,1,1)
table.cell(dashboard,0,2,"02",text_color = color.white,bgcolor = color.teal)
table.cell(dashboard,0,3,"03",text_color = color.white,bgcolor = color.teal)
table.cell(dashboard,1,2,"12",text_color = color.white,bgcolor = color.teal)
table.cell(dashboard,1,3,"13",text_color = color.white,bgcolor = color.teal)
```