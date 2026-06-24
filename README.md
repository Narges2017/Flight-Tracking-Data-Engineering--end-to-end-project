

[![Microsoft Fabric](https://img.shields.io/badge/Microsoft%20Fabric-Lakehouse%20%7C%20Dataflow%20Gen2-blue)](https://learn.microsoft.c
[![PySpark](https://img.shields.io/badge/PySpark-Delta%20Lake-orange)](https://spark.apache.org/)
[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)](https://powerbi.microsoft.com/)


An **end-to-end Flight Tracking Analytics solution** built on **Microsoft Fabric** using Lakehouse architecture, Dataflow Gen2, PySpark


---


## 📌 Project Overview


This project delivers a complete data engineering and analytics pipeline for **flight tracking data**. It covers the full journey from 
to business intelligence:


- Ingest and transform flight data using **Dataflow Gen2**
- Process and model data using **PySpark notebooks** in a **Fabric Lakehouse**
- Build dimensional models (Fact & Dimension tables)
- Visualize insights through **Power BI** dashboards


The solution follows modern data platform best practices on Microsoft Fabric.


---


## 🏗️ Architecture


```
Flight Data Sources
        ↓
┌──────────────────────┐
│   Dataflow Gen2      │   ← Ingestion & initial transformation
└──────────────────────┘
        ↓
┌──────────────────────┐
│     Lakehouse        │   ← Bronze / Silver / Gold layers
│   (Delta Tables)     │
└──────────────────────┘
        ↓
┌──────────────────────┐
│   PySpark Notebooks  │   ← Advanced transformations & modeling
└──────────────────────┘
        ↓
┌──────────────────────┐
│      Power BI        │   ← Dashboards & Analytics
└──────────────────────┘
```


---


## 🛠️ Technologies Used


| Technology           | Purpose                              |
|----------------------|--------------------------------------|
| **Microsoft Fabric** | Unified data platform                |
| **Lakehouse**        | Data storage with Delta Lake         |
| **Dataflow Gen2**    | Low-code data ingestion & transform  |
| **PySpark**          | Advanced data processing             |
| **Power BI**         | Visualization & reporting            |
| **Delta Lake**       | ACID transactions & time travel      |


---


## 📁 Project Structure


```
Flight-Tracking-Data-Engineering--end-to-end-project/
├── dataflows/                    # Dataflow Gen2 definitions
├── notebooks/
│   └── fact_and_dimension_tables.ipynb
├── pipelines/                    # Orchestration pipelines (if any)
├── docs/                         # Documentation & design docs
├── screenshots/                  # Dashboard & architecture screenshots
├── .gitignore
├── LICENSE.txt
└── README.md
```


---


## ✅ Prerequisites


- Microsoft Fabric workspace with **capacity** (F8 or higher recommended)
- A **Lakehouse** item created in the workspace
- Access to flight tracking data source (API, CSV, database, etc.)
- Power BI Desktop or Power BI Service access


---


## 🚀 Getting Started


### 1. Setup in Microsoft Fabric


1. Create a new **Workspace** in Microsoft Fabric.
2. Create a **Lakehouse** inside the workspace.
3. Import or create the **Dataflow Gen2** from the `dataflows/` folder.
4. Attach the Lakehouse to the provided notebook.


### 2. Run the Components (Recommended Order)


| Step | Component                        | Description                                      |
|------|----------------------------------|--------------------------------------------------|
| 1    | **Dataflow Gen2**                | Ingest raw flight data into the Lakehouse        |
| 2    | `fact_and_dimension_tables.ipynb`| Create Fact and Dimension tables (Star Schema)   |
| 3    | **Power BI**                     | Connect to Gold layer and build dashboards       |


### 3. Notebook Execution Tips


- Use **`.mode("overwrite")`** when writing tables to avoid `TABLE_OR_VIEW_ALREADY_EXISTS` errors.
- If you encounter **`TooManyRequestsForCapacity`**:
  - Go to **Monitoring hub** → Cancel active Spark jobs
  - Wait 2–5 minutes before retrying
  - Consider upgrading your Fabric capacity during development


---


## 📓 Notebooks


### `fact_and_dimension_tables.ipynb`


**Purpose**: Builds the analytical data model using dimensional modeling techniques.


**Key Activities**:
- Creates Fact table(s) for flight events/metrics
- Builds Dimension tables (e.g., `dim_aircraft`, `dim_airport`, `dim_date`, `dim_flight_status`, etc.)
- Applies business logic and data quality rules
- Outputs clean, analytics-ready tables in the Gold layer


---


## 📊 Power BI Integration


This project includes Power BI reports/dashboards for flight analytics. Common use cases include:


- Real-time or near-real-time flight status monitoring
- Delay analysis and root cause identification
- Airport and route performance
- Aircraft utilization metrics


> Screenshots of the dashboards are available in the `screenshots/` folder.


---


## ⚠️ Common Issues & Solutions


| Error                                      | Cause                                      | Solution |
|--------------------------------------------|--------------------------------------------|----------|
| `TABLE_OR_VIEW_ALREADY_EXISTS`             | Table already exists from previous run     | Use `mode("overwrite")` or `CREATE OR REPLA
| `TooManyRequestsForCapacity` (HTTP 430)    | Fabric capacity limit reached              | Cancel jobs in Monitoring hub + wait or upg
| Dataflow Gen2 refresh failures             | Source connectivity or transformation issues | Check Dataflow refresh history and creden


---


## 📈 Future Enhancements


- [ ] Add real-time streaming ingestion (Eventstreams / Kafka)
- [ ] Implement incremental loading patterns
- [ ] Add data quality monitoring (e.g., Great Expectations)
- [ ] Build a semantic model with Direct Lake mode
- [ ] Add automated pipeline orchestration using Fabric Pipelines
- [ ] Include predictive analytics (flight delay prediction)


---


## 🤝 Contributing


Contributions, suggestions, and feedback are welcome!  
Feel free to open an issue or submit a pull request.


---


## 📄 License


This project is licensed under the MIT License - see the [LICENSE.txt](LICENSE.txt) file for details.


---


## 👩‍💻 Author


**Narges**  
Flight Tracking End-to-End Data Engineering Project on Microsoft Fabric


---


> Built with ❤️ using Microsoft Fabric for modern data engineering and analytics.


---


