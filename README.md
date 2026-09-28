# Microsoft Fabric Real-Time Earthquake Analytics Platform

## Description
An end-to-end cloud data engineering and business intelligence solution built on **Microsoft Fabric**. The platform automatically ingests near real-time global seismic event data from the USGS REST API, processes and cleanses it using PySpark notebooks following the **Medallion Architecture** (Bronze, Silver, Gold), and delivers zero-latency interactive visualizations in Power BI via **Direct Lake mode**.

## Key Features
* **Automated Data Ingestion (Bronze Layer):** PySpark ingestion notebooks fetching raw JSON payloads directly from the USGS REST API into a Fabric Lakehouse.
* **Data Cleansing & Transformation (Silver Layer):** JSON schema flattening, epoch timestamp conversion to ISO datetimes, and Delta Lake table creation.
* **Spatial & Business Enrichment (Gold Layer):** Reverse geocoding (`reverse_geocoder`) to extract two-letter ISO country codes from geographic coordinates, alongside dynamic earthquake severity classification.
* **Pipeline Orchestration:** Automated daily pipeline workflows built in **Fabric Data Factory** using dynamic parameters (`UTCNow`, `addDays`).
* **Direct Lake Analytics:** Interactive **Power BI** map dashboard connected directly to Delta tables, eliminating data import/refresh latency.

## Architecture Pipeline
`USGS REST API` ➔ `Bronze Layer (Raw JSON)` ➔ `Silver Layer (Cleansed Delta Tables)` ➔ `Gold Layer (Enriched Analytics)` ➔ `Data Factory Pipeline` ➔ `Power BI (Direct Lake)`

## Tech Stack
* **Cloud Platform:** Microsoft Fabric
* **Engine & Languages:** PySpark (Python), Spark SQL
* **Data Lakehouse:** Delta Lake Tables (OneLake)
* **Orchestration:** Fabric Data Factory Pipelines
* **Analytics & BI:** Power BI (Direct Lake Mode, Custom Map Visuals)
* **External APIs:** USGS Earthquake Hazards API, Reverse Geocoder

---

## 🛠️ Workflow (Images)

### Lakehouse
 ![image alt](https://github.com/darikson-creator/fabric-earthquake-pipeline/blob/c8c989c716f5971202a1adc57c8736ef43aac9f7/1.%20LakeHouse.png)
 
### Bronze Layer(code)
 ![image alt](https://github.com/darikson-creator/fabric-earthquake-pipeline/blob/c8c989c716f5971202a1adc57c8736ef43aac9f7/2.%20Bronze%20Layer.png)
 
### Silver Layer(code)
 ![image alt](https://github.com/darikson-creator/fabric-earthquake-pipeline/blob/c8c989c716f5971202a1adc57c8736ef43aac9f7/3.%20Silver_layer.png)
 
### Gold Layer(code)
 ![image alt](https://github.com/darikson-creator/fabric-earthquake-pipeline/blob/c8c989c716f5971202a1adc57c8736ef43aac9f7/4.%20Gold%20Layer.png)
 
### Orchestration Pipeline
![image alt](https://github.com/darikson-creator/fabric-earthquake-pipeline/blob/c8c989c716f5971202a1adc57c8736ef43aac9f7/5.%20Pipeline.png)

### PBI Report
![image alt](https://github.com/darikson-creator/fabric-earthquake-pipeline/blob/c8c989c716f5971202a1adc57c8736ef43aac9f7/6.%20PBI_Report.png)
