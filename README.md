# Power-BI
1) DAX for multiply 2 measures from 2 tables: 
from products table: Total Cost = SUMX(shipments,shipments[Boxes]*RELATED(products[Cost per box]))
2) division: Profit % = DIVIDE([Total Profit],[Total Sales])
3) Number of records in a table: Total Shipments = COUNTROWS(shipments)
4) Filter: LBS Count = CALCULATE([Total Shipments],shipments[Boxes]<50)
