First use SQL to extract/find the exact result you want.
Then come to Power Bi and first do some correction.(If you want)
Then use DAX to find the required values and put the values in new columns.
Add different measures as you reqired.
I used five measure - > avg pizza order, avg pizza sold per order,order date, total order , total pizza sold, total revenue.
Avg Order Value = [Total Revenue]/[Total Orders]
Avg Pizzas per Order = [Total Pizzas sold]/[Total Orders]
Total Orders = DISTINCTCOUNT('pizza_sales_excel_file2 (2)'[order_id])
Total Pizzas sold = SUM('pizza_sales_excel_file2 (2)'[quantity])
Total Revenue = SUM('pizza_sales_excel_file2 (2)'[total_price])
Order day = UPPER(LEFT('pizza_sales_excel_file2 (2)'[Day Name],3))
Order Month = UPPER(LEFT('pizza_sales_excel_file2 (2)'[Month Name],3))
** After you make calculation on Power Bi , make sure the results must match with SQL values.
