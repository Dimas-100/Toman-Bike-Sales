# Toman-Bike-Sales

## Table of Contents

- [Project Overview](#project-overview)
- [Recommendations](#recommendations)

### Project Overview

![Screenshot 2024-08-09 152040](https://github.com/user-attachments/assets/5f50c005-583a-49f9-a911-23dffb7c8fb1)

### Data Sources
Revenue Data: The primay dataset used for this analysis is the bike_share_yr_0.csv, bike_share_yr_1.csv, and cost_table.csv

### Tools
Power BI (Power Query) - Data Cleaning/Creating Reports
SQL(PostgreSQL) - Data Analysis
PowerPoint - Create Presenetation

### Data Cleaning/Transformation 

In the initial data preparation phase, I performed the following tasks:
 1. Data loading and inspection
 2. Handling mising values
 3. Data cleaning and formatting


### Exploratory Data Analysis

EDA involved exploring revenue data to answer key questions, such as:

 - What are the most profitable seasons and year?
 - Did revenue increase from 2021 to 2022?
 - How did our price increase from $4.99 to $5.99 impact profit?


### Data Analysis

SQL code

'''
WITH cte AS (
SELECT *
FROM bike_year_0
UNION
SELECT *
FROM bike_year_1)

SELECT 
dteday,
season,
cte.yr,
weekday,
hr,
ride_type,
riders,
price,
COGS,
riders * price AS revenue,
riders*price - COGS AS profit
FROM cte
LEFT JOIN cost_table
on cte.yr = cost_table.yr
order by price desc, profit desc
LIMIT 100




### Results/Findings

The analysis results are summarized as follows:
 1. 25% increase in price
 2. increase in demand 64%
 3. The price change of $4.99 to $5.99 saw significanct profit gain


### Recommendations

 Based on the analysis, we recommend the following actions:
 - Increase the price by 10%


### Limitations


### References
