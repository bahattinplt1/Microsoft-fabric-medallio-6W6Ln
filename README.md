# Microsoft Fabric - Medallion Architecture End-to-End Project

This repository demonstrates a complete implementation of the **Medallion Architecture** (Bronze → Silver → Gold) in **Microsoft Fabric**, designed to simulate a modern data engineering and analytics pipeline.

## 🧱 Overview

The project follows a layered approach for building a scalable and maintainable data model, using Microsoft Fabric's integrated Lakehouse, Delta Lake, and Semantic Model tools.

---

## ✅ Implementation Summary

### 1. Workspace Setup
- Created a Microsoft Fabric workspace with trial or premium capacity.
- Enabled the Data Model Editing preview feature for semantic modeling.

### 2. Lakehouse and Bronze Layer
- Created a new Lakehouse named `Sales`.
- Uploaded sales CSV data (2019, 2020, 2021) into a `bronze` folder.

### 3. Silver Layer Transformation
- Loaded bronze data using PySpark with an explicitly defined schema.
- Applied data validation and enrichment (e.g. flags, timestamps).
- Saved the cleaned data as a Delta table named `sales_silver`.

### 4. Gold Layer Modeling (Star Schema)
- Created three dimension tables:
  - `dimdate_gold` (date breakdown and formats)
  - `dimcustomer_gold` (name split, customer IDs)
  - `dimproduct_gold` (item name, type, IDs)
- Created `factsales_gold` as the fact table linking all dimensions.

### 5. Semantic Model
- Created a custom semantic model named `Sales_Gold`.
- Included the gold tables and defined relationships for reporting.
- Model is ready to be used directly in Power BI or Fabric Reports.

---

## 🛠️ Tools & Technologies

- Microsoft Fabric (Lakehouse, Delta Lake, Notebooks, Semantic Models)
- PySpark & SQL
- Delta Lake Merge Operations
- Power BI-compatible semantic modeling

---

## 📸 Screenshots

All implementation steps are visually documented in the `screenshots/` folder.

---

## 📦 Source Data

The dataset used in this project was provided by Microsoft Learn:  
**[orders.zip](https://github.com/MicrosoftLearning/dp-data/blob/main/orders.zip)**  
Contains sales data in CSV format for 2019, 2020, and 2021.

---

## 🙌 Credits

Based on training materials from Microsoft Fabric learning labs.
