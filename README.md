# Supply Chain & Logistics Optimization Dashboard

## Project Overview
This project analyzes end-to-end supply chain data to identify geographic bottlenecks, track delivery performance, and highlight operational inefficiencies. By engineering custom metrics and applying advanced SQL transformations to raw logistics data, this dashboard provides operations leadership with immediate visibility into region-specific shipping delays and inventory risks.

## The Business Problem
Supply chain and operations teams require real-time visibility into shipping performance to prevent customer churn and reduce tied-up capital. The objective of this analysis was to:
* Identify which regions suffer from the highest delivery delays.
* Calculate 30-day rolling averages of delivery times to track performance trends.
* Flag high-risk logistical bottlenecks for immediate operational intervention.

## Tech Stack & Skills Used
* **Python (Pandas):** Data cleaning, handling missing values, and engineering exact delivery delay metrics from raw transactional data.
* **SQL (SQLite):** Advanced data transformation utilizing Common Table Expressions (CTEs) and Window Functions to calculate time-series rolling averages.
* **Microsoft Power BI:** Interactive data visualization, Power Query data validation, and DAX measure creation (KPIs).

## Methodology & Workflow

### 1. Data Engineering & Cleaning (Python/Pandas)
* Ingested a 180,000+ row dataset and do cleaning and select some important columns.
* Formatted datetime columns and engineered a core `delay_in_days` metric by calculating the variance between scheduled and actual shipping dates.

### 2. Time-Series Aggregation (SQL)
* Built an in-memory SQL database to process the cleaned logistics data.
* Executed queries using Window Functions `AVG() OVER (PARTITION BY ...)` to calculate a 30-day rolling average of delivery delays per region, smoothing out daily variance to reveal true operational trends.

### 3. Data Visualization (Power BI)
* Engineered custom DAX formulas for high-level KPIs (Average Global Delay, Max Rolling Delay, Region Count).
* Designed an interactive layout featuring a Filled Map with gradient conditional formatting to pinpoint geographic bottlenecks.
* Implemented cross-filtering so stakeholders can click a high-risk region and instantly view its historical delay trend line.

## Key Insights
* **Regional Bottlenecks:** Eastern Asia exhibits the highest average delay of more that 40 hrs.
* **Historical Trends:** The 30-day rolling average indicated a maximum steady recovery in delivery times, with average delays dropping from 287 times down to 50 times across South Asia logistics routes.

## Files in this Repository
* `Supply_Chain_Prep.ipynb`: The Python script containing the Pandas cleaning and SQL transformation logic.
* `Rolling_Delays.csv`: The processed output dataset ready for BI ingestion.
* `Supply_Chain_Delays.pbix`: The final Power BI dashboard file.
* `Supply_Chain_Dashboard.png`: A high-resolution preview of the final visualizations.

## Screenshots
<img width="1858" height="866" alt="codeSS1" src="https://github.com/user-attachments/assets/4e09a86d-f868-482d-8d69-a6ec809770f8" />
<img width="1845" height="855" alt="codeSS2" src="https://github.com/user-attachments/assets/5537395b-05a8-4e02-96ad-67dd802ebb86" />
<img width="1850" height="850" alt="codeSS3" src="https://github.com/user-attachments/assets/5176aa1d-eb0b-43d5-b285-37bf7b583972" />
<img width="1279" height="713" alt="Supply_Chain_Dashboard" src="https://github.com/user-attachments/assets/587dadea-9b81-441a-8f44-61134b3d0a05" />

---
*Author: Vivek Rajput* 
