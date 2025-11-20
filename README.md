# Bike Shop Analysis Project

This project analyzes the sales and profitability data for a bike shop over a two-year period using SQL and Power BI. The objective was to identify trends, generate insights, and recommend strategies for pricing and profitability improvements.

## Project Overview

The analysis covered two years of data from the `bike_share_yr_0` and `bike_share_yr_1` tables, as well as a `cost_table` detailing costs and pricing. SQL was used to clean and merge the data, while Power BI was used to visualize key metrics and create an interactive dashboard.

---

## Dashboard Preview

Below is a preview of the dashboard created for the Bike Store project:

![Dashboard Preview](https://github.com/shreyashsupe/Dashboard-Projects/blob/main/Bike%20Data%20Analysis%20(SQl%2BPowerbi)/Dashboard.png)

![Dashboard Preview](https://github.com/Strik3r10/Analyst-2-SQL-PowerBI/blob/main/Dashboard1.png)

## Tools and Technologies

- **SQL**: For data cleaning, transformation, and analysis.
- **Power BI**: For data visualization and dashboard creation.

---

## Steps in the Project

1. **Data Preparation in SQL:**
   - Combined data from `bike_share_yr_0` and `bike_share_yr_1` using a `UNION ALL` query.
   - Joined the combined dataset with the `cost_table` to calculate revenue and profit.
   - Calculated the following metrics:
     - **Revenue**: `riders * price`
     - **Profit**: `revenue - COGS`

   Example SQL Query:
   ```sql
   WITH cte AS (
       SELECT * FROM bike_share_yr_0
       UNION ALL
       SELECT * FROM bike_share_yr_1
   )
   SELECT 
       dteday, season, a.yr, weekday, hr, rider_type, riders, price, COGS,
       riders * price AS revenue,
       (riders * price) - COGS AS profit
   FROM cte AS a
   LEFT JOIN cost_table AS b 
   ON a.yr = b.yr;
   ```

2. **Exporting Results:**
   - Exported SQL query results to a CSV file for use in Power BI.

3. **Visualization in Power BI:**
   - Created an interactive dashboard with the following elements:
     - **KPI Metrics:** Total riders, total revenue, and total profit.
     - **Revenue and Profit Over Time:** A bar and line chart showing trends over two years.
     - **Revenue by Season:** Bar chart visualizing revenue per season.
     - **Riders Demographics:** A donut chart showing the proportion of casual vs. registered users.
     - **Profitability by Hour:** A heatmap showing revenue across different hours and days of the week.

---

## Key Findings

1. **When Are We Making Money?**
   - Peak earnings occur during early evening hours, specifically between 5:00 PM and 7:00 PM, with total peak-hour revenue of $1.55M.
   - Peak-hour revenue is approximately 23% higher than average hourly revenue.

2. **Revenue by Season:**
   - Season 3 generated the highest revenue (~$4.9M), followed by Season 2 (~$4.2M).

3. **Rider Demographics:**
   - Registered users contribute ~81.26% of total revenue.
   - Registered riders generate ~4× more profit per trip than casual riders.

4. **KPI Summary:**
   - Total Riders: 3 Million
   - Total Revenue: $15 Million
   - Total Profit: $15.14 Million

---

## Recommendations

1. **Conservative Price Increase:**
   - A 10-15% price increase is recommended to test the market's response without risking significant loss of customers.
   - For example:
     - A 10% increase would raise the price from $4.99 to $5.49.
     - A 15% increase would set the price at approximately $5.74.

2. **Segmented Pricing Strategy:**
   - Introduce separate pricing strategies for casual and registered riders based on their sensitivity to price changes.
   - Offer membership perks to convert high-usage casual riders to the registered category.

3. **Monitor and Adjust:**
   - Monitor customer feedback and sales data closely after implementing price changes to make necessary adjustments.

4. **Focus on Peak Hours:**
   - Optimize staffing, inventory, and marketing spend during peak revenue hours (5:00 PM to 7:00 PM).
   - Monetize high-demand hours through dynamic pricing, with expected uplift of $1.5M–$2.5M annually.

---

## Files in the Repository

| File | Description |
|------|-------------|
| `bike_share_yr_0.csv`, `bike_share_yr_1.csv` | Raw yearly datasets |
| `cost_table.csv` | Cost & pricing table |
| `Cleaned_data.csv` | Final cleaned dataset |
| `SQL Query.sql` | SQL transformation logic |
| `Bike Data Analysis.pbix` | Power BI dashboard |
| `Dashboard.png`, `Cycle Imge.png` | Dashboard preview screenshots |
| `README.md` | Documentation |


---

## Conclusion

This project provides actionable insights into the bike shop's performance and offers strategies to enhance revenue and profitability. The interactive dashboard allows stakeholders to explore data trends and make data-driven decisions effectively.


## Authors
[![Owais Farooqui | Analyst & Data Science Enthusiast](https://img.shields.io/badge/Owais_Farooqui-Analyst_&_Data_Science-1F425F?style=flat&logo=tableau&logoColor=white)](https://github.com/Strik3r10)
[![LinkedIn](https://img.shields.io/badge/Connect-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/owais-farooqui-942281256/)
