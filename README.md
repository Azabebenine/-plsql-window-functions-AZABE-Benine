# -plsql-window-functions-AZABE-Benine
DATABASE DEVELOPMENT PL/SQL Assignment
## PROBLEM DEFINITION
STEP1:
I chose a business that sells laptops and computer accessories called LENOVO. They operate in several East African countries like Rwanda, Kenya, and Uganda. Their sales team wants to better understand which laptops are popular in each region and how often customers are buying. This helps them make better decisions when it comes to promotions, restocking, and marketing.
DATE CHALLENGE
Right now, LENOVO has a lot of sales data, but they’re not sure which laptop models are selling the most in different regions or which brands are performing better overall. They also want to understand their customers better like how often someone buys, how much they usually spend, and whether they’re more into budget or high-end laptops. Without this information, they’re just guessing when it comes to advertising and inventory.
EXPECTED
The goal is to find the top 3 best-selling laptops in each region and by brand, track how frequently customers are buying, and group customers based on how much they spend. This analysis will help LENOVO make smarter decisions like who to target with premium offers, which regions need more stock of popular models, and how to design better promotions.

STEP2: SUCCESS CRITERIA
To solve the business problem defined in Step 1 I have outlined 5 clear and measurable goals. Each one will use a specific window function in PL/SQL to give meaningful insights into product performance and customer behavior.
1.	TOP 5 LAPTOP MODELS PER REGION PER QUARTER

We want to know which laptop models are performing best in each region, broken down by quarter. Using the RANK() function will help us rank products by total sales within each region and quarter, so we can easily spot the top 5.
2.	RUNNING MONTHLY SALES TOTALS

To track how sales are progressing over time, we’ll use SUM OVER(ORDER BY month) to calculate a running total of monthly sales. This will help visualize trends and see whether overall revenue is increasing month by month.
3.	MONTH OVER MONTH SALES GROWTH

Using the lag or LEAD function, we’ll compare the current month’s sales to the previous month. This shows whether sales are growing, dropping, or staying flat over time — very useful for business forecasting.
4.	CUSTOMER SPENDING QUARTILES

By applying NTILE over the total amount each customer has spent, we can divide our customers into four spending groups (quartiles). This helps us understand who the high spenders are and who may need incentives to buy more.
5.	THREE MONTH MOVING AVERAGE OF SALES 

To smooth out monthly fluctuations and get a better view of sales trends, we’ll use the AVG OVER(ROWS BETWEEN 2 PRECEDING AND CURRENT ROW) function. This shows a moving average of sales over the last 3 months, which is helpful for identifying long-term patterns.

