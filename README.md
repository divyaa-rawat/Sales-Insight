# Sales Insights 


### Check Out the Dashboard : https://app.powerbi.com/view?r=eyJrIjoiZjE4YjIyNDUtNmYxZC00YjY2LWE3MmYtOGRlNGZhMGFmYjQ3IiwidCI6ImRmODY3OWNkLWE4MGUtNDVkOC05OWFjLWM4M2VkN2ZmOTVhMCJ9

## Project overview
The project focused on creating a dynamic Power BI dashboard for a computer hardware business, providing real-time sales insights. The Sales Director aimed to use data analysis to navigate market challenges effectively. 

The dashboard included key insights, profit analytics, and performance metrics. It offered a comprehensive view of sales data, featuring real-time visualizations, profitability breakdowns, and performance insights. With a user-friendly interface and scalability, the goal was to empower informed decision-making and enhance competitiveness in the evolving market.



### Steps followed 


- Step 1 : Utilized SQL for data analysis and gaining insights.

      1. In order to read the data  
             
                       - Select * from customer;
                       - Select * from products;

      2. In oder to count the no. of record

                       - Select count(*) from transaction;

      3. In order to analyse the data 
                       
                       - SELECT distinct product_code FROM transactions where market_code='Mark001;

                       - SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

                       - SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

                       - SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date 
                                where date.year=2020 and date.month_name="January" and sales.transaction.market_code='Mark001'

- Step 2 : Loaded data into Power BI Desktop from SQL.

- Step 3 : Conducted data cleaning and transformation using Power Query.

               - Cleaned up the data by getting rid of any extra or empty stuff, making sure the dataset is neat.

               - Used filters to remove things we don't need, so we're left with just the important info for analysis.

               - Made sure all the money values are in the same format, so it's easy to understand and accurate for financial analysis.

- step 4 : Created essential matrices using DAX (Data Analysis Expressions).

               - Profit Margin % = DIVIDE([Total Profit Margin],[Revenue],0)

               - Profit Margin Contribution % = DIVIDE([Total Profit Margin],CALCULATE([Total Profit Margin],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))
                            
               - Revenue = SUM('sales transactions'[new_sales_amount])

               - Revenue Contribution % = DIVIDE([Revenue],CALCULATE([Revenue],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))

               - Revenue LY = CALCULATE([Revenue],SAMEPERIODLASTYEAR('sales date'[date]))

               - Sales Qty = SUM('sales transactions'[sales_qty])

               - Target Diff = [Profit Margin %]-'Profit Target '[Profit Target  Value]

               - Total Profit Margin = sum('sales transactions'[profit_margin])


- step 5 : Created three important report pages 

               1. key Insights         - A quick overview of the most important findings and trends.

               2. Profit Analysis -    - The Profit Analysis page delves into the financial aspect of the business. 
                                         It includes in-depth analyses of profit margins, contributions, and overall financial performance.

               3. Performance Analysis - The Performance Analysis page is dedicated to assessing the overall operational performance of the business. 
                                         It encompasses metrics related to sales quantity, revenue, and year-over-year performance. 

### Insights Gained from the Project
   * Learned how to clean and transform data effectively.
   * Gained insights into using Power Query for better data manipulation.
   * Improved understanding and use of DAX functions for analysis.
   * Successfully applied SQL queries to extract useful information.

## Dashboard in a Snapshot

### Home 

![SI 1](https://github.com/divyaa-rawat/Sales-Insight/assets/147628244/475f555e-a2b5-4e66-9db2-44ad86a89622)


### key Insights
![SI 2](https://github.com/divyaa-rawat/Sales-Insight/assets/147628244/f9c57e1c-5737-4c25-8db0-430f79706360)


### Profit Analysis
![SI 2 1](https://github.com/divyaa-rawat/Sales-Insight/assets/147628244/fe689deb-12f5-467a-ad5c-ea8c2e2ae759)


### Performance Analysis
![SI 4](https://github.com/divyaa-rawat/Sales-Insight/assets/147628244/9c43a0ad-1e30-4d2f-8669-c76bbf37f5d2)
