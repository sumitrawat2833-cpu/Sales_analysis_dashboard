# Sales_analysis_dashboard
Analysed 50K+ rows of sales data and developed 3+ interactive dashboards to track sales, revenue, and KPIs

# Data Analysis Using SQL
Show all customer records

1. SELECT * FROM customers;

Show total number of customers

2. SELECT count(*) FROM customers;

Show transactions for Chennai market (market code for chennai is Mark001

3. SELECT * FROM transactions where market_code='Mark001';

Show distrinct product codes that were sold in chennai

4. SELECT distinct product_code FROM transactions where market_code='Mark001';

Show transactions where currency is US dollars

5. SELECT * from transactions where currency="USD"

Show transactions in 2020 join by date table

6. SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

Show total revenue in year 2020,

7. SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

Show total revenue in year 2020, January Month,

8. SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

Show total revenue in year 2020 in Chennai

9. SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";

Data Analysis Using Power BI
  Formula to create norm_amount column
= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)
