# clinical-trials-analytics-platform

## Overview
This project builds an end-to-end data engineering pipeline on Azure for analyzing clinical trials data including drugs, patients, and study outcomes.

## Architecture
ADF → ADLS (Bronze) → Databricks (Silver & Gold) → Power BI

## Layers
- Bronze: Raw data ingestion
- Silver: Cleaned and transformed data
- Gold: Business KPIs

## Technologies
- Azure Data Factory
- Azure Data Lake
- Databricks (PySpark)
- Delta Lake
- Power BI

## Use Cases
- Drug success rate
- Patient distribution
- Study performance
- Cost analysis