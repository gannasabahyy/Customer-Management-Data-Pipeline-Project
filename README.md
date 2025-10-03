# Customer-Management-Data-Pipeline-Project
# Customer Management & Analytics Data Platform

A comprehensive data engineering and business intelligence project that builds a modern data pipeline to analyze customer behavior, predict churn, and calculate customer lifetime value (CLV).

## 📊 Project Overview

This project demonstrates the design and implementation of a complete data ecosystem - from raw data ingestion to actionable business insights. The system integrates multiple data sources (customer data, usage logs, transactions, offers, and support tickets) into a centralized data warehouse, enabling advanced customer analytics and churn prediction.

**Business Goal:** Improve customer churn prediction and lifetime value (CLV) analysis while providing a single source of truth for customer reporting and dashboards.

## 🏗️ Architecture

The architecture follows a data lakehouse pattern combining raw data ingestion, structured warehousing, and analytics:
Data Sources → Ingestion Layer → Storage Layer → Processing Layer → BI Layer

### Technology Stack

- **Data Engineering:** Sqoop, NiFi, HDFS, Hive, Hue
- **Business Intelligence:** Power BI Direct Query
- **Data Modeling:** Star Schema / Fact Constellation

## 📁 Data Pipeline Architecture

### 1. Data Ingestion Layer

**Apache Sqoop:** Imports relational data from MariaDB into HDFS and Hive
`bash
sqoop import --connect jdbc:mysql://localhost/SIC --table customers --as-parquetfile --target-dir /warehouse/customers

Apache NiFi: Ingests semi-structured/unstructured data (JSON) and pushes to HDFS

GetFile Processor: Reads JSON files from local directory

ConvertRecord Processor: Converts JSON to Parquet format

PutHDFS Processor: Writes processed data to HDFS

###2. Storage & Processing Layer
HDFS: Distributed storage for raw and processed data
Hive: Data warehousing and SQL-based processing
Hue: Web interface for data exploration and query execution

###3. Data Modeling
The data warehouse uses a Star Schema with the following structure:

Fact Tables
fact_customer_activity - Detailed customer actions and interactions

fact_customer_metrics - Customer-level performance metrics and KPIs
Dimension Tables
dim_customer - Customer demographics and attributes

dim_usage - Product usage and engagement data

dim_offer - Marketing campaigns and offers

dim_support_ticket - Customer support interactions
