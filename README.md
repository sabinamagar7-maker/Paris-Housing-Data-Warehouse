# Urban Analytics: A Multi‑Domain Data Warehouse for Paris

## Overview

This project presents the design and implementation of a multi-domain urban analytics data warehouse focused on the city of Paris. The project integrates datasets related to housing transactions, demographics, business activity, permits, and urban indicators to support analytical reporting and business intelligence.

The solution follows a layered ELT architecture implemented in Snowflake, with transformations progressing from RAW ingestion to normalized data models and finally to denormalized BI-ready marts used for Power BI reporting.

The project also incorporates GitHub-based version control and a basic CI workflow using GitHub Actions to demonstrate modern analytics engineering practices.

---

# Objectives

The main objectives of this project were:

* Build a scalable ELT pipeline using Snowflake
* Design a structured normalized warehouse architecture
* Create denormalized analytical models optimized for BI reporting
* Develop interactive dashboards and KPI reporting in Power BI
* Demonstrate modern analytics engineering concepts such as:

  * Layered warehouse architecture
  * Version control with GitHub
  * CI workflow automation
  * Data modeling
  * SQL-based transformations

---

# Technologies Used

| Category          | Tools / Technologies |
| ----------------- | -------------------- |
| Data Warehouse    | Snowflake            |
| Data Processing   | SQL, Python          |
| Visualization     | Power BI             |
| Version Control   | Git, GitHub          |
| CI Workflow       | GitHub Actions       |
| Data Preparation  | Python, Pandas       |
| IDE / Development | VS Code              |

---

# Architecture

The project follows a layered ELT architecture:

```text
Source Data
    ↓
RAW Layer
    ↓
Normalized Layer (3NF)
    ↓
Denormalized Layer / Data Marts
    ↓
Power BI Dashboards
```

## RAW Layer

The RAW layer stores minimally transformed source datasets loaded into Snowflake.

Characteristics:

* Preserves original source structure
* Acts as technical source of truth
* Supports reproducibility and reprocessing
* Loaded using SnowSQL

## Normalized Layer

The normalized layer applies transformation logic and organizes data following normalization principles.

Characteristics:

* Reduces redundancy
* Establishes relationships between entities
* Improves data consistency and integrity
* Creates reusable analytical foundations

Examples:

* Dimension tables
* Transaction tables
* Business activity entities
* Permit entities

## Denormalized Layer

The denormalized layer transforms normalized structures into BI-optimized models.

Characteristics:

* Optimized for analytical queries
* Reduces join complexity for reporting
* Supports Power BI performance
* Structured as fact and dimension models

---

# ELT Workflow

The project follows an ELT (Extract, Load, Transform) approach.

## Extraction

Datasets were downloaded from multiple public urban and demographic data sources.

Examples:

* Paris DVF Housing Transactions
* INSEE demographic data
* Business activity datasets
* Permit datasets

## Loading

Large datasets were uploaded into Snowflake using SnowSQL.

Example workflow:

```text
CSV / ZIP datasets
    ↓
Snowflake Stage
    ↓
RAW tables
```

## Transformation

Transformations were implemented using SQL scripts stored in the GitHub repository.

Main transformation stages:

1. RAW Layer
2. Normalized Layer
3. Denormalized Layer

---

# Repository Structure

```text
paris-housing-dwh/
│
├── datasets/
│   └── sample_data/
│
├── sql/
│   ├── _01_raw_layer.sql
│   ├── _02_Normalized_layer.sql
│   └── _03_Denormalized_layer.sql
│
├── Normalized_Data_model_diagram/
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
└── README.md
```

---

# Data Modeling

The project includes both normalized and denormalized modeling approaches.

## Normalized Modeling

The normalized layer follows relational modeling principles to:

* Eliminate redundancy
* Improve consistency
* Separate entities logically
* Support scalable transformations

## Denormalized Modeling

The denormalized layer was designed specifically for BI reporting.

It includes:

* Fact tables
* Dimension tables
* KPI-ready aggregations
* Time-based analytical structures

---

# Power BI Reporting

Interactive dashboards were developed in Power BI to analyze:

* Housing prices
* Transaction volumes
* Demographic trends
* Business activity
* Urban development patterns
* Geographic distribution

The dashboards include:

* KPI cards
* Trend analysis
* Geospatial visualizations
* Comparative district analysis
* Time-series reporting

---

# CI Workflow (GitHub Actions)

A basic CI workflow was implemented using GitHub Actions.

The workflow automatically validates:

* Required SQL files exist
* SQL files are not empty
* Repository structure integrity

This demonstrates understanding of:

* CI/CD concepts
* GitHub Actions workflows
* Automated validation pipelines
* Analytics engineering development practices

Workflow file:

```text
.github/workflows/ci.yml
```

---

# CI/CD Conceptual Understanding

Although this project currently implements CI validation only, the architecture supports future CD deployment workflows.

Potential future CD implementation:

```text
Git Push
    ↓
CI Validation
    ↓
Snowflake Deployment Pipeline
    ↓
Automatic SQL Execution
    ↓
Warehouse Update
```

Possible deployment technologies:

* SnowSQL
* Snowflake Python Connector
* dbt
* GitHub Actions

---

# Analytics Engineering Concepts Demonstrated

This project demonstrates understanding of:

* ELT architecture
* Data warehouse layering
* Normalized and denormalized modeling
* SQL transformation workflows
* Snowflake-based analytics architecture
* Version control with GitHub
* CI workflow automation
* Downstream dependency concepts
* BI-oriented warehouse design

---

# Future Improvements

Potential future enhancements include:

* dbt integration
* Automated Snowflake CD deployment
* Data quality testing
* Incremental loading strategies
* Advanced CI validation
* Automated Power BI refresh orchestration
* Additional urban datasets

---

# Dataset Note

Due to dataset size limitations, only sample datasets are included in this repository.

The original datasets were loaded into Snowflake using SnowSQL and processed through the ELT pipeline.

---

# Author

Sabina Thapa Magar

* SQL
* Snowflake
* Power BI
* Python
* Data Warehousing
* Analytics Engineering Concepts
