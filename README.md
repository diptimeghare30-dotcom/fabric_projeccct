# 🚀 Metadata-Driven Data Pipeline with Data Validation & CI/CD (Microsoft Fabric)

![Fabric](https://img.shields.io/badge/Microsoft-Fabric-blue)
![PySpark](https://img.shields.io/badge/PySpark-Data%20Engineering-orange)
![Delta](https://img.shields.io/badge/Delta-Lakehouse-green)
![CI/CD](https://img.shields.io/badge/CI%2FCD-Enabled-success)
![Status](https://img.shields.io/badge/Project-Production--Ready-brightgreen)

---

## 📌 Overview

This project demonstrates a **production-grade, metadata-driven data pipeline** built using **Microsoft Fabric Lakehouse** and **PySpark**.

It is designed to simulate real-world data engineering workflows, including:
- Dynamic data ingestion
- Rule-based data validation
- Bad records tracking
- Incremental data processing
- Bronze → Silver → Gold architecture
- CI/CD deployment pipelines

---

## 🏗️ Architecture

```
Landing → Bronze → Validation → Stage → Silver → Gold
```

---

## 🛠️ Tech Stack

| Category | Technology |
|---------|------------|
| Platform | Microsoft Fabric |
| Processing | PySpark |
| Storage | Lakehouse (Delta Tables) |
| Querying | SQL |
| Pipeline | Fabric Pipelines |
| CI/CD | Deployment Pipelines |

---

## ⚙️ Setup & Installation

### Prerequisites
- Microsoft Fabric Workspace
- Lakehouse created
- PySpark environment enabled

### Steps

1. Clone the repository
```bash
git clone https://github.com/your-username/metadata-driven-data-pipeline.git
cd metadata-driven-data-pipeline
```

2. Upload files to Fabric Lakehouse

3. Run setup notebook:
```python
nb_setup_table.py
```

4. Execute pipeline scripts in order:
- ingestion_pipeline.py
- data_validation.py
- stage_processing.py
- silver_merge.py
- gold_aggregation.py

---

## 🔄 Pipeline Workflow

### 1️⃣ Metadata-Driven Ingestion
- Reads metadata table
- Dynamically loads files
- Writes to Bronze tables

**Example:**
```
customers.csv → bronze_db.customers
```

---

### 2️⃣ Data Validation Framework

Rules are stored in metadata:

| Rule Type | Description |
|----------|------------|
| check_primary_key | Duplicate detection |
| check_nulls | Null validation |
| check_regex_email_format | Email validation |
| check_whitelist | Allowed values |
| check_null_or_zero | Invalid numeric check |

Bad records stored in:
```
audit_db.bad_records_tbl
```

---

### 3️⃣ Stage Layer Processing
- Separates:
  - Bad Records (`_br`)
  - Good Records (`_gr`)

---

### 4️⃣ Silver Layer (MERGE / UPSERT)
- Handles:
  - Updates
  - Inserts
- Adds:
  - UpdateLoadID
  - UpdateTimestamp

---

### 5️⃣ Gold Layer (Business Insights)

**Example:**
```
Top 10 Customer Cities
```

Output Table:
```
gold_db.top10_customer_cities
```

---

## 📊 Key Features

- ✅ Metadata-driven design (no hardcoding)
- ✅ Reusable pipeline architecture
- ✅ Data quality validation framework
- ✅ Audit logging & monitoring
- ✅ Bad records tracking system
- ✅ Incremental processing (MERGE)
- ✅ Scalable Lakehouse architecture
- ✅ CI/CD integration (Dev → Test → Prod)

---

## 🚀 CI/CD Implementation

- Fabric Deployment Pipeline:
  - Dev → Test → Prod
- Workspace-based promotion
- Automated artifact deployment

---

## 📈 Example Use Case

E-commerce dataset:
- Customers
- Orders
- Products

---

## 🔮 Future Enhancements

- Streaming ingestion (real-time)
- Power BI dashboards
- SCD Type 2 implementation
- REST API ingestion
- Data quality scorecards

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repo  
2. Create a new branch  
3. Commit your changes  
4. Open a Pull Request  
