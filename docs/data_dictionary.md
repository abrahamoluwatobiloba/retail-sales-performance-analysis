# Retail Sales Data Dictionary

| Column           | Type after preparation | Description                                                                                                           |
| ---------------- | ---------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `OrderNumber`    | Text                   | Identifier for an order. Multiple rows may share one order number because an order can contain several product lines. |
| `ProductName`    | Text                   | Name and variant of the product sold.                                                                                 |
| `Color`          | Text                   | Product colour. Missing values are labelled `Unknown` during preparation.                                             |
| `Category`       | Text                   | Broad product group, such as Bikes, Components, Clothing, or Accessories.                                             |
| `Subcategory`    | Text                   | More detailed product classification, such as Road Bikes or Mountain Frames.                                          |
| `ListPrice`      | Numeric                | Listed product price before transaction-level price adjustments.                                                      |
| `Orderdate`      | Date                   | Date on which the order was placed in the raw dataset. Renamed to `OrderDate` in the notebook.                        |
| `Duedate`        | Date                   | Expected fulfilment due date in the raw dataset. Renamed to `DueDate` in the notebook.                                |
| `Shipdate`       | Date                   | Actual shipment date in the raw dataset. Renamed to `ShipDate` in the notebook.                                       |
| `PromotionName`  | Text                   | Promotion associated with the transaction line, including `No Discount`.                                              |
| `SalesRegion`    | Text                   | Region associated with the transaction.                                                                               |
| `OrderQuantity`  | Integer                | Number of units in the transaction line.                                                                              |
| `UnitPrice`      | Numeric                | Actual unit selling price.                                                                                            |
| `SalesAmount`    | Numeric                | Total sales amount for the transaction line.                                                                          |
| `DiscountAmount` | Numeric                | Discount amount applied to the transaction line.                                                                      |
| `TaxAmount`      | Numeric                | Tax amount recorded for the transaction line.                                                                         |
| `Freight`        | Numeric                | Freight or shipping amount recorded for the transaction line.                                                         |

## Derived Fields in the Notebook

| Derived field       | Formula / definition                    | Purpose                                                       |
| ------------------- | --------------------------------------- | ------------------------------------------------------------- |
| `GrossListValue`    | `ListPrice × OrderQuantity`             | Approximate list-value amount before discounts.               |
| `GrossAtUnitPrice`  | `UnitPrice × OrderQuantity`             | Validates the relationship to transaction-line sales.         |
| `PromoDiscountRate` | `DiscountAmount ÷ GrossListValue`       | Estimates discount relative to list-value amount where valid. |
| `OrderToShipDays`   | `ShipDate − OrderDate`                  | Measures elapsed days between order and shipment.             |
| `OrderToDueDays`    | `DueDate − OrderDate`                   | Measures the planned fulfilment window.                       |
| `ShipVsDueDays`     | `ShipDate − DueDate`                    | Negative values indicate shipment before the due date.        |
| `ShipmentStatus`    | Derived from `ShipVsDueDays`            | Classifies records as shipped before, on, or after due date.  |
| `OrderYear`         | Year extracted from `OrderDate`         | Supports annual summaries.                                    |
| `OrderMonth`        | Month number extracted from `OrderDate` | Supports seasonal/monthly summaries.                          |
| `OrderMonthName`    | Month name extracted from `OrderDate`   | Supports readable month labels.                               |
| `OrderYearMonth`    | Year-month extracted from `OrderDate`   | Supports monthly trend analysis.                              |

## Important Interpretation Notes

- The data is transaction-line level, not necessarily order level.
- `SalesAmount`, `TaxAmount`, and `Freight` appear strongly related in the source dataset. Correlations among them should not be treated as causal relationships.
- The dataset does not include product cost, profit, gross margin, returns, actual delivery dates, customer details, or marketing spend.
- Shipment timing is not the same as final delivery performance.
