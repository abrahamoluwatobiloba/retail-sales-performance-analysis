# Data Guide

## Dataset

This project uses a retail transaction dataset containing product, pricing, promotion, regional, quantity, sales, tax, freight, order-date, due-date, and shipment-date fields.

The analysis uses transaction-line records. A single order number may appear in multiple rows because one order can contain more than one product.

## Dataset Source

This project uses the `Retail.csv` dataset from the public
[Retail-Sales-Analysis-EDA GitHub repository](https://github.com/tejas79883/Exploratory-Data-Analysis-EDA--Retail-Sales-Data).

The dataset contains approximately 32,041 sales records across 17
columns, covering sales activity from 2011 to 2013.

Accessed for portfolio analysis: October 2026.

### Attribution

The dataset was not collected by me. My contribution to this project
was data cleaning, exploratory data analysis, statistical analysis,
visualization, and development of business insights and recommendations.

## Raw Data Location

For local analysis, place the authorized source file in:

```text
data/raw/Retail.csv
```

The raw dataset is intentionally excluded from this repository unless its source licence explicitly permits redistribution.

## Expected File Name

```text
Retail.csv
```

## Expected Columns

The analysis expects these fields:

- `OrderNumber`
- `ProductName`
- `Color`
- `Category`
- `Subcategory`
- `ListPrice`
- `Orderdate`
- `Duedate`
- `Shipdate`
- `PromotionName`
- `SalesRegion`
- `OrderQuantity`
- `UnitPrice`
- `SalesAmount`
- `DiscountAmount`
- `TaxAmount`
- `Freight`

## Data Usage Notes

- Do not modify the file in `data/raw/`. Treat it as the original source.
- Any cleaned or transformed version of the dataset should be saved in `data/processed/`.
- Verify that you have the right to use and share the dataset before uploading any data file to GitHub.
- The source, licensing terms, and field definitions should be confirmed before using results for real business decisions.

## Reproducing the Analysis

1. Obtain `Retail.csv` from the public source repository listed above.
2. Save the file as `Retail.csv`.
3. Place it in `data/raw/`.
4. Open the project notebook.
5. Run all cells from top to bottom.
