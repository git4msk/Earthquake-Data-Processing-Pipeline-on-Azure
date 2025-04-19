# Earthquake Data Processing Pipeline on Azure

This project implements an end-to-end data engineering pipeline using Microsoft Azure services to ingest, process, and analyze global earthquake data. The pipeline leverages key Azure components for scalable data movement, transformation, and storage, following a medallion architecture (Bronze → Silver → Gold).

## Project Overview

The primary objective of this project is to build a cloud-based data pipeline that:
- Ingests earthquake data from a public API.
- Processes the raw JSON data into structured formats using Azure Databricks.
- Stores the data in Azure Data Lake Storage (ADLS Gen2).
- Enables querying and analysis through Azure Synapse Analytics.

The processed dataset can be used to derive insights into the frequency, magnitude, and location of seismic events over time.

## Architecture

The solution follows a layered architecture:

1. **Bronze Layer** – Stores raw JSON data ingested from the USGS Earthquake API.
2. **Silver Layer** – Contains cleaned and semi-structured data using PySpark in Azure Databricks.
3. **Gold Layer** – Final curated datasets ready for analytics and visualization.

## Tools and Technologies

- Azure Data Factory – Orchestration and scheduling
- Azure Databricks – Data transformation (PySpark)
- Azure Data Lake Storage Gen2 – Data storage
- Azure Synapse Analytics – Data analysis using SQL
- USGS Earthquake API – Public data source
- Delta Lake – Storage format for versioning and optimization

## Data Flow

1. **Data Ingestion**  
   ADF pipeline triggers a notebook in Databricks to call the USGS API and write raw data to the Bronze layer.

2. **Data Transformation**  
   The Bronze data is cleaned and structured into the Silver layer using PySpark in Databricks.

3. **Data Aggregation**  
   Gold layer datasets are created with derived columns, formatted timestamps, and optimized schema.

4. **Data Querying**  
   Azure Synapse Analytics is connected to the Gold layer for exploratory analysis.

## Outcomes

- Successfully built a real-time ingestion and transformation pipeline.
- Learned how to integrate ADF, Databricks, ADLS, and Synapse Analytics.
- Gained hands-on experience with data flow orchestration, PySpark-based transformation, and lakehouse design.
