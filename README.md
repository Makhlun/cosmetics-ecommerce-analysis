# Cosmetics Store – E-commerce Analysis (Oct 2019 – Feb 2020)
End-to-end analysis of a cosmetics online store using the OSEMN framework – from raw data cleaning through SQL-based exploration to a final Tableau dashboard.

## Executive Summary
The cosmetics store has 1,639,151 unique users across 5 months, yet only 6.04% made repeat purchases – indicating a retention problem. A 52.87% cart abandonment rate suggests friction in the checkout process that requires further investigation. Purchase activity peaks on Thursdays, with weekends being the least active days.

## Business Problem
- Where are users dropping off in the purchase funnel?
- Which brands drive the most revenue?
- When are users the most active?
- How well is the store retaining buyers for repeat purchases?
  
## Methodology
The project follows OSEMN framework, which stands for Obtain, Scrub, Explore, Model, and Interpret. However, the Modeling step was intentionally reframed to Metrics to define and calculate key business metrics such as conversion rates, revenue, and retention. This approach better serves the business questions posed in this analysis than predictive modeling would.

## Skills
- **Tools:** Python, pandas, DuckDB, SQL, Tableau, Jupyter Notebook.
- **Data Processing:** Data cleaning, dtype optimization, handling missing values, datetime parsing, deduplication.
- **Analysis:** Exploratory data analysis, funnel analysis, aggregations, window functions, subqueries.
- **Visualization:** Dashboard design, KPI reporting, business storytelling with data.

## Results & Business Recommendations
|Insight|Recommendation|
|----|----|
|52.87% cart abandonment rate|Investigate checkout process,  consider cart reminder emails or simplified checkout flow|
|6.04% of users repeat purchases|Introduce loyalty program|
|November 2019 peak revenue ($1.53M)|Analyze what drove November growth – likely pre-holiday demand. Plan targeted campaigns ahead of the same period next year|
|The peak of activities on Thursday|Schedule promotions on Thursday|
|13.32% view-to-purchase conversion rate| Analyze drop-off points between cart and purchase – reducing friction here has the highest revenue impact|
|Average order value of $4.94| Introduce product bundles or "frequently bought together" recommendations to increase basket size|

## Dashboard
Interactive dashboard built in Tableau visualizing key metrics, revenue trends, funnel analysis, and purchase activity patterns.

_**Note:**_ Dashboard built on pre-aggregated data exports due to Tableau Public's. 15M row limit on the raw dataset. Interactive filtering not available as a result.

[View Dashboard](https://public.tableau.com/app/profile/mariia.makhlun/viz/visualization_17750556200000/Dashboard1?publish=yes) or see the results here:


<img width="1280" height="639" alt="image" src="https://github.com/user-attachments/assets/05b04d6e-355e-484b-a098-46b73a534dc0" />


## Next Steps
- Cart abandonment dive-in by brand – Which brands have the highest removal rate?
- Hour-of-day analysis – Which hours are the most popular to purchase?
- Price sensitivity – Do higher prices lead to lower conversion rates?
