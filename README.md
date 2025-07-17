---
title: "Optimising Cloud-Based Data Processing: A Case Study on Azure and Near-Earth Object Analysis"
author: "Fatimo Adeniya"
course: "LDS7005M – Big Data and Cloud Computing"
date: "2025"
version: "1.0"
---

# Optimising Cloud-Based Data Processing: A Case Study on Azure and Near-Earth Object Analysis

##  Project Overview

This project explores the design and implementation of a scalable cloud-based data processing pipeline using **Microsoft Azure** and **Apache Spark (Databricks)** to analyse a structured dataset of **Near-Earth Objects (NEOs)** obtained from NASA’s Open API. It demonstrates how cloud-native tools can be used to ingest, process, transform, and model large-scale scientific datasets for real-time decision support in aerospace analytics.

---

##  Dataset Information

- **Source**: NASA Open API via Kaggle  
- **Dataset Title**: `Nearest Earth Objects (1910–2024)`  
- **Records**: ~90,000+ NEO entries  
- **Format**: CSV (Structured)  
- **Key Fields**:
  - `id`, `name`
  - `absolute_magnitude_h`
  - `estimated_diameter_min/max`
  - `relative_velocity`
  - `miss_distance`
  - `orbiting_body`
  - `is_potentially_hazardous_asteroid`

---

##  Cloud Services Used

- **Azure Blob Storage** for cloud-native object storage  
- **Azure Databricks** for distributed compute and in-memory analytics (via Apache Spark)  
- **Azure Cost Management** for financial tracking  
- **Azure Monitor & Log Analytics** for performance monitoring  
- **Azure Active Directory & RBAC** for access control  
- **Parquet & Snappy compression** for storage optimisation

---

##  Processing Pipeline

1. **Data Ingestion**
   - CSV uploaded to Azure Blob container (`neoprojectdata/datasets`)
   - Accessed using secure token via Spark config

2. **Data Cleaning**
   - Removal of missing and duplicate entries using PySpark
   - Type casting and standardisation

3. **Feature Engineering**
   - Log-transformations to reduce skew
   - Composite metrics: `risk_ratio`, `velocity_to_size`

4. **Exploratory Data Analysis (EDA)**
   - Histograms, boxplots, heatmaps
   - Target distribution and correlation matrices

5. **Model Training**
   - Algorithms: Logistic Regression, Random Forest, XGBoost, KNN
   - SMOTE used for class imbalance correction
   - Evaluation metrics: Accuracy, Precision, Recall, AUC

---

##  Results Summary

| Model              | Accuracy | Precision | Recall | AUC  |
|-------------------|----------|-----------|--------|------|
| Logistic Regression | 72.5%   | 30.4%     | 89.5%  | 0.84 |
| Random Forest       | 87.1%   | 49.7%     | 73.8%  | 0.93 |
| XGBoost             | 75.5%   | 33.9%     | 96.1%  | 0.91 |
| KNN                 | 82.4%   | 40.1%     | 76.6%  | 0.86 |

- **Best Overall**: Random Forest (balanced performance)
- **Best Recall**: XGBoost (for risk-sensitive tasks)

---

##  Business and Scientific Implications

- Enables **early detection of potentially hazardous asteroids**
- Supports **planetary defense**, **risk assessment**, and **mission planning**
- Architecture aligns with real-world standards used by NASA, ESA, and commercial space firms

---

##  Security and Compliance

- AES-256 encryption (at rest)
- TLS/IPSec (in transit)
- GDPR, HIPAA, ISO/IEC 27001 compliant
- Role-Based Access Control (RBAC) and Multi-Factor Authentication (MFA)

---

##  Cost Optimisation Strategies

- Use of **Spot Instances** and **Auto-Termination** for compute savings  
- Tiered storage: Hot (active), Cool (archive)  
- Compression: Parquet + Snappy  
- Budget alerts via Azure Cost Management tools

---

##  Limitations

- No real-time streaming; batch-only processing
- Pre-1950 data sparsity may bias forecasts
- Interpretability limitations in ensemble models (no SHAP/LIME implemented)
- Dependent on Azure ecosystem (portability limits)

---

##  Directory Structure

```plaintext
 /azure-neo-pipeline
├── README.md
├── /notebooks
│   └── databricks_notebook.ipynb
├── /figures
│   └── *.png (all figures referenced in report)
├── /data
│   └── nearest-earth-objects.csv
