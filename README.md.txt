# PL/SQL Window Functions Analysis

## Business Problem
This project analyzes transactional sales data for a retail company to understand customer purchasing behavior, product performance, and sales trends. The analysis supports the Sales and Marketing departments in making data-driven decisions using SQL JOINs and Window Functions.

## Business Context
- **Company Type:** Retail Sales Company  
- **Department:** Sales & Marketing Analytics  
- **Industry:** Retail / E-commerce  

The company stores customer, product, and transaction data in an Oracle database and requires advanced SQL analysis to generate insights.

## Data Challenge
The business struggles to identify top-performing products, inactive customers, and sales trends over time. Traditional SQL queries provide limited insights without ranking, cumulative analysis, and comparisons across time periods.

## Expected Outcome
The analysis is expected to:
- Identify top customers and products by revenue
- Detect inactive customers and unsold products
- Analyze sales trends and growth patterns
- Segment customers for targeted marketing strategies


## Success Criteria
The following measurable goals are achieved using window functions:

1. **Top 5 products by revenue** using `RANK()`
2. **Running monthly sales totals** using `SUM() OVER()`
3. **Month-over-month sales growth** using `LAG()`
4. **Customer quartile segmentation** using `NTILE(4)`
5. **Three-month moving averages** using `AVG() OVER()`

## 🗄️ Database Schema
The database consists of three related tables:

### Tables
- **CUSTOMERS**
  - CUSTOMERID (PK)
  - CUSTOMERNAME
  - REGION

- **PRODUCTS**
  - PRODUCTID (PK)
  - PRODUCTNAME
  - PRICE

- **TRANSACTIONS**
  - TRANSACTIONID (PK)
  - CUSTOMERID (FK)
  - PRODUCTID (FK)
  - QUANTITY
  - TRANSACTIONDATE

### ER Diagram
The ER diagram illustrating table relationships is included in the diagrams folder.


## SQL JOIN Queries
Implemented JOIN types include:
- INNER JOIN – Valid customers and products
- LEFT JOIN – Customers with no transactions
- RIGHT / FULL JOIN – Products with no sales
- FULL OUTER JOIN – Matched and unmatched records
- SELF JOIN – Customer comparison within the same region

All JOIN queries are available in the `sql file with screenshots in the screenshots folder.

## Window Function Queries
The project implements four categories of window functions:

1. **Ranking Functions**  
   `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `PERCENT_RANK()`

2. **Aggregate Window Functions**  
   `SUM()`, `AVG()`, `MIN()`, `MAX()` using `ROWS` and `RANGE`

3. **Navigation Functions**  
   `LAG()`, `LEAD()` for growth analysis

4. **Distribution Functions**  
   `NTILE(4)`, `CUME_DIST()` for customer segmentation

Queries are stored in `sql/window_functions.sql`.


## Results Analysis
### Descriptive Analysis
Sales data shows varying customer activity across regions, with a small number of products generating the majority of revenue.

### Diagnostic Analysis
Inactive customers and unsold products indicate opportunities for improved marketing and inventory management.

### Prescriptive Analysis
The company should focus promotions on high-value customers, discontinue low-performing products, and optimize regional sales strategies.


## Screenshots
Clear screenshots of query execution and results are stored in the `screenshots/` folder as proof of implementation.


## References
- Oracle Database SQL Language Reference  
- Oracle Window Functions Documentation  
- Academic SQL Analytics Tutorials from youtube  


## Integrity Statement
“All sources were properly cited. Implementations and analysis represent original work. No AI
generated content was copied without attribution or adaptation.”
