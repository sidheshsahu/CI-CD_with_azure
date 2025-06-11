
# End-to-End Azure Data Engineering Pipeline for Blinkit Data with Full CI/CD Automation

Blinklytics is a fully integrated Azure-based Data Engineering project that replicates a real-world retail analytics pipeline using Blinkit customer, order, product, and feedback data. It demonstrates a complete CI/CD-enabled modern data architecture using Azure Data Factory, Azure Data Lake, Azure Databricks, and Azure Synapse Analytics, concluding with a Power BI star schema visualization.




## Project Architecture Overview

🥉**1. Ingestion – Bronze Layer (Azure Data Factory)**:
Developed a parameterized pipeline in Azure Data Factory (ADF) to dynamically ingest multiple CSV files:

customers.csv

orders.csv

products.csv

feedback.csv

Source: GitHub

Destination: Azure Data Lake Storage Gen2 (ADLS) – Bronze layer

Data organized into respective folders for each entity

🥈 **2. Transformation – Silver Layer (Azure Databricks)**
Utilized Azure Databricks notebooks with Spark to:

Read raw data from Bronze

Perform data cleaning, type casting, and transformation logic

Wrote the cleaned data in Parquet format to the Silver layer of ADLS

🥇**3. Data Warehousing – Gold Layer (Azure Synapse Analytics)**:
Implemented a data warehouse using Azure Synapse Analytics (Serverless SQL Pool):

Created:

EXTERNAL DATA SOURCE

DATABASE SCOPED CREDENTIAL

EXTERNAL FILE FORMAT

EXTERNAL TABLES over Parquet files from Silver layer

Designed dimensional model with:

dim_customers

dim_orders

dim_products

dim_feedback

fact_sales (joins dimensions)

📊 -**4. BI & Reporting – Power BI**:
Connected Power BI directly to Synapse external tables via Serverless SQL endpoint

Built and modeled a Star Schema

Created dashboards for:

Sales Insights

Customer Feedback Trends

Product Performance

⚙️ **5. CI/CD – DevOps Automation**:
Implemented CI/CD pipelines for both ADF and Synapse using Azure DevOps

Version control and collaboration via Git integration

ARM templates used for:

Deployment of linked services, datasets, and pipelines in ADF

Deployment of Synapse artifacts (credentials, formats, tables)

Enabled modular infrastructure delivery and automated release management


## 📂 Dataset

Dataset consists of the following Excel files:
- Customers
- Products
- Orders
- Customer_Feedback
## Objectives

Designed and implemented a dynamic ingestion pipeline in Azure Data Factory to extract structured Blinkit retail data from GitHub to Azure Data Lake (Bronze layer).

Performed data transformation in Azure Databricks with secure Entra ID authentication, writing clean data to Parquet format in Silver layer.

Developed a data warehouse in Synapse Analytics by creating external sources, formats, credentials, and external tables over the Silver data.

Built and modeled a Star Schema in Power BI with fact_sales, dim_customers, dim_orders, dim_products, and dim_feedback.

Automated CI/CD pipelines in Azure DevOps for ADF and Synapse using ARM templates, ensuring version control, continuous deployment, and modular infrastructure delivery.

## 🛠️ Tools & Technologies

- Azure Data Factory (ADF)
- Azure Data Lake Storage Gen2 (ADLS)
- Azure Databricks
- Azure Synapse Analytics
- Azure DevOps Organization
- PowerBI
- GitHub
