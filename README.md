# Clinical Trials & Drug Analytics Platform

## 📌 Project Overview

This project implements an end-to-end data engineering pipeline on Azure to process and analyze clinical trials data, including drugs, patients, studies, and outcomes. The pipeline follows a layered architecture (Bronze, Silver, Gold) to transform raw data into business-ready insights.

---

## 🏗️ Architecture

Source Data (CSV) → Azure Data Factory → Azure Data Lake (Bronze) → Azure Databricks (Silver & Gold) → Power BI

---

## 🟤 Bronze Layer (Raw Ingestion)

* Ingests raw CSV data into Azure Data Lake using Azure Data Factory.
* Stores data in Delta format without transformation.
* Captures ingestion logs such as record count, pipeline status, and timestamps.

---

## ⚪ Silver Layer (Data Processing & Engineering)

* Performs data cleaning (null handling, duplicate removal).
* Applies data standardization and schema validation.
* Joins multiple datasets (trial, drug, patient, timeline, outcomes).
* Implements **SCD Type 2** for dimension tables (e.g., patient) to track historical changes.
* Adds derived columns such as treatment duration and age group.
* Stores invalid records in quarantine tables.
* Logs transformation status and processed record counts.

---

## 🟡 Gold Layer (Analytics & Modeling)

* Designs a **star schema** with:

  * Fact Table: `fact_trial`
  * Dimension Tables: `dim_patient`, `dim_drug`
* Performs aggregations to generate business KPIs:

  * Drug success rate
  * Patient distribution
  * Cost per study
* Optimized for reporting and analytics.
* Logs final output metrics.

---

## 🔍 Data Quality & Governance

* Null and duplicate validation in Silver layer.
* Quarantine tables for bad data.
* Schema enforcement using Delta Lake.

---

## 🔄 Incremental Processing (Planned Enhancement)

* Supports incremental loading using `last_run_time`.
* Ensures only new or updated records are processed.

---

## 📊 Reporting

* Gold layer data is consumed by Power BI dashboards for:

  * Clinical trial performance
  * Drug effectiveness analysis
  * Patient insights

---

## 🧾 Logging & Monitoring

* Centralized logging table capturing:

  * Pipeline name
  * Layer (Bronze/Silver/Gold)
  * Record counts
  * Status (Success/Failure)
  * Execution timestamps
* Enables monitoring and debugging of pipeline runs.

---

## 🛠️ Technologies Used

* Azure Data Factory
* Azure Data Lake Storage Gen2
* Azure Databricks (PySpark)
* Delta Lake
* Power BI

---

## 🚀 Key Highlights

* End-to-end pipeline design
* Scalable layered architecture
* Implementation of SCD Type 2
* Data quality and validation framework
* Star schema modeling for analytics
* Logging and monitoring for production readiness

---

## 📈 Future Improvements

* Full implementation of incremental pipelines
* Advanced CI/CD using Azure DevOps
* Real-time streaming integration
* Enhanced monitoring with Azure Monitor

---
