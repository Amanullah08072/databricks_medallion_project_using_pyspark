# Databricks Medallion Architecture Data Engineering Pipeline

An end-to-end Data Engineering project implementing Medallion Architecture (Bronze/Silver layers), batch ETL, and real-time streaming pipelines using **PySpark**, **Spark Structured Streaming**, and **Delta Lake** on **Databricks**.

---

## 🏗️ Architecture & Features

This repository (`databricks_medallion_project_using_pyspark`) implements modularized data transformation scripts and fault-tolerant streaming pipelines for e-commerce transactional data:

* **Modular Ingestion & Extraction**: Custom scripts for extracting data from DBFS Volumes, raw files, and external sources (Membership, Addresses, Refunds, Orders, Payments).
* **Medallion Data Transformations**: PySpark transformations handling JSON parsing, array exploding, schema enforcement, joins, and monthly aggregations.
* **Spark Structured Streaming**: Real-time stream processing with **Checkpointing** and **Write-Ahead Logs (WAL)** for fault-tolerant state management.
* **Idempotent Write Sinks**: Exactly-once processing guarantees when appending streaming records to Delta Lake.
* **Databricks Integration**: Notebook-driven ETL design managed with Git integration and Unity Catalog governance.

---

## 📂 Repository Structure

```text
databricks_medallion_project_using_pyspark/
│
├── project_using_pyspark/
│   ├── py 03 Extract Customer Data.py
│   ├── py 04 Extract Orders Data.py
│   ├── py 05 Extract Data From Membership.py
│   ├── py 06 Extract Data From Addresses.py
│   ├── py 07 Payment Data.py
│   ├── py 071 Refunds.py
│   ├── py 10 Transform Customer Data.py
│   ├── py 11 Transform Payments Data.py
│   ├── py 12 Transform Refunds Data.py
│   ├── py 13 Transform Membership Data.py
│   ├── py 14 Transform addresses.py
│   ├── py 15 Play with Orders Json.py
│   ├── py 16 Transform Orders Data.py
│   ├── py 17 Transform Orders Data - Explode Arrays.py
│   ├── py 18 Join Customer and Addresses.py
│   └── py 19 Monthly Order Summary.py
│
├── Spark Structured Streamming/
│   ├── Ingest Customer Stream.py
│   └── Unity Catalog Integration.py
│
└── README.md