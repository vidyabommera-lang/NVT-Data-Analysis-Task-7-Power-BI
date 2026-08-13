# Task 7 - DAX Measures

> Dataset note: the uploaded `train.csv` contains Sales but does not contain Profit or Quantity columns. Therefore, the measures below use only fields that actually exist in the dataset.

```DAX
Total Sales =
SUM(Sales[Sales])

Total Orders =
DISTINCTCOUNT(Sales[Order ID])

Total Customers =
DISTINCTCOUNT(Sales[Customer ID])

Average Order Value =
DIVIDE([Total Sales], [Total Orders], 0)

Average Shipping Days =
AVERAGEX(
    Sales,
    DATEDIFF(Sales[Order Date], Sales[Ship Date], DAY)
)

Sales YTD =
TOTALYTD(
    [Total Sales],
    Sales[Order Date]
)
```

## Optional Date Table

```DAX
DateTable =
CALENDAR(
    MIN(Sales[Order Date]),
    MAX(Sales[Order Date])
)

Year = YEAR(DateTable[Date])
Month Number = MONTH(DateTable[Date])
Month = FORMAT(DateTable[Date], "MMM")
Year Month = FORMAT(DateTable[Date], "YYYY-MM")
```

After creating `DateTable`, create a relationship:
`DateTable[Date]` -> `Sales[Order Date]`.

## Important
Do NOT create Profit or Profit Margin measures for this dataset unless a Profit column is added from a valid source. The uploaded file has no Profit field.
