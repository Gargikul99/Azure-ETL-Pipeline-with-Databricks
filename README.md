# Azure ETL Pipeline with Databricks

This repository showcases an **ETL pipeline** built using **Azure Data Factory** (ADF) and **Databricks** for processing and transforming e-commerce data. The data is sourced from the **Olist Brazilian E-Commerce Dataset** and is processed through multiple stages, including raw data ingestion (Bronze layer), data transformation (Silver layer), and data aggregation (Gold layer). The final output of the Gold layer is prepared for analysis and machine learning.

## Project Overview

The project demonstrates how to build an ETL pipeline that processes raw e-commerce data and transforms it into actionable insights. The pipeline is structured into three layers:

1. **Bronze Layer**: Raw data ingestion and storage.
2. **Silver Layer**: Data cleaning, transformation, and enrichment.
3. **Gold Layer**: Aggregated data for machine learning and analysis.

### Technologies Used

- **Azure Data Factory (ADF)**: Orchestrates the ETL pipeline and manages the flow of data.
- **Databricks**: Performs advanced data transformations using **PySpark**.
- **Azure Blob Storage**: Stores the raw, transformed, and aggregated data.
- **Azure Databricks Notebooks**: Execute PySpark code for cleaning, transforming, and aggregating the data.
  
## Layers and Transformations

### Bronze Layer (Raw Data Ingestion)

In the **Bronze Layer**, the raw e-commerce data is ingested and stored into **Azure Blob Storage**. The raw data consists of several tables related to orders, customers, products, payments, reviews, and sellers.

The following tables are part of the Bronze layer:

- **customer_df**: Information about customers.
- **geolocation_df**: Geolocation details for customers and sellers.
- **order_items_df**: Item details for each order.
- **order_payments_df**: Payment details for each order.
- **order_reviews_df**: Customer reviews for each order.
- **orders_df**: Order details, including timestamps and status.
- **products_df**: Product details including category and specifications.
- **sellers_df**: Seller information and details.

This layer serves as the foundation for subsequent transformations.

### Silver Layer (Data Transformation)

In the **Silver Layer**, data from the **Bronze Layer** is transformed and cleaned. Key transformations in this layer include:

- **Data Cleaning**: Missing values, duplicates, and erroneous entries are handled.
- **Data Enrichment**: New calculated columns such as order delays, shipping information, and order durations are added.
- **Data Joins**: Relevant tables are joined together to create a comprehensive dataset for further analysis. For example, customer data is joined with order details and payment information.
- **Standardization**: Data is converted into a uniform format, making it ready for aggregation and analysis.

Transformations are executed in **Azure Databricks** using **PySpark**, which allows for large-scale processing and complex data operations.

### Gold Layer (Data Aggregation and Final Transformation)

The **Gold Layer** is where the final transformation occurs, and the data is aggregated and structured for machine learning models and analysis. Key actions in this layer include:

- **Customer Segmentation**: Aggregating data by `customer_unique_id` to calculate metrics like total orders, total order value, and total freight value per customer.
- **Product-Level Aggregation**: Calculating order and payment totals per product to understand product performance.
- **Derived Columns**: Creating new insights, such as customer order frequency and total value spent.

The **Gold Layer** output is a highly aggregated and processed dataset ready for analysis or feeding into machine learning models.

## Work Done So Far

### Data Ingestion and Transformation

- Ingested raw e-commerce data from **Azure Blob Storage** into the **Bronze Layer**.
- Cleaned and transformed the data in the **Silver Layer** using **PySpark** in **Databricks**.
- Aggregated and prepared the data in the **Gold Layer** for analysis.

### Key Transformations in Gold Layer

- Calculated **total order value** per customer.
- Aggregated customer orders and payments to understand customer spending patterns.
- Cleaned and normalized data to prepare for machine learning.

### Tools and Technologies Used

- **Azure Data Factory**: Used for orchestrating the ETL pipeline and managing data flow between storage and Databricks.
- **Databricks Notebooks**: Used to write and execute PySpark code for data transformation.
- **Azure Blob Storage**: Used to store raw and transformed data in various stages of the pipeline.

## Future Steps

- **Machine Learning Models**: Once the Gold Layer is completed, the next step will be to apply machine learning algorithms to the data to build models for customer segmentation, product recommendations, or predictive analytics.
- **Model Deployment**: Models will be deployed to Azure Machine Learning or another platform for real-time predictions and recommendations.

## Conclusion

This project provides an end-to-end solution for processing and transforming e-commerce data using **Azure Data Factory** and **Databricks**. The pipeline processes raw data through the Bronze, Silver, and Gold layers, transforming it into a clean, structured dataset ready for analysis and machine learning.

