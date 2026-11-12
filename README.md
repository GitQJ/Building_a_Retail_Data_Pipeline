# Building_a_Retail_Data_Pipeline
Retail Sales ETL Pipeline: Merging SQL &amp; Parquet Data into Clean, Analysis-Ready CSVs | Python, pandas, SQL

## Building a Retail Data Pipeline

Built a modular ETL pipeline that merges retail sales from a PostgreSQL table and a Parquet file, cleans the result and loads analysis-ready CSVs, including average weekly sales by month.

# CONTEXT
Retail sales swing around public holidays, so analysts need clean, consistent data before they can study supply and demand. The brief was to turn two raw sources (store sales and complementary data such as CPI, unemployment and holiday flags) into reusable outputs.

# MY ROLE
The SQL query and extract step were provided. I wrote the transform, aggregation, load and validation functions.

# WHAT I DID
• Transform: filled missing numeric values with column means, dropped rows without a date, derived a Month column, kept weeks with sales over $10,000 and reduced the data to 7 analysis columns
• Aggregate: grouped by month to compute average weekly sales
• Load: wrote clean_data.csv and agg_data.csv without an index through a reusable function that takes output paths as arguments
• Validate: added a check that both output files exist in the working directory
• Kept each stage as its own function (extract, transform, aggregate, load, validate) so it can be tested and rerun

# RESULTS
• Merged 231522 raw rows into 106206 clean rows after filtering (125277 rows removed by the $10K rule)
• Monthly averages range from 32,736.99 in October to 39238.8 in December
• Both output files created and confirmed by the validation step

# TECH STACK
Python, pandas, SQL (PostgreSQL), Parquet, ETL design
