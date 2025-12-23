#  Bangalore Taxi Fare Prediction – End-to-End Databricks Pipeline

This project demonstrates an end-to-end data engineering and machine learning pipeline built using Azure Databricks and PySpark, following the **Medallion Architecture (Bronze, Silver, Gold).

I built an end-to-end taxi fare prediction pipeline using Azure Databricks, following the Medallion architecture, and deployed batch ML predictions using Spark ML.

---

## Project Overview

The goal of this project is to analyze Bangalore taxi trips and predict taxi fares using historical trip data.  
The pipeline ingests raw data, cleans and enriches it, trains a regression model, and generates batch predictions for analytics.

---

## Architecture

**Bronze**
- Raw taxi trip CSV ingestion
- No transformations (source of truth)

**Silver**
- Data cleaning (nulls, duplicates)
- Feature engineering:
  - Trip distance (Haversine formula)
  - Trip duration
  - Hour, day of week, month
- Percentile-based outlier handling
- Stored as Delta table

**Gold**
- Machine Learning model training (Spark ML – Linear Regression)
- Model evaluation (RMSE, R²)
- Batch inference
- Gold predictions table with actual vs predicted fares

---

## Tech Stack

- Azure Databricks
- PySpark & Spark SQL
- Delta Lake
- Spark MLlib
- Azure Blob Storage
- Python

---

##  Model Performance

| Metric | Value |
|------|------|
| RMSE | ~₹32 |
| R² | ~0.94 |

---

##  Repository Structure

taxi-fare-prediction-databricks/
│
├── notebooks/
│ ├── 00-setup.ipynb
│ ├── 01-bronze-ingest.ipynb
│ ├── 02-silver-transform.ipynb
│ ├── 03-train-model.ipynb
│ └── 04-batch-score-gold.ipynb
│
├── data/
│ └── taxi_bangalore_10000.csv
│
├── README.md

## Author

Anjali Ledade
www.linkedin.com/in/anjali-ledade-a94984172 | https://github.com/anjaliledade18