# Power-BI
1) DAX for multiply 2 measures from 2 tables: 
from products table: Total Cost = SUMX(shipments,shipments[Boxes]*RELATED(products[Cost per box]))
2) division: Profit % = DIVIDE([Total Profit],[Total Sales])
3) Number of records in a table: Total Shipments = COUNTROWS(shipments)
4) Filter: LBS Count = CALCULATE([Total Shipments],shipments[Boxes]<50)
5) In the model view, right click calendar in the data pane and choose mark as date
6) Total Sales (Prev Month) = CALCULATE([Total Sales],PREVIOUSMONTH('calendar'[Date]))
7) MoM Sales Change % = 
    VAR this_month = [Total Sales]
    VAR prev_month = [Total Sales (Prev Month)]
RETURN 
    DIVIDE(this_month-prev_month,prev_month)
