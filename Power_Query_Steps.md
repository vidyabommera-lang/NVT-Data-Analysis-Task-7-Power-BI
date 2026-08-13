# Power Query Cleaning Steps / M Template

The uploaded dataset contains 9,800 rows and 18 original columns. There are 11 missing Postal Code values.

In Power BI:
1. Get Data -> Text/CSV -> select `train.csv`
2. Transform Data
3. Set Order Date and Ship Date to Date type using `MM/DD/YYYY`
4. Set Row ID to Whole Number
5. Set Sales to Decimal Number
6. Set Postal Code to Whole Number/Text depending on the required geographic analysis
7. Add Year/Month fields if desired
8. Check nulls and duplicates
9. Close & Apply

Example M transformation template:

```powerquery
let
    Source = Csv.Document(
        File.Contents("train.csv"),
        [Delimiter=",", Encoding=65001, QuoteStyle=QuoteStyle.Csv]
    ),
    PromotedHeaders = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    ChangedTypes = Table.TransformColumnTypes(
        PromotedHeaders,
        {
            {"Row ID", Int64.Type},
            {"Order ID", type text},
            {"Order Date", type date},
            {"Ship Date", type date},
            {"Ship Mode", type text},
            {"Customer ID", type text},
            {"Customer Name", type text},
            {"Segment", type text},
            {"Country", type text},
            {"City", type text},
            {"State", type text},
            {"Postal Code", Int64.Type},
            {"Region", type text},
            {"Product ID", type text},
            {"Category", type text},
            {"Sub-Category", type text},
            {"Product Name", type text},
            {"Sales", type number}
        },
        "en-US"
    )
in
    ChangedTypes
```

Note: if Power BI interprets the dates incorrectly, explicitly use the column's Change Type -> Using Locale -> Date -> English (United States).
