# Power-BI

[Link to this Portfolio project](https://app.powerbi.com/view?r=eyJrIjoiZmU2ODcwOTItNTBlZS00ZDViLTgyOWUtNWZmOWNmMzc4OTc3IiwidCI6ImNlN2MyYzVlLTQ1NmEtNGM5NC1iMWU2LTIyNDQ0ODdiNWNhOSIsImMiOjJ9)

<img width="607" alt="Screenshot 2025-03-24 at 1 23 32 AM" src="https://github.com/user-attachments/assets/d421278f-790b-43b9-a591-009e8c8822d0" />



**Concepts Used:**
1) Bins
2) Parameters/dynamic visual based on slicer
3) Bookmark+Selection switch functionality
4) New cards, with reference values (Design option for separate comditional formatting)
5) Gauge with Target setting
6) Zoom slider
7) Image insertion in a table
8) Icon creation in tables, based on performance indicator column made with help of If function
9) tooltip
10) Calculated Groups
11) **DAX Calcultions Samples:**
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
        8) Latest Date = LASTDATE('calendar'[Start of Month])
        9) Total Sales Latest Month = 
                VAR ld = [Latest Date]
            RETURN
                CALCULATE([Total Sales],'calendar'[Date]=ld)
        10) Latest MoM Sales Change % = 
                VAR ld = [Latest Date]
                VAR this_month_sales = [Total Sales Latest Month]
                VAR prev_month_sales = CALCULATE([Total Sales],'calendar'[Start of Month]=EDATE(ld,-1))
            RETURN DIVIDE(this_month_sales-prev_month_sales,prev_month_sales)
        11) Calculated Groups:
            MoM % = 
                VAR ld = LASTDATE('calendar'[Start of Month])
                VAR this_month_sales = CALCULATE(SELECTEDMEASURE(),'calendar'[Start of Month]=ld)
                VAR prev_month_sales = CALCULATE(SELECTEDMEASURE(),'calendar'[Start of Month]=EDATE(ld,-1))
            RETURN DIVIDE(this_month_sales-prev_month_sales,prev_month_sales)

Published workbook: https://app.powerbi.com/groups/me/reports/e1e68e7d-d534-4e5a-8bb0-015bd347f5a2/dd13fce710e1d8204807?experience=power-bi
