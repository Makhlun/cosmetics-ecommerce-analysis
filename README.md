# Cosmetics Store – E-commerce Analysis (Oct 2019 – Feb 2020)
End-to-end analysis of a cosmetics online store using the OSEMN framework – from raw data cleaning through SQL-based exploration to a final Tableau dashboard.

## (!) _Metric Corrections (May 2026)_

After republishing this project I audited the key metrics and found three calculation errors. 
All have been corrected in the notebook and dashboard.

| Metric | Original | Corrected | What was wrong |
|---|---|---|---|
| Average Order Value | $4.94 | $40.79 | Averaged item-level price per purchase event instead of session-level basket total |
| Repeat Buyer Rate | 6.04% | 21.09% | Denominator was all users (including non-buyers); should be buyers only. Also counted purchase events instead of distinct purchase sessions per user |
| Funnel conversion | Event-count ratios | Session-based flags | Counted raw events instead of unique sessions reaching each stage |

**The pattern:** the SQL ran without errors and produced numbers that looked reasonable — 
which is exactly why these bugs are dangerous. The fix in each case was asking 
*"what should this number actually represent?"* before writing the query.

## Executive Summary
The cosmetics store has 1,639,151 unique users across 5 months. Of 110,518 users who made at least one purchase, 21.09% returned for a second — indicating moderate retention with room to improve. A 52.87% cart abandonment rate suggests friction in the checkout process that requires further investigation. Purchase activity peaks on Thursdays, with weekends being the least active days.

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
|21.09% of users repeat purchases|Introduce loyalty program to convert one-time buyers into regulars|
|November 2019 peak revenue ($1.53M)|Analyze what drove November growth – likely pre-holiday demand. Plan targeted campaigns ahead of the same period next year|
|The peak of activities on Thursday|Schedule promotions on Thursday|
|3.64% session-to-purchase conversion|The view-to-cart drop (23% proceed) is the largest funnel gap — reducing friction here has the highest revenue impact|
|Average order value of $40.79|Introduce "frequently bought together" recommendations to increase basket size further|

## Dashboard
Interactive dashboard built in Tableau visualizing key metrics, revenue trends, funnel analysis, and purchase activity patterns.

_**Note:**_ Dashboard built on pre-aggregated data exports due to Tableau Public's 15M row limit on the raw dataset. Interactive filtering not available as a result.

[View Dashboard](https://public.tableau.com/app/profile/mariia.makhlun/viz/visualization_17750556200000/Dashboard1?publish=yes)

<img width="1699" height="892" alt="image" src="https://github.com/user-attachments/assets/025c6f74-0ee9-45e2-9b26-d3ed5adad9e3" />


## Limitations

- Dataset covers only 5 months (Oct 2019 – Feb 2020); seasonal patterns cannot be confirmed without a full year
- No user demographics available — cannot segment conversion or retention by user characteristics
- Revenue figures reflect item prices at event time; no information on returns or cancellations of purchases

## Next Steps
- Cart abandonment by brand — which brands have the highest removal rate?
- Hour-of-day analysis — which hours drive the most purchases?
- Price sensitivity — do higher-priced items have lower conversion rates?
