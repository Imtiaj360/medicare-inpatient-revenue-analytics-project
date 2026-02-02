# Medicare Inpatient Revenue & Payment Variance Analytics

[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![DuckDB](https://img.shields.io/badge/Database-DuckDB-orange?logo=duckdb&logoColor=white)](https://duckdb.org/)
[![Power BI](https://img.shields.io/badge/Visualization-Power_BI-yellow?logo=power-bi&logoColor=black)](https://powerbi.microsoft.com/)
[![Industry-Healthcare](https://img.shields.io/badge/Industry-Healthcare-red)](https://www.cms.gov/)

## Executive Overview
This project provides an end-to-end data audit of **Medicare Inpatient Hospital** payments. By processing over **146,427 records** from the CMS (Centers for Medicare & Medicaid Services) API, this analysis identifies revenue trends, medical complexity impacts, and systemic payment variances across the United States.

The primary objective was to perform a **Revenue Cycle Management (RCM) audit**, uncovering recovery opportunities where hospitals are significantly underpaid relative to regional benchmarks.

---

## Key Business Insights
* **The $701.31M Recovery Opportunity:** Audit-style analysis identified **728 hospitals** currently paid 30% below their state average for identical services.
* **Revenue Concentration:** Discovered that **25% of Diagnosis Related Groups (DRGs)** drive **90% of total Medicare revenue ($88.41B)**.
* **Geographic Leakage:** New York ($159M), Maryland ($136M), and California ($133M) show the highest potential for payment recovery.
* **Complexity Premium:** Analyzed how **Major Complications (MCC)** drive an average payment increase from $13.8K to $19.2K per case.
* **Patient Burden:** Determined a national average patient responsibility rate of **16.99%** of the total inpatient bill.

---

## Technical Workflow

### 1. Data Engineering (Python & DuckDB)
- **Extraction:** Automated ingestion of provider and service-level data via the CMS API.
- **Processing:** Used **DuckDB** for high-performance SQL analysis directly on DataFrames, enabling complex window functions to calculate state-level averages and standard deviations.
- **Cleaning:** Handled medical coding (DRGs) and provider taxonomies to ensure consistency across 2,945 hospitals.

### 2. Business Intelligence (Power BI)
Developed a multi-page executive dashboard to visualize:
- **Financial KPIs:** Total Revenue, Average Reimbursements, and Discharge Volumes.
- **Variance Audit:** Heatmaps and tables flagging specific "Underpaid Hospitals" by state.
- **Medical Complexity:** Revenue breakdowns by MCC (Major Complications) and CC (Complications) status.

---

## Repository Structure
```text
├── notebooks/
│   └── Medicare_Inpatient_Analysis.ipynb  
├── dashboard/
│   └── Medicare_Project_Dashboard.pdf    
├── requirements.txt                       
└── README.md                             
