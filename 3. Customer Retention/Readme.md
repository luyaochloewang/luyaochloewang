### Customer Retention

The project focuses on analyzing customer retention, which is crucial for understanding how well a business retains customers after their initial purchase. The goal is to assess customer retention rates, the average quantity purchased, and the average price by segmenting customers into cohorts based on the month they made their first purchase.

#### Dataset

The analysis uses a real-world transaction dataset with about 500,000 records of a UK-based online retail store, spanning from December 2010 to December 2011. Key features include `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, and `Country`.

#### Key Steps

1. **Data Preparation:**
    
    - Imported necessary libraries and loaded the dataset.
    - Converted `InvoiceDate` to datetime format.
    - Cleaned the data by dropping rows with missing `CustomerID`.
2. **Cohort Creation:**
    
    - Grouped customers into acquisition cohorts based on the month of their first purchase.
    - Calculated the difference in months between a customer's first purchase and subsequent purchases to create a cohort index.
3. **Customer Retention Analysis:**
    
    - Counted the number of customers retained each month by cohort.
    - Calculated monthly retention rates as a percentage of the cohort size.
4. **Average Quantity Analysis:**
    
    - Calculated the average quantity purchased per customer each month by cohort.
5. **Visualization:**
    
    - Visualized retention rates and average quantities to identify trends in customer retention and purchasing behavior across cohorts.

The analysis provides insights into customer behavior over time, helping businesses understand their retention rates and average purchase behavior across different customer cohorts.
