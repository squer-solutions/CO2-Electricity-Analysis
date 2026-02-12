# Data Engineering Challenge: Multi-Layer ETL Pipeline

## Goal

Build a simplified medallion architecture pipeline (Bronze/Silver/Gold) using PySpark that works across multiple platforms: local PySpark, Databricks, BigQuery, or other cloud services.

This is a 30-minute exercise. Focus on core concepts and working code over perfection.

## Dataset

`datasets/annual-co2-emissions-per-country.csv` — CO2 emissions by country and year

## Task

Build a simple pipeline with two layers (Bronze → Silver is sufficient; Gold is optional):

### Bronze Layer (Raw Ingestion)

- Read CSV data as-is
- Add one metadata column: `loaded_at` (current timestamp)
- Write to structured format (Parquet, Delta, or table)

### Silver Layer (Cleaned)

- Filter data to years 2000–2023 only
- Remove any rows with null `country_code`, `year`, or `co2_emissions`
- Ensure no duplicate combinations of `country_code` + `year`
- Write to structured format

### Gold Layer (Optional Bonus)

- If time permits: Create a simple aggregation (e.g., total CO2 by year or by country)

## Incremental Load (Optional)

If you finish early, demonstrate how you would handle new data arriving (e.g., year 2024 data).

## Data Quality Checks

- **No duplicate keys** in Silver layer (unique on `country_code` + `year`)
- **No nulls** in required columns (`country_code`, `year`, `electricity_access`, `co2_emissions`)
- **Valid ranges:** electricity access values between 0 and 100

## Platform Flexibility

You are free every platform or service. 
- **Local:** PySpark with Parquet or Delta Lake (if available)
- **Databricks:** Native Delta Lake support
- **BigQuery:** PySpark via BigQuery connectors, or SQL-based approach
- **Other platforms:** Abstract storage layer to support different backends

Consider parametrizing table locations/URIs rather than hardcoding them.

## Deliverables
- Clear comments explaining each layer and data transformations
- Brief instructions on how to run (1-2 sentences)
- Output data files or tables

## Technical Provisioning

It is not required to use Python! However, if you want to make use of PDM

```bash
curl -sSL https://pdm-project.org/install-pdm.py | python3 -
pdm install
```

You will find the interpreter in `.venv/bin/python`


### Spark Server
The Python environment already contains a PySpark package. You could start your implementation with this code:
```python 
# %% [markdown]
# # Data Engineering Challenge: Medallion Architecture ETL
#
# **Run instructions:** Execute cells sequentially. Requires PySpark 3.5.0
#
# Uses local PySpark with Parquet files (Bronze → Silver → Gold layers)

# %%
from pyspark.sql import SparkSession
from pyspark.sql.functions import (
    col,
    current_timestamp,
    sum as spark_sum,
    count,
    max as spark_max,
)
from pathlib import Path

# Initialize Spark in local mode
spark = (
    SparkSession.builder.appName("CO2_ETL_Pipeline").master("local[*]").getOrCreate()
)

print(f"Spark {spark.version} initialized")

# %%
# Define paths
BASE_DIR = Path("datasets")
OUTPUT_DIR = Path("output")
OUTPUT_DIR.mkdir(exist_ok=True)

SOURCE_FILE = BASE_DIR / "annual-co2-emissions-per-country.csv"
BRONZE_PATH = OUTPUT_DIR / "bronze_co2"
SILVER_PATH = OUTPUT_DIR / "silver_co2"
GOLD_PATH = OUTPUT_DIR / "gold_co2_summary"
```

As an alternative, you can also start your local Spark instance using Docker. Take a look in the spark-local folder and run `docker compose up` if you like to do so. 
