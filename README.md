# Optimising Cloud-Based Data Processing  
### A Case Study on Azure and Near-Earth Object Analysis

## Overview

This project presents a scalable big data pipeline designed to ingest, process, and model astronomical datasets on Near-Earth Objects (NEOs) using Microsoft Azure cloud technologies. Leveraging Azure Blob Storage and Apache Spark via Databricks, the architecture demonstrates how scientific datasets can be efficiently transformed into actionable insights that support real-time risk assessment and planetary defense analytics.
---

## Dataset Information

- **Source**: NASA Open API via Kaggle  
- **Dataset**: Nearest Earth Objects (1910–2024)  
- **Records**: ~90,000+  
- **Format**: CSV  
- **Key Features**:
  - ID, name
  - Absolute magnitude
  - Diameter estimates
  - Relative velocity
  - Miss distance
  - Orbiting body
  - Hazardous classification

---

## Cloud Services Used

- **Azure Blob Storage** for structured data ingestion  
- **Azure Databricks** for distributed Spark processing  
- **Azure Monitor** for performance metrics  
- **Azure Cost Management** for budget control  
- **RBAC & MFA** for secure access  
- **Parquet format** with Snappy compression for optimisation
---

## Processing Pipeline Summary

1. **Ingestion**  
   - Dataset uploaded to Azure Blob Storage  
   - Connected to Databricks using secure token-based access  

2. **Cleaning**  
   - Missing values dropped  
   - Data type casting and deduplication  

3. **Feature Engineering**  
   - Log transformation of skewed variables  
   - Composite metrics: `risk_ratio`, `velocity_to_size`  

4. **EDA (Exploratory Data Analysis)**  
   - Descriptive statistics, visualisation (histograms, heatmaps)  
   - Target class inspection and correlation analysis  

5. **Model Training**  
   - Algorithms: Logistic Regression, Random Forest, XGBoost, KNN  
   - SMOTE used to balance classes  
   - Metrics: Accuracy, Precision, Recall, AUC  

---

## Impact and Applications

- Improves early detection of hazardous NEOs  
- Enhances mission planning and disaster response forecasting  
- Supports explainable AI with engineered features and clean preprocessing  
- Aligns with real-world data science practices used in aerospace

---

## Security and Governance Highlights

- **AES-256** encryption at rest  
- **TLS/IPSec** during transit  
- Compliant with **GDPR**, **HIPAA**, **ISO/IEC 27001**  
- Access managed via **RBAC** and **Azure Active Directory**

---

## Project Directory Structure

```plaintext
 /azure-neo-pipeline
├── README.md
├── /notebooks
│   └── databricks_notebook.ipynb
├── /figures
│   └── *.png
├── /data
│   └── nearest-earth-objects.csv
