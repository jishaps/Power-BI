# Power-BI
1) DAX for multiply 2 measures from 2 tables: 
from products table: Total Cost = SUMX(shipments,shipments[Boxes]*RELATED(products[Cost per box]))
2) Number of records in a table: Total Shipments = COUNTROWS(shipments)
3) Filter: LBS Count = CALCULATE([Total Shipments],products[Cost per box]<50)
