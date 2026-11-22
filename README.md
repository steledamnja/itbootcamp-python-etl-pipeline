# Northern Star Shop — ETL Pipeline

## Project Overview

This project implements an ETL pipeline to analyze football merchandise sales and investigate whether match results influence sales.

The pipeline combines store data with Northern Star League (NSL) match results using Python and Pandas.

## Data Sources

- Orders — JSON API
- Products — CSV
- Teams — CSV
- Matches — Parquet

## ETL Process

### 1. Extract
- Retrieve orders from a paginated API.
- Download product, team, and match data.
- Save original files in `data/raw/`.

### 2. Transform
- Clean and standardize data.
- Remove duplicate orders.
- Validate orders and separate valid and rejected records.
- Calculate order totals.
- Combine orders with product information.
- Calculate league standings and team performance.
- Analyze sales during the three days following match results.

### 3. Load
- Save processed datasets in `data/processed/`.
- Export results as CSV and Parquet files.

## Pipeline Results

| Metric | Value |
|---|---:|
| Total orders | 1,852 |
| Duplicate orders | 12 |
| Valid orders | 1,800 |
| Rejected orders | 52 |
| Total revenue | 10,045,400 RSD |
| Generated output files | 8 |

## Output Files

- `clean_orders.parquet` — Valid and transformed orders
- `rejected_orders.csv` — Rejected orders and rejection reasons
- `products.csv` — Cleaned product catalog
- `league_table.csv` — Football league standings
- `revenue_by_team.csv` — Revenue by football team
- `revenue_by_category.csv` — Revenue by product category
- `sales_after_results.csv` — Sales analysis by match result
- `summary.csv` — Pipeline execution summary

## Project Structure

```text
data/
├── raw/
│ ├── orders.json
│ ├── products.csv
│ ├── teams.csv
│ └── matches.parquet
└── processed/
├── clean_orders.parquet
├── rejected_orders.csv
├── products.csv
├── league_table.csv
├── revenue_by_team.csv
├── revenue_by_category.csv
├── sales_after_results.csv
└── summary.csv

pipeline.ipynb
README.md
```

## Technologies

- Python
- Pandas
- Requests
- JSON
- CSV
- Parquet
- Databricks
- Git and GitHub

## How to Run

1. Open `pipeline.ipynb` in Databricks.
2. Install or enable the required Python libraries.
3. Run all notebook cells in order.
4. Check the generated files in `data/raw/` and `data/processed/`.

## Conclusion

The pipeline successfully processes 1,852 orders, identifies 12 duplicates, validates 1,800 orders, and generates reports connecting merchandise sales with football match results.

The project demonstrates a complete ETL workflow, from data extraction and cleaning to transformation, validation, and analytical reporting.