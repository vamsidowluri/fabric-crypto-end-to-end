# fabric-crypto-end-to-end
An end-to-end ELT pipeline built on Microsoft Fabric using PySpark, Delta Lake, and Power BI Direct Lake to analyze real-time crypto financial data.

# End-to-End Real-Time Financial Data Pipeline on Microsoft Fabric

Project Overview
This project demonstrates a modern **Medallion Architecture** built entirely within **Microsoft Fabric**. It ingests real-time cryptocurrency data from the CoinGecko API, processes it through Bronze/Silver/Gold layers using PySpark, and serves insights via **Power BI Direct Lake** mode for zero-latency reporting.

The goal was to build a scalable, automated ELT solution that eliminates traditional data movement bottlenecks while handling schema evolution.

Architecture
**Source (API)** $\rightarrow$ **Bronze (Raw JSON)** $\rightarrow$ **Silver (Clean Delta Table)** $\rightarrow$ **Gold (Aggregated Business Data)** $\rightarrow$ **Power BI (Direct Lake)**

Ingestion: Python/Requests to fetch real-time JSON data.
Storage: OneLake (ADLS Gen2) using Delta Parquet format.
Transformation: PySpark (Notebooks) for cleaning, casting, and deduplication.
Orchestration: Fabric Data Pipelines (similar to Azure Data Factory) for scheduling and dependency management.
Reporting:  Power BI Semantic Model using Direct Lake mode (no data import required).

 Tech Stack
Platform: Microsoft Fabric (Trial Capacity)
Languages: Python, PySpark, SQL
Formats: Delta Lake, Parquet, JSON
Visualization: Power BI (Direct Lake)

Medallion Architecture:
    Bronze: Raw ingestion of complex nested JSON.
    Silver: Type enforcement, deduplication, and schema evolution handling.
    Gold:  Daily aggregations (Avg Price, Market Cap) optimized for BI.
Zero-Copy Reporting: Utilized Fabric's **Direct Lake** to query OneLake data directly from Power BI, eliminating refresh latency.
Resilient Pipelines: Built idempotent ingestion logic to handle re-runs and data overlaps without duplication.

## 📈 Visuals
<img width="940" height="428" alt="image" src="https://github.com/user-attachments/assets/af0cf72a-8e94-4696-bc1a-810e15354da3" />

<img width="934" height="423" alt="image" src="https://github.com/user-attachments/assets/cd22ea99-6780-4d67-8eed-07f565842921" />


Pipeline Success: Shows the automated orchestration of Bronze $\to$ Silver $\to$ Gold notebooks.
Executive Dashboard: Tracks $6T+ market cap trends with drill-down capabilities by asset.

## 👨‍💻 About Me
I am a Data Engineer with 3+ years of experience in **Azure**, **Oracle DBA**, and **Big Data** technologies. I specialize in building robust data platforms that bridge the gap between complex backend engineering and actionable business intelligence.

