
# 🚢 Weather-Based Docking Safety Analysis  
*A Data Engineering Project*

## 📌 Project Overview

This project demonstrates an end-to-end **data engineering pipeline** that ingests raw weather data from CSV files, cleans and transforms it, stores it in **Microsoft SQL Server**, and produces actionable insights about whether weather conditions are **safe for a ship to dock at a given location for an extended period of time**.

The primary focus of this project is **data pipeline design, data quality handling, SQL–Python integration, and analytical reasoning**, rather than meteorological precision.

---

## 🎯 Problem Statement

Ships docked for long durations can be exposed to operational and structural risks due to adverse weather conditions such as:

- High wind speeds  
- Extreme temperatures  
- Persistent unfavorable cloud conditions  

The objective is to classify docking conditions into three categories:

- **SAFE**
- **RISK**
- **UNSAFE**

based on clearly defined engineering assumptions.

---

## 🧱 Project Architecture

```

Raw CSV Files
↓
Data Ingestion (Python)
↓
Data Cleaning & Validation
↓
Microsoft SQL Server
↓
Feature Engineering
↓
Safety Classification Logic
↓
Analytical Queries (SQL)
↓
Final CSV Report

```

---

## 🛠️ Tech Stack

- **Python** (pandas, pyodbc)
- **Microsoft SQL Server**
- **T-SQL**
- **CSV-based data ingestion**
- **Git / GitHub**

---

## 📁 Project Structure

```

weather-docking-safety/
│
├── data/
│   ├── raw/              # Original weather CSV files
│   ├── processed/        # Cleaned and validated data
│
├── scripts/
│   ├── ingest.py         # CSV ingestion logic
│   ├── clean.py          # Data cleaning & validation
│   ├── transform.py     # Feature engineering + SQL Server load
│   ├── analyze.py       # Docking safety classification
│
├── sql/
│   ├── schema.sql        # SQL Server table definitions
│   ├── queries.sql      # Analytical SQL queries
│
├── output/
│   └── reports/
│       └── docking_safety_report.csv
│
├── requirements.txt
├── .gitignore
└── README.md

```

---

## 🔄 Data Pipeline Steps

### 1️⃣ Data Ingestion
- Load multiple raw CSV weather files
- Validate schema consistency
- Merge data into a unified dataset

### 2️⃣ Data Cleaning
- Handle missing values
- Remove duplicate records
- Convert timestamps to UTC
- Enforce valid numeric ranges
- Remove corrupted or invalid observations

### 3️⃣ Database Storage (SQL Server)
- Persist cleaned data in Microsoft SQL Server
- Use structured schemas for reliability and scalability
- Enable efficient analytical querying with T-SQL

### 4️⃣ Feature Engineering
Derived features include:
- High wind indicator
- Extreme temperature indicator
- Composite weather risk score

### 5️⃣ Safety Classification
Each observation is classified as:
- **SAFE**
- **RISK**
- **UNSAFE**

using rule-based logic derived from engineered features.

---

## ⚠️ Docking Safety Rules (Engineering Assumptions)

| Condition | Classification |
|---------|----------------|
| Wind speed > 20 knots | UNSAFE |
| Temperature < -5°C or > 40°C | RISK |
| High cloud coverage + strong wind | RISK |
| Otherwise | SAFE |

> These thresholds are simplified engineering assumptions used to demonstrate analytical logic and pipeline design. They are not intended to represent official maritime safety regulations.

---

## 📊 Output

The final output of the pipeline is a CSV report containing:

- Location  
- Date  
- Weather metrics  
- Docking safety classification  
- Primary risk reason  

```

output/reports/docking_safety_report.csv

````

This report is suitable for downstream analytics, dashboards, or operational decision-making systems.

---

## 🧠 Example Analytical Questions Answered

- Which locations experience the highest percentage of unsafe docking days?
- What is the longest continuous unsafe docking period per location?
- How does docking safety vary across months?
- Which weather factor contributes most to docking risk?

---

## ▶️ How to Run the Project

1. Clone the repository
```bash
git clone https://github.com/huseyinozerr/weather-docking-safety.git
cd weather-docking-safety
````

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Set up Microsoft SQL Server

* Create a database (e.g. `weather_safety`)
* Execute `sql/schema.sql` to create tables

4. Run the pipeline scripts in order

```bash
python scripts/ingest.py
python scripts/clean.py
python scripts/transform.py
python scripts/analyze.py
```

---

## 🚀 What This Project Demonstrates

* End-to-end data pipeline construction
* Robust data cleaning and validation
* Python and SQL Server integration
* Analytical problem-solving with real-world constraints
* Clean project organization and version control practices

---

## 🔮 Possible Extensions

* Orchestrate the pipeline using Airflow
* Store raw data in cloud object storage
* Add real-time weather ingestion
* Build dashboards using Power BI
* Containerize the pipeline using Docker

---

## 📬 Contact

GitHub: [https://github.com/huseyinozerr](https://github.com/huseyinozerr)

```
```
