# Shopping Trends Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results / Findings](#results-/-findings)
- [Recommendations](#recommendations)
---

### Project Overview
This project analyzes shopping trends using MsExcel, SQL and Power Bi Tools, in uncovering insights into customer behavior and sales patterns. The analysis explores specific aspects such as seasonal trends, product category trends, and also demographic trends to provide insights for making informed data-driven business decisions.

![ShoppingTrends Dashboard Screenshot](https://github.com/user-attachments/assets/2cfbbca8-e9c2-415a-9320-9efa477cb9d3)


### Data Sources

Shopping Trend Data: The primary dataset used for this analysis was gotten from Kaggle. 
[download here](https://www.kaggle.com/datasets/bhadramohit/customer-shopping-latest-trends-dataset)

### Tools

- Microsoft Excel (Data Storage and Data Organization).
- SQL Server (Data Querying and Data Transformation).
- PowerBi (Data Modelling, adding measure to already existing fields and Data Visualization, building interactive dashboard).

### Data Cleaning and Preparation
The dataset did not require cleaning as it was a clean data without duplicates, missing values. 
However, I separated the dataset into two different excel worksheets to make it easier to manage, analyze and export to SQL for further analysis (Data Segmentation/Partitioning)

### Exploratory Data Analysis
Exploring the dataset to answer key questions, such as:

- What the top selling product was?
- What season had the most revenue across all different locations?
- What is the top 3 most preferred payment methods?
- The age group with highest revenue generated?

### Data Analysis

```sql
SELECT
a.age, a.gender, a.item_purchased, a.category, a.amount AS revenue, a.location, a.subscription_status, a.shipping_type,
b.season, b.payment_means, b.payment_method, b.frequency_of_purchases, b.review_rating, b.discount_applied, b.promo_code_used, b.size, b.color
FROM shoppingtrends_ci AS a
JOIN shoppingtrends_si AS b
ON a.id = b.id;
```

```powerbi
1. Age Group = SWITCH(TRUE(), 'Query1'[age]>=18 && 'Query1'[age]<=24, "18-24",
'Query1'[age]>=25 && 'Query1'[age]<=34, "25-34",
'Query1'[age]>=35 && 'Query1'[age]<=44, "35-44",
'Query1'[age]>=45 && 'Query1'[age]<=54, "45-54",
'Query1'[age]>=55 && 'Query1'[age]<=64, "55-64",
'Query1'[age]>=65, "65 and above", "Unknown")
```

### Results / Findings

The analysis results are summarized as follows;
1. The top selling product category was CLOTHING with 44.73% in total revenue.
2. The Fall Season recorded the most revenue across all product category, with 25.75% of the total revenue.
3. The top 3 preferred payment method is PayPal, Credit card and Cash in that order.
4. Customers in the age group 45-54 generated the highest revenue.
5. Majority of revenue generated are from Male gender with 67.74% of total revenue.


### Recommendations

Based on the analysis, I recommmend the following actions;
1. Focus marketing the Clothing category on Social media and also by adding more clothing brands or styles to cater to diverse customer preferences.
2. Ensure sufficient inventory levels of top selling products during the Fall season to meet increased demand.
3. Offer Incentives and discounts during the peak season.
4. Ensure that PayPal, Credit card and cash payments are seamless and efficient.
5. Develop products or services that cater to the needs and interests of this age group and Male gender.







 
