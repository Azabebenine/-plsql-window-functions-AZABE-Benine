
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

## step3

| **Table**        | **Purpose**                            | **Key Columns**                                                                     | **Example Row**                        |
| ---------------- | -------------------------------------- | ----------------------------------------------------------------------------------- | -------------------------------------- |
| **customers**    | Stores customer info for LENOVO buyers | `customer_id (PK)`, `name`, `region`                                                | `1002, Alice Mugisha, Nairobi`         |
| **products**     | Stores laptop and accessory catalog    | `product_id (PK)`, `name`, `category`                                               | `3001, Lenovo ThinkPad E15, Laptop`    |
| **transactions** | Records all LENOVO sales               | `transaction_id (PK)`, `customer_id (FK)`, `product_id (FK)`, `sale_date`, `amount` | `5001, 1002, 3001, 2024-03-10, 850000` |
## ER Diagram
<img width="1221" height="688" alt="image" src="https://github.com/user-attachments/assets/dd0656de-8fb1-442c-abf7-55be27a6ca05" />
## STEP4
Here we have cmd command that used to create the table
<img width="1920" height="1080" alt="Screenshot 2025-09-29 034005" src="https://github.com/user-attachments/assets/c463c447-5c7d-49a1-82b3-b20c8ab68912" />

after to create the user we create the table into the user by using this command

<img width="1920" height="1080" alt="Screenshot 2025-09-29 034853" src="https://github.com/user-attachments/assets/1d961a65-12e8-4fea-bfb7-c52e431e03ed" />
after to create the tables we insert some data into the table 
<img width="1920" height="1080" alt="Screenshot 2025-09-29 040607" src="https://github.com/user-attachments/assets/0302c8bf-6f41-4001-b160-8932a3315381" />
<img width="1920" height="1080" alt="Screenshot 2025-09-29 045032" src="https://github.com/user-attachments/assets/ea088ad9-d40f-4e0e-b7b0-b0ce31141efa" />
<img width="1920" height="1080" alt="Screenshot 2025-09-29 045103" src="https://github.com/user-attachments/assets/8981190b-e230-45f7-ad08-0958efb45deb" />

After this we join ORACLE TO CHECK OUR TABLES AND DATA
This is table with Data 

<img width="1920" height="1080" alt="Screenshot 2025-09-29 065209" src="https://github.com/user-attachments/assets/853e4848-a1fc-4692-ba7e-6b763fafa349" />
<img width="1920" height="1080" alt="Screenshot 2025-09-29 065230" src="https://github.com/user-attachments/assets/da29aa09-e5bf-4448-aefa-c8d66d435be9" />
<img width="1920" height="1080" alt="Screenshot 2025-09-29 065246" src="https://github.com/user-attachments/assets/b417e361-8e83-4137-ab1e-6e02accc3004" />

finally we start using Query to select and using sum, average etc...

<img width="1920" height="1080" alt="Screenshot 2025-09-29 055834" src="https://github.com/user-attachments/assets/332eb110-4556-4fee-99b8-06d3880260c2" />
AGGREGATE
<img width="1920" height="1080" alt="Screenshot 2025-09-29 060214" src="https://github.com/user-attachments/assets/8552cf5b-6c33-452c-a20e-b16d92109fb5" />
<img width="1920" height="1080" alt="Screenshot 2025-09-29 060534" src="https://github.com/user-attachments/assets/6e6d4152-fee0-44b0-bb09-46092afb76a1" />
SUM
<img width="1920" height="1080" alt="Screenshot 2025-09-29 062300" src="https://github.com/user-attachments/assets/1add2634-25fd-48a6-a66b-8449b5ec5f7d" />
<img width="1920" height="1080" alt="Screenshot 2025-09-29 062918" src="https://github.com/user-attachments/assets/2f04562c-f649-4909-9f90-9359a90ffcfe" />

NAVIGATION

<img width="1920" height="1080" alt="Screenshot 2025-09-29 062918" src="https://github.com/user-attachments/assets/dc80fc1c-e356-4bf0-8f83-14df7a724138" />
<img width="1920" height="1080" alt="Screenshot 2025-09-29 063041" src="https://github.com/user-attachments/assets/4f27c6d0-70a8-4ec7-bd4c-2fb759a5cff1" />

## STEP6

1.Descriptive – What happened?


Top spender: Customer 1002 (alice mugisha, Nairobi) made the highest purchase (850,000).

Low spenders: Customers 2003 (dusabe irene, Kigali) and 1234 (benine jolie, Uganda) only spent 45,000 each.

Outlier: The single purchase of 850,000 is far above the other transactions (45,000).

Products: All sales are laptops, but Lenovo Thinkpad E15 dominates revenue.

Trend: Sales are very uneven—one large transaction drives nearly all revenue.


2. Diagnostic – Why did it happen?



Customer concentration: Revenue depends heavily on one customer (risk of overreliance).

Product mix: High-value laptops (E15) create spikes in revenue, while other models (E11, E7) bring smaller amounts.

Market segmentation: Nairobi customer contributed most, suggesting regional differences in purchasing power.

Ties in sales: Two customers (Uganda, Kigali) spent the same amount → possible shared price point or low engagement.


3. Prescriptive – What next?


Customer strategy:


Strengthen relationships with top customer (Alice Mugisha, Nairobi) → loyalty programs, premium services.

Re-engage low-value customers (Uganda, Kigali) → targeted promotions, bundles, or financing options.

Product strategy:


Push mid-range laptops (E7, E11) to balance reliance on the high-ticket E15 model.

Introduce product variety to attract different spending tiers.

Regional strategy:


Invest in Nairobi as a strong revenue hub.

Explore why Kigali and Uganda customers are underperforming → pricing, accessibility, or marketing gaps.

Risk management: Diversify customer base to reduce revenue dependency on one big transaction.

## STEP7

REFERENCES:

1.Wikipedia. Window function (SQL). Available at: https://en.wikipedia.org/wiki/Window_function_(SQL)

2.https://chatgpt.com

3.SQLTutorial.org. SQL NTILE Function. Available at: https://www.sqltutorial.org/sql-window-functions/sql-ntile

4.SQLTutorial.org. SQL CUME_DIST Function. Available at: https://www.sqltutorial.org/sql-window-functions/sql-cume_dist

5.DataLemur. SQL Time-Series Window Functions: LEAD & LAG Tutorial. Available at: https://datalemur.com/sql-tutorial/sql-time-series-window-function-lead-lag

6.Medium. LEAD and LAG Functions in SQL. Available at: https://medium.com/@simon.harrison_Select_Distinct/lead-and-lag-functions-in-sql-37558caa259b

7.The Data School. LAG() & LEAD() | Advanced SQL Window Functions. Available at: https://www.thedataschool.com.au/daniel-lawson/lag-lead-advanced-sql-window-functions

8.Medium. Mastering SQL Analytic Functions: Rank, NTILE, and CUME_DIST. Available at: https://medium.com/@stger040/mastering-sql-analytic-functions-rank-ntile-and-cume-dist-d76bc483217b

9.YugabyteDB Docs. Case Study: Compare PERCENT_RANK(), CUME_DIST(), and NTILE. Available at: https://docs.yugabyte.com/preview/api/ysql/exprs/window_functions/analyzing-a-normal-distribution

10.Neon Tech. PostgreSQL NTILE Function with Examples. Available at: https://neon.com/postgresql/postgresql-window-function/postgresql-ntile-function

 “All sources were properly cited. Implementations and analysis represent original work. No AI-
generated content was copied without attribution or adaptation".












