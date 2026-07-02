# Databricks LakeFlow Spark Declarative Pipeline

This project implements a medallion-style transportation analytics pipeline using Databricks LakeFlow and Spark Declarative Pipelines. It ingests raw trip files, standardizes them into Bronze and Silver layers, and produces Gold-level city analytics for downstream BI and operational reporting.

## What This Project Does

- Ingests trip and city data with Auto Loader
- Applies schema cleanup and data quality checks
- Uses streaming tables and CDC-style upserts
- Builds Silver and Gold layers for analytics
- Organizes city-level reporting SQL for downstream dashboards

## Architecture

![Databricks Workflow Architecture](3.%20other_files/architecture.png)

![Pipeline Graph](3.%20other_files/pipeline.png)

## Repository Structure

- `1. data/`: raw and incremental transportation datasets
- `2. codes/bronze/`: raw ingestion jobs
- `2. codes/silver/`: cleaned and validated transformation jobs
- `2. codes/gold/`: analytics-ready SQL models by city
- `2. codes/project_setup.ipynb`: setup notebook for the workspace
- `3. other_files/`: architecture images and supporting assets

## Technical Highlights

- `bronze/trips.py` uses Databricks Auto Loader against cloud object storage
- `silver/trips.py` standardizes fields, adds quality expectations, and creates an auto-CDC flow
- Gold SQL models split analytics by city for controlled access and reporting

## Skills Demonstrated

- Databricks LakeFlow pipeline design
- Spark streaming ingestion
- Medallion architecture implementation
- Data quality rules and expectations
- CDC-style upsert modeling
- SQL analytics engineering

## Potential Use Cases

- City-wise transportation operations reporting
- BI dashboards and executive KPI tracking
- Incremental batch plus streaming data engineering patterns
