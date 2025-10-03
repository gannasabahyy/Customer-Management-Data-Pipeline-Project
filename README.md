# Customer Analytics & Churn Prediction Platform

A data engineering project that builds a complete data pipeline for customer behavior analysis and churn prediction.

## 📊 Overview

- **Business Problem:** 35% monthly customer churn rate requiring data-driven solutions
- **Solution:** Built end-to-end data pipeline from ingestion to actionable insights
- **Key Findings:** Identified high churn in young customers (18-29), critical support issues causing 100% churn, and CLV drivers

## 🏗️ Architecture
Data Sources → Sqoop/NiFi → HDFS → Hive → Power BI

**Technology Stack:** Sqoop, NiFi, HDFS, Hive, Hue, Power BI  
**Data Model:** Star Schema with fact and dimension tables

## 📈 Key Insights

- **35% monthly churn rate** - critical business emergency
- **Young customers (18-29)** are churning at 100% in some regions
- **High-severity support issues** (ATM failures, mobile token issues) cause 100% churn
- **Savings & Cashback products** drive highest customer lifetime value

## 🚀 Quick Start

1. Ingest data: `sqoop import --connect jdbc:mysql://localhost/SIC --table customers`
2. Create Hive tables (see `/sql/schema.sql`)
3. Run analysis queries (see `/sql/analysis_queries.sql`)
4. Connect Power BI for dashboards

## 📁 Project Structure
├── sql/ # Hive schema & analysis queries
├── nifi/ # Data flow templates
├── docs/ # Detailed documentation
└── powerbi/ # Dashboard files
