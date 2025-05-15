# Customer-Lifetime-Value-CLV-Analysis

# Project Overview
The objective is to estimate the Customer Lifetime Value (CLV) of customers using a dataset of ~8000 transaction records (customer_sales.csv) spanning 2011 to 2014. CLV represents the predicted net profit from a customer over their entire relationship with a business, emphasizing long-term customer value over short-term profits. The project analyzes customer spending patterns by cohort (based on acquisition year), calculates historic CLV, and provides business insights to improve customer retention and acquisition strategies.
Methodology
The analysis follows a structured seven-step approach using Python in a Jupyter Notebook (CLV_Analysis.ipynb):

# Understand the Dataset:

Load the customer_sales.csv dataset using pandas.
Identify missing values, date ranges (2011-01-01 to 2014-12-31), unique customers (792), unique orders (4117), and sales statistics (e.g., min: -110.0, max: 206000.0, std dev: 3218.07).
Assess sales trends over time using a line graph to check for increases (e.g., due to inflation).


## Explore the Dataset:

Detect outliers in the Sales column (e.g., values like 206000.0 and 198000.0) using descriptive statistics.
Analyze the impact of discounts on sales and profits (partially implemented).
Investigate factors affecting sales via regression (partially implemented).


## Determine Origin Year of Customers:

Group customers into cohorts based on their first transaction year (2011–2014) by finding the earliest Order Date for each customer using pandas grouping.


## Calculate Cumulative Transaction Amounts:

Compute cumulative sales for each cohort at customer ages of 0, 12, 24, and 36 months by summing transactions within the respective time periods since the origin year.


## Calculate the Number of New Customers:

Determine the number of new customers per origin year, ensuring consistency across age intervals (e.g., same count at 12, 24, 36 months for each cohort).


## Historic CLV Calculation:

Calculate historic CLV by dividing cumulative transaction amounts by the number of new customers for each cohort and age interval.
Visualize CLV trends for each cohort using matplotlib.
Compute a volume-weighted average CLV curve by weighting cohort CLVs by the number of customers in each cohort, resulting in values like [872.20, 1602.10, 2383.51, 3208.32].


## Interpret Results:

Analyze spending patterns: Older cohorts (2011, 2012) show higher CLV (e.g., 3208.32 for 2011 at 36 months) and sustained engagement, while newer cohorts (2013, 2014) decline rapidly, indicating retention issues.
Provide business insights: Recommend loyalty programs for high-value cohorts and retention strategies (e.g., onboarding, personalized engagement) for newer cohorts.



This methodology ensures a comprehensive CLV analysis, combining data exploration, cohort-based calculations, and actionable insights for business decision-making.
