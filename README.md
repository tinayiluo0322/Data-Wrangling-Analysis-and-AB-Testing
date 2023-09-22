# Data-Wrangling-Analysis-and-AB-Testing

The provided SQL code in this project follows a structured A/B testing workflow:

**Step 1 - Data Comparison and Assessment:**
- The first step in the workflow involves comparing the `final_assignments_qa` table to assignment events captured for user-level testing.
- The primary objective is to assess whether the `final_assignments_qa` table contains all the necessary data for computing metrics like the 30-day view-binary.
- The analysis reveals that the critical `created_at` date is missing from the table, which is essential for metric computation.

**Step 2 - Data Transformation:**
- In response to the data inadequacy discovered in Step 1, a data transformation step is initiated.
- A query and table creation statement are formulated to make the `final_assignments_qa` table resemble the structure of the `final_assignments` table.
- In cases where data is missing, placeholders of the appropriate data type are introduced.

**Step 3 - Order Binary Calculation:**
- Leveraging the transformed data, the workflow moves on to calculating the order binary for the 30-day window following the test assignment for `item_test_2`.
- This calculation includes the day the test started and is based on the `final_assignments` table.

**Step 4 - View Binary and Average Views Calculation:**
- Similar to Step 3, a query is constructed to compute the view binary and average views for the 30-day period after the test assignment for `item_test_2`.
- The calculation accounts for the day the test started and utilizes both the `final_assignments` and `view_item_events` tables.

**Step 5 - Statistical Analysis:**
- Statistical analysis is performed using the [ABBA test calculator](https://thumbtack.github.io/abba/demo/abba.html).
- The focus is on computing the lifts in metrics and p-values for the binary metrics, specifically the 30-day order binary and 30-day view binary.
- A 95% confidence interval is used for this analysis, and the results help assess the significance of the metrics.

**Step 6 - Reporting and Interpretation:**
- The final step involves generating a report using Mode’s Report Builder feature.
- This report includes a title, graphical representations of the two binary metrics, lift values, p-values obtained from the AB test calculator, and comprehensive interpretations of the results.
- Both the 30-day order binary and 30-day view binary metrics are presented and explained in terms of their significance.

In summary, this workflow outlines a rigorous process for conducting A/B testing, from data comparison and transformation to statistical analysis and comprehensive reporting. 
