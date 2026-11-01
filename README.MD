# 🏭 Poka-yoke Data Factory

Welcome to the **Poka-yoke Data Factory**—a centralized, domain-driven repository dedicated to generating realistic, "messy" synthetic enterprise datasets. 

Designed for data engineers and analysts, this repository houses programmatic data generators that intentionally inject real-world data anomalies (such as missing values, skewed distributions, type mismatches, and outliers) to stress-test ETL pipelines, Pandas transformations, and SQL models.

## 🛠️ Tech Stack
* Python 3.x | Pandas | NumPy

## ⚠️ Data Privacy & Synthetic Data Disclaimer
All datasets generated, stored, or referenced within this repository (`Poka-yoke_Data_Factory`) are strictly **synthetic and programmatically generated**

---

## 📂 Repository Structure

```text
Poka-yoke_Data_Factory/
│
├── auto_retail_datasets/        # Auto Retail domain (Sales, Inventory, Pricing)
│   ├── generator.py             # Python script generating dirty data via NumPy/Pandas
│   └── raw_ar_sales.csv         # Sample generated dataset
│
├── finance_datasets/            # (Coming Soon) Financial & Transactional data
├── hr_datasets/                 # (Coming Soon) Employee & Payroll metrics
│
├── requirements.txt             # Project dependencies
└── .gitignore                   # Ignored files (caches, virtual envs)