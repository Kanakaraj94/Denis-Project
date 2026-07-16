# Denis - Azure Data Engineering Project

## Project Overview

**Denis** is an end-to-end Azure Data Engineering project built using the Medallion Architecture (Bronze, Silver, and Gold). The project ingests data from multiple sources, performs data cleaning and business transformations, and loads the processed data into Azure SQL Database for reporting and analytics.

---

## Architecture

```
               Multiple Data Sources
                        │
                        ▼
              Azure Data Factory (ADF)
                        │
                        ▼
            Azure Data Lake Storage Gen2
        ┌────────────────────────────────┐
        │        Bronze Layer            │
        │  Raw Data Ingestion            │
        └────────────────────────────────┘
                        │
                        ▼
        ┌────────────────────────────────┐
        │        Silver Layer            │
        │ Data Cleaning & Transformation │
        └────────────────────────────────┘
                        │
                        ▼
        ┌────────────────────────────────┐
        │         Gold Layer             │
        │ Business & Analytical Data     │
        └────────────────────────────────┘
                        │
                        ▼
               Azure SQL Database
                        │
                        ▼
            Reporting / Power BI Ready
```

---

# Technologies Used

- Azure Data Factory (ADF)
- Azure Data Lake Storage Gen2 (ADLS Gen2)
- Azure SQL Database
- Azure Blob Storage
- GitHub
- Azure Mapping Data Flow
- MySQL Database
- MongoDB
- Azure Key Vault

---

# Medallion Architecture

## Bronze Layer

Purpose:
- Store raw data exactly as received from source systems.

Activities:
- Read data from multiple sources.
- Store raw files in ADLS Bronze layer.
- Preserve original data without transformations.

---

## Silver Layer

Purpose:
- Clean and standardize raw data.

Transformations:
- Remove duplicate records
- Handle null values
- Trim leading/trailing spaces
- Standardize data formats
- Rename columns
- Filter invalid records
- Convert data types
- Create cleaned datasets

Output:
- Cleaned and validated data stored in ADLS Silver layer.
- Individual normalized tables loaded into Azure SQL Database.

---

## Gold Layer

Purpose:
- Create business-ready analytical datasets.

Activities:
- Join multiple Silver datasets.
- Create denormalized business tables.
- Calculate business metrics.
- Load analytical datasets into Azure SQL Database.

Business Calculations:
- Total Revenue
- Total Cost
- Gross Profit
- Average Sales Per Day

Output:
- Gold layer in ADLS.
- Denormalized analytical tables in Azure SQL Database.

---

# Azure SQL Database

Normalized Tables:
- Categories
- Product
- SubCategories
- Sales
- Geography
- SalesRep

Denormalized Tables:
- Gold analytical table (Denis_G_Tb)

Analytical Metrics:
- Total Revenue
- Total Cost
- Gross Profit
- Average Sales Per Day

---

# Azure Data Factory Components

- Pipelines
- Mapping Data Flows
- Linked Services
- Datasets
- Integration Runtime
- Copy Activities
- Sink Transformations
- Execute Pipeline Activity

---

# Git Workflow

Repository Structure:

```
main
│
├── feature/bronze-layer
├── feature/silver-layer
├── feature/gold-layer
│
└── adf_publish
```

Workflow:

1. Create Feature Branch
2. Develop
3. Commit Changes
4. Push to GitHub
5. Create Pull Request
6. Merge to Main
7. Publish ADF

---

# Project Workflow

1. Read data from multiple sources.
2. Load raw data into Bronze layer.
3. Clean and standardize data in Silver layer.
4. Store normalized tables in Azure SQL Database.
5. Join Silver datasets in Gold layer.
6. Calculate business metrics.
7. Store denormalized analytical tables in Azure SQL Database.

---

# Project Features

- End-to-End ETL Pipeline
- Medallion Architecture
- Azure Data Factory Pipelines
- Mapping Data Flows
- Azure SQL Integration
- GitHub Version Control
- Normalized Data Model
- Denormalized Analytical Model
- Business KPI Calculations

---

# Business KPIs

- Total Revenue
- Total Cost
- Gross Profit
- Average Sales Per Day

---

# Future Enhancements

- Incremental Loading
- Change Data Capture (CDC)
- Azure Databricks Integration
- Delta Lake Implementation
- Power BI Dashboard
- Azure Key Vault Integration
- Pipeline Monitoring & Alerts
- CI/CD using Azure DevOps or GitHub Actions

---

# Author

**Kanaka Raj**

Azure Data Engineering Project - Denis
