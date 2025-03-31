# Toman-Bike-Shop

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Preparation](#data-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#results/findings)
- [Recommendations](#recommendations)

### Project Overview

This project aims to provide in sights for Toman Bike Shop over the past 2 years. By analysing various aspects of the data to identify profits & revenue trends, seasonal revenue, hourly revenue analysis for informed decision making.

![Screenshot (47)](https://github.com/user-attachments/assets/33dc45ae-531e-438c-9dba-10f6b977c13d)

### Data Sources

Sales Data: 
- The primary datasets include- "bike_share_yr_0.csv", "bike_share_yr_1.csv" and "cost_table.csv", containing detailed information about each sale made by the company and the associated costs

### Tools

- SQL server - Data analysis
- Power BI - Creating report

### Data Preparation

In the intial data preparation phase, we peformed the following tasks:
1. Created a database on SQL server for Toman Bike Shop.
2. Then added tables to the database using the csv files.
3. Joined the tables to form 1 with comprehensive report.
4. Then transformed the data to Power BI for visualisation.

### Exploratory Data Analysis

EDA invloved exploring the sales data to answer key question, such as:

- Which hours are most likely to have high sales recorded?
- During which season are most bikes bought?
- How best can the company increase its prices during the next year?

### Data Analysis

``` sql
with cte as (
select * from bike_share_yr_0
union all
select * from bike_share_yr_1)


select 
dteday,
season,
a.yr,
weekday,
hr,
rider_type,
riders,
price,
COGS,
riders*price as revenue,
riders*price-COGS as profit
from cte a
left join cost_table b
on a.yr = b.yr
```
### Results/Findings

The analysis results are summarises as follows:
1. Sales revenue increased during the second year despite the increase in price.
2. During the month of August and September is when the highest sales are recorded.
3. Late evening hours during the 16th hour to the 19th hour is when the highest sales are made.
4. There was a 25% increase in price which lead to a 64% increase in demand from the previous year.

### Recommendations

Based on the analysis, we recommend the following actions:
1. Offer discounts or products which may compliment our bikes during the peak hours to keep our sales high.
2. More stock to be available during season 3 which has the highest sales
3. We recommend different pricings for different types of customers offering discounts to registered users.
4. We recommend a a 10-15% increase in price to test market response without risking a significant loss of customers.
5. Conduct further markets research to understand customer satisfaction, potential competetive changes and the overall economic enviroment.This can guide whether leaning towards the lower or higher end of the suggested increse.






