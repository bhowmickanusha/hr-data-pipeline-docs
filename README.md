# HR Data Pipeline - Complete Documentation

## Overview
End-to-end data engineering pipeline for HR employee punch records and master data.

**Architecture:** Azure Data Factory → Databricks → Power BI

---

## Quick Links
- [Architecture Diagram](./ARCHITECTURE.md)
- [ADF Setup Guide](https://github.com/bhowmickanusha/hr-data-pipeline-adf/blob/main/documentation/ADF_SETUP.md)
- [Databricks Notebooks](https://github.com/bhowmickanusha/hr-data-pipeline-databricks/blob/main/README.md)
- [Troubleshooting](https://github.com/bhowmickanusha/hr-data-pipeline-docs/blob/main/docs/TROUBLESHOOTING.md)

---

## Repository Links
| Repository | Purpose | Link |
|------------|---------|------|
| ADF Pipeline | Data Factory pipelines & activities | [Link](https://github.com/bhowmickanusha/hr-data-pipeline-adf) |
| Databricks | ETL notebooks (Bronze/Silver/Gold) | [Link](https://github.com/bhowmickanusha/hr-data-pipeline-databricks) |
| Documentation | Complete guides & diagrams | This repo |

---

## Data Flow
Daily (23:59)

├── Oracle PUNCH_DATA → ADLS → Bronze

├── Bronze → Silver (transformation)

└── Silver → Gold (aggregations)

└── Power BI Dashboard

Weekly (Sunday 23:58)

├── Oracle EMP_SAL, EMP_MST, EMP_LEAVE_MST, EMP_LEAVE_DTL → ADLS → Bronze

├── Bronze → Silver

└── Silver → Gold (re-merge)
