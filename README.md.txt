# Flight Tracking Data Engineering with Microsoft Fabric

## Project Overview

This project demonstrates an end-to-end Data Engineering solution built using Microsoft Fabric.

The solution ingests flight tracking data, performs data cleansing and transformation using Dataflow Gen2, stores data in a Lakehouse, builds a Star Schema using PySpark notebooks, orchestrates the workflow through Fabric Pipelines, and delivers analytics through Power BI reports.

---

## Architecture

```text
Flight Data Source
        │
        ▼
Dataflow Gen2
(Extract & Transform)
        │
        ▼
Lakehouse
(Cleaned Flights)
        │
        ▼
PySpark Notebook
(Fact & Dimension Tables)
        │
        ▼
Semantic Model
        │
        ▼
Power BI Dashboard
```

---

## Technologies Used

- Microsoft Fabric
- Dataflow Gen2
- Lakehouse
- PySpark
- Delta Tables
- Semantic Model
- Power BI
- Data Pipeline

---

## Data Model

### Fact Table

#### Fact_Flights

- flight_id
- date_key
- airline_key
- departure_airport_key
- arrival_airport_key
- flight_status
- flight_number
- flight_iata
- duration
- hour
- time_bucketing
- flight_type

### Dimension Tables

#### Dim_Airline

- airline_key
- airline_iata
- airline_name

#### Dim_Airports

- airport_key
- airport_iata
- airport_name
- airport_timezone

#### Dim_Date

- date_key
- full_date
- year
- month
- month_name
- day_of_month
- day_name
- week_of_year

---

## Pipeline Workflow

1. Extract flight data using Dataflow Gen2.
2. Apply cleansing and transformation rules.
3. Load cleaned data into the Fabric Lakehouse.
4. Build Fact and Dimension tables using PySpark.
5. Refresh Semantic Model.
6. Deliver insights through Power BI reports.

---

## Repository Structure

```text
Flight-Tracking-Data-Engineering/
├── dataflows/
├── notebooks/
├── pipelines/
├── screenshots/
├── docs/
├── README.md
└── LICENSE
```

---

## Screenshots

### Dataflow

![Dataflow](screenshots/dataflow.png)

### Pipeline

![Pipeline](screenshots/pipeline.png)

### Semantic Model

![Semantic Model](screenshots/semantic_model.png)

### Dashboard

![Dashboard](screenshots/dashboard.png)

---

## Key Features

- End-to-End Data Engineering Pipeline
- Star Schema Modeling
- Automated Data Refresh
- Pipeline Orchestration
- Power BI Reporting
- Microsoft Fabric Lakehouse Architecture

---

## Future Improvements

- Real-time Flight Streaming
- Incremental Data Loading
- Data Quality Monitoring
- Advanced Flight Delay Analytics
- CI/CD Integration with GitHub