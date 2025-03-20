# Power-BI
DAX for multiply 2 measures from 2 tables: 
from products table: Total Cost = SUMX(shipments,shipments[Boxes]*RELATED(products[Cost per box]))
