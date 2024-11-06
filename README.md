# LITA-CAPSTONE-PROJECT-SALES-DATA

## Table of Content 
- Overview
- Data Sources
- Tools Used
- Data Cleaning and Preparation
- Exploratory Data Analysis
- Data Analysis
- Visualization and Inference
- Recommendations
- Limitations
----------------------------------------------------------------------------
### Project Overview
This analysis project aim to generates insight into the sales performance of of a retails store over the past years by analysing the variuos parameters in the data received.
We seek to gather enough insight to make reasonable decisions which then enable us to tell a compelling stories around our data from the insight gotten and to know the best performance from our data uilizing Excel, SQL, and Power BI, the analysis will identify top-selling products, regional trends and monthly Sales pattern. 
By analyzing various aspect of the sales data, this project aims to uncover trends, make data-driven recommedations, and gain a deeper understanding of the company's performance, ultimately designning an interactive Power BI dashboard for stakeholder decision making.

### Data Sources
##### Sales Data
The primary dataset used for this analysis is the 'LITA CAPSTONE DATASET' provided by The Incubator Hub. This dataset contains information about sales transactions made by the retail storeand it  includes the following key columns:
- Region: The geographical area where the store operates.
- OrderID : The specific number or tag of an order
- CustomerID : The specific number or tag of a customer
- Product: The list of product available for sale
- Orderdate: The date in which a particular order was made.
- Quantity: The count of available order sold
- Unit Sold: The number of units sold for a given transaction.



### Tool Used
#### Excel
  For Data cleaning
  For Analysis
  
#### Structured Query Language (SQL)
  For Data Querying
  For Analysis
  
#### PowerBI
For Reporting
For Dashboards Presentation

#### Github
For Sharing insight about the project

### Data Cleaning and Preparation
In the initial Preparation phase i performed the following tasks
Data loading and inspection
Handling Missing Variables
Data Cleaning and Formatting
Removing Duplicates

### Exploratory Data Analysis
- which product is the best-selling?
- what is the overall sales trend?
- Which region has the highest sales?
- what is the total revenue?
- Who are the Top 5 customer by total sales?
- Which region have the most loyal customers?

### Data Analysis
Here are some of the codes and features utilized to extract insights from the customer data include the following:
#### For SQL
FOR  "which product is the best-selling?"
```
Select product, sum(quantity*unitprice) as totalsale
 From [dbo].[LITA+Capstone+Dataset1]
 Group by product
```
what is the overall sales trend?
```
Select region, count(*) as NumberOfTransactions
From [dbo].[LITA+Capstone+Dataset1]
Group by region
```

Which region has the highest sales?
```
select top 1 product, sum(quantity*unitprice) as totalsales
From [dbo].[LITA+Capstone+Dataset1]
Group by product
Order by totalsales desc
```

what is the total revenue?
```
SELECT Product, SUM(Total_Sales) AS TotalRevenue
FROM [dbo].[LITA+Capstone+Dataset1]
GROUP BY Product
```

Who are the Top 5 customer by total sales?
```
Select top 5 customer_id, sum(quantity*unitprice) as totalpurchaseAmount
From [dbo].[LITA+Capstone+Dataset1]
Group by customer_id
Order by TotalPurchaseAmount desc
```

To calculate the percentage of total sales contributed by each region. 
```
With Region As(
 Select Region, sum (Total_Sales) as SalesFromTable from [dbo].[LITA+Capstone+Dataset1]
 Group by Region)
 Select Region, (SalesFromTable * 100.0 / (Select sum(Total_Sales) from [dbo].[LITA+Capstone+Dataset1])) as SalesPercentage
 from Region
```

#### Pivot Summarization
##### Total Sales by Product
![Screenshot 2024-11-05 234726](https://github.com/user-attachments/assets/85d97ae5-2071-41f9-a026-6cb06e296d53)
##### Total Sales by Region
![Screenshot 2024-11-05 235108](https://github.com/user-attachments/assets/aa0c8c66-42d9-426a-a312-61a6d927eec7)

##### Total Sales by Month
![Screenshot 2024-11-05 235122](https://github.com/user-attachments/assets/e6537df5-8266-4a08-a9b7-95be3e62ff63)

##### Region by Product, Total Sales and Quantity
![Screenshot 2024-11-05 235305](https://github.com/user-attachments/assets/a920e5ec-c231-4804-89fd-acf7a5b54ec4)


### Visualization
#### Insight from PowerBI
![Screenshot 2024-11-05 234001](https://github.com/user-attachments/assets/3401b836-d70e-47e7-9d72-a78d379a42ed)


### Result and Conclusion
The result of the analysis are summarized as follows:

The Retail Store sales fluctuate throughout the year, peaking consistently in February. In sales and revenue Shoes and the South region are the best performing. Shirts has the highest average sales while South region alsp boasts the highest average sales. Notably, 2023 sales exceeded 2024 sales by 9.9%, although 2024 is yet to conclude.

### Recommendations
Based on the sales analysis and to capitalize on the insight and findings, I recommend the following strategic actions:

Invest in targeted marketing and promotions to leverage the February sales peak,and maximizing revenue potential.
Prioritize promotions for Shoes and Shirts, ensuring these top-selling products receive adequate attention.
Concentrate marketing efforts on the high-performing South region to further boost sales.
Explore targeted campaigns and opportunities to grow sales in the underperforming west region.
Implement a customer segmentation strategy to effectively target high lifetime value customers

### Limitations
Notable limitations were minimized due to the dataset's cleanliness as no null or blank columns were present, ensuring data integrity However, removing duplicates from the dataset initially may have potentially impacted the accuracy of the analysis.
