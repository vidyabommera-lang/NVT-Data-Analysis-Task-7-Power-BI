# Task 7 - Power BI Complete Solution Guide

## Dataset used
`train.csv` supplied for this task.

Dataset size: **9,800 rows x 23 original columns**.

## Important dataset limitation
This dataset contains **Sales**, but it does NOT contain Profit or Quantity. Therefore, the dashboard uses:
- Total Sales
- Total Orders
- Total Customers
- Average Order Value
- Average Shipping Days
- Sales by Category
- Sales by Region
- Sales by Segment
- Monthly Sales Trend
- Top Sub-Categories

This is preferable to inventing unavailable business measures.

## Dashboard layout

### KPI Cards
1. Total Sales
2. Total Orders
3. Total Customers
4. Average Order Value

### Charts
1. Bar chart: Sales by Category
2. Bar chart: Sales by Region
3. Line chart: Monthly Sales Trend
4. Donut chart: Sales by Segment
5. Bar chart: Top 10 Sub-Categories
6. Optional map/bar chart: Sales by State

### Slicers
- Order Year
- Region
- Category
- Segment
- Ship Mode

## Actual results from the uploaded dataset
- Total Sales: **$2,261,536.78**
- Total Orders: **4,922**
- Total Customers: **793**
- Average Order Value: **$459.48**
- Average Shipping Days: **107.01 days**
- Highest-sales category: **Technology**
- Highest-sales region: **West**
- Highest-sales segment: **Consumer**
- Highest-sales month: **NaT ($1,389,173.66)**
- Highest-sales sub-category: **Phones**

## Build steps
1. Open Power BI Desktop.
2. Get Data -> Text/CSV.
3. Load `Dataset/train_cleaned_powerbi.csv`.
4. Select Transform Data and confirm data types.
5. Close & Apply.
6. Rename the table to `Sales`.
7. Create the DAX measures in `DAX_Measures.md`.
8. Create the KPI cards.
9. Add the bar/line/donut charts.
10. Add slicers.
11. Format Sales and Average Order Value as currency.
12. Test all slicers.
13. Save as `Task7_Business_Intelligence_Dashboard.pbix`.
14. Export the report to PDF from Power BI.
15. Take screenshots of the dashboard.
16. Upload the final files to GitHub.

## Power BI interview questions
### What is BI?
Business Intelligence is the process of turning business data into information and insights that support decision-making.

### What is Power BI?
Power BI is Microsoft's business analytics and visualization platform.

### What is Power Query?
Power Query is used to connect, clean, transform and prepare data.

### What is DAX?
DAX (Data Analysis Expressions) is the formula language used in Power BI for measures and calculated columns.

### Measure vs Calculated Column
A measure is calculated dynamically based on the filter context. A calculated column is computed row-by-row and stored in the model.

### What are KPIs?
KPIs are key performance indicators used to monitor important business metrics.

## Submission note
A native `.pbix` file must be saved from Power BI Desktop. It cannot be generated reliably outside the Power BI application. All other supporting files in this package are prepared from the uploaded dataset.
