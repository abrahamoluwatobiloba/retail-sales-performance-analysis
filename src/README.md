# Source Code

This directory is reserved for reusable Python modules that support the retail sales analysis.

At the current stage, the main analysis is contained in:

```text
notebooks/retail_sales_performance_analysis.ipynb
```

As the project develops, reusable code can be moved from the notebook into this folder.

## Planned Modules

```text
src/
├── data_loader.py
├── data_cleaning.py
├── metrics.py
└── visualization.py
```

### Intended Responsibilities

| Module             | Purpose                                                                                  |
| ------------------ | ---------------------------------------------------------------------------------------- |
| `data_loader.py`   | Load and validate the raw retail dataset from `data/raw/Retail.csv`.                     |
| `data_cleaning.py` | Standardize columns, handle missing values, convert data types, and create cleaned data. |
| `metrics.py`       | Create reusable sales, discount, order, and shipment-timing metrics.                     |
| `visualization.py` | Store reusable plotting functions for project figures.                                   |

## Current Status

The project currently uses a notebook-first workflow. This directory is included to support future refactoring and to demonstrate the intended separation between raw data, analysis notebooks, reusable code, reports, and documentation.
