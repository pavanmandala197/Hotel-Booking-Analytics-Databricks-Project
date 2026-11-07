# 🏨 Hotel Booking Analytics – Databricks Medallion Architecture

## 📌 Project Overview

The **Hotel Booking Analytics Platform** is an end-to-end data engineering project developed using **Databricks, Lakeflow Spark Declarative Pipelines, Databricks SQL, Unity Catalog, and AI/BI Dashboards**.

The main objective of this project is to transform raw hotel booking data into clean, reliable, and business-ready datasets using the Medallion Architecture (Bronze, Silver, and Gold layers).

The project focuses on improving data quality, identifying booking trends, analyzing hotel performance, monitoring cancellations, and generating meaningful business insights through interactive dashboards.

## 🎯 Business Objectives

- Build an automated and repeatable data pipeline in Databricks.
- Ingest raw hotel booking data from a CSV file.
- Implement Bronze, Silver, and Gold data layers.
- Identify and handle duplicate and invalid booking records.
- Perform data cleaning and transformation using SQL.
- Generate business-level summary tables.
- Validate data quality through reconciliation checks.
- Develop an interactive dashboard for business analysis.

## 🛠️ Technologies Used

- **Databricks** – Data engineering and analytics platform.
- **Lakeflow Spark Declarative Pipelines** – Data pipeline development and orchestration.
- **SQL** – Data ingestion, cleaning, transformation, and analysis.
- **Unity Catalog** – Data organization and governance.
- **Medallion Architecture** – Bronze, Silver, and Gold data processing.
- **Databricks AI/BI Dashboard** – Data visualization and business reporting.

## 🏗️ Project Architecture – Medallion Architecture

The project follows a three-layer Medallion Architecture.

### 🥉 Bronze Layer – Raw Data Ingestion

- Ingested the hotel booking CSV dataset into Databricks using a Unity Catalog Volume.
- Created a Bronze streaming table to store raw booking records.
- Preserved the original source data.
- Added source file name and data load timestamp for tracking.

### 🥈 Silver Layer – Data Cleaning and Transformation

Performed data cleaning and validation to improve data quality.

Key operations:

- Removed duplicate booking records using `booking_id`.
- Standardized text columns using `TRIM()` and `INITCAP()`.
- Handled missing values using `COALESCE()`.
- Calculated missing nights using `DATEDIFF()`.
- Recalculated missing booking amounts.
- Identified invalid check-in and check-out dates.
- Identified negative room rates.
- Stored rejected records separately with rejection reasons.
- Retained cancelled bookings as valid business records.

### 🥇 Gold Layer – Business-Ready Data

Created aggregated summary tables to support business analysis.

| Gold Table | Purpose |
|---|---|
| gold_monthly_bookings | Monthly booking trends, cancellations, room nights and revenue |
| gold_hotel_summary | Hotel, city and regional performance |
| gold_room_type_summary | Room type performance and guest ratings |
| gold_channel_summary | Booking channel performance and cancellation rates |
| gold_data_quality | Data quality metrics and reconciliation |

## 📊 Dashboard Development

Developed a Databricks AI/BI Dashboard to visualize business performance using Gold-layer tables.

The dashboard includes three analytical sections:

**1. Overview**
- Total Bookings
- Net Revenue
- Room Nights
- Cancelled Bookings
- Monthly Revenue Trends
- Revenue by City

**2. Hotels, Rooms & Channels**
- Revenue by Hotel
- Average Daily Rate (ADR)
- Revenue by Room Type
- Average Guest Rating
- Cancellation Rate by Booking Channel

**3. Data Quality**
- Total Bronze Records
- Clean Bookings
- Rejected Records
- Duplicate Records
- Reconciliation Status
- Data Quality Issues

## 📈 Key Business Metrics

- **Net Revenue:** Total booking amount after discounts, considering completed bookings only.
- **Room Nights:** Total number of nights for completed bookings.
- **Average Daily Rate (ADR):** Net Revenue divided by Room Nights.
- **Cancellation Rate:** Percentage of cancelled bookings out of total bookings.
- **Hotel Performance:** Comparison of revenue and booking performance across hotels.

## 🔍 Data Quality and Validation

Implemented data quality checks to ensure reliable reporting.

- Duplicate booking identification.
- Missing value handling.
- Invalid date validation.
- Negative room rate validation.
- Separate rejected records.
- Data reconciliation between Bronze, Silver and rejected records.

The reconciliation check ensures that source records are accounted for as clean records, rejected records, or duplicates removed.

## 💡 Key Learning Outcomes

Through this project, I gained practical experience in:

- Building end-to-end data pipelines using Databricks.
- Understanding and implementing Medallion Architecture.
- Working with Unity Catalog and Volumes.
- Developing Lakeflow Spark Declarative Pipelines using SQL.
- Performing data cleaning and transformation.
- Creating business-ready Gold summary tables.
- Implementing data quality and reconciliation checks.
- Developing interactive AI/BI dashboards.
- Translating business requirements into analytical insights.

## 📁 Project Deliverables

- Databricks Lakeflow pipeline.
- Bronze, Silver and Gold tables.
- SQL transformation queries.
- Data quality and reconciliation results.
- Pipeline graph and architecture screenshots.
- Databricks AI/BI Dashboard.
- Project documentation.

## 👨‍💻 Conclusion

This project demonstrates how raw hotel booking data can be transformed into trusted business information using modern data engineering concepts.

By implementing the Medallion Architecture in Databricks, the project establishes a structured and repeatable data processing workflow, improves data quality, and provides meaningful insights into hotel booking trends, revenue, cancellations, and operational performance.

**This project helped me strengthen my practical knowledge of Databricks, SQL, data engineering, and business analytics.**
