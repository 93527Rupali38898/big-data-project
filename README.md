# Real-Time Disease Outbreak Detection using Apache Spark

## Overview

This project implements a scalable Big Data pipeline to detect disease outbreak patterns using real-time patient vitals, medical test results, clinical notes, and demographic data.

It integrates both **batch and streaming data** using Apache Spark to identify abnormal spikes and generate alerts for healthcare systems.

---

## Problem Statement

Healthcare systems generate massive structured and unstructured data daily. The objective is to:

* Detect early signs of disease outbreaks (e.g., fever, infections)
* Process large-scale heterogeneous data efficiently
* Monitor healthcare system load
* Generate real-time alerts for hospitals

---

## Tech Stack

* Apache Spark (PySpark)
* Spark Streaming / Structured Streaming
* Python (Pandas, NumPy)
* Kafka / Socket (stream simulation)
* NLP for clinical notes processing
* Matplotlib and Plotly for visualization

---

## Data Sources

* **Patient Demographics (CSV):** patient_id, age, gender, city
* **Medical Test Results (JSON):** test_name, result_value, test_date
* **Billing & Insurance Claims (Parquet):** claim data
* **Clinical Notes (TXT):** unstructured symptom data
* **Streaming Vitals (JSON):** temperature, heart rate, etc.

---

## Pipeline Architecture

1. Data Ingestion (Batch and Streaming)
2. Data Cleaning and Preprocessing
3. Data Integration using Spark joins
4. NLP processing for clinical notes
5. Feature extraction and transformation
6. Aggregation by region and time
7. Outbreak detection and alert generation

---

## Key Modules

### PS-1: Early Outbreak Detection

* Combines real-time vitals with historical test data
* Detects abnormal temperature and test patterns
* Identifies region-wise outbreak hotspots

### PS-2: Sociodemographic Risk Profiling

* Groups patients by age and gender
* Calculates abnormal test risk rates
* Identifies high-risk population segments

### PS-3: Outbreak vs Healthcare Load Analysis

* Extracts symptoms from clinical notes using NLP
* Correlates symptom spikes with insurance claims
* Measures healthcare system pressure

### PS-4: Hospital Resource Alert System

* Monitors real-time patient vitals
* Tracks hospital workload using claims data
* Generates alerts based on stress index

---

## Results

### Dataset Summary

* Total Patients: 200
* Total Vitals Records: 1000
* Total Test Results: 500

### Key Findings

* Patients with fever: 191
* Abnormal test cases: 148
* Outbreak-like cases detected: 140

### Region-wise Outbreak (Top Cities)

* Bangalore: 117 cases
* Chennai: 110 cases
* Hyderabad: 109 cases
* Delhi: 87 cases

### Risk Insights

* Highest risk observed in age group 19–35 (male)
* Overall abnormal test rate ≈ 46.5%

### Healthcare Load Analysis

* Hyderabad showed highest overload (~58%)
* Strong correlation between symptoms and claims

### Outputs Generated

* outbreak_map_data.csv
* outbreak_barchart.csv
* ps2_risk_profile.csv
* ps3_region_outbreak_claims.csv
* Visualization charts (.png)

---

## Project Structure

```id="clean123"
big-data-project/
│── PS1_EarlyOutbreakDetection.ipynb
│── PS2_groupbased_risk.ipynb
│── PS3_RegionLevelOutbreakVsLoad.ipynb
│── PS4_HospitalAlertSystem.ipynb
│── README.md
```

---

## How to Run

1. Clone the repository

```bash id="run1"
git clone https://github.com/93527Rupali38898/big-data-project.git
cd big-data-project
```

2. Install dependencies

```bash id="run2"
pip install pyspark pandas matplotlib seaborn plotly
```

3. Launch Jupyter Notebook

```bash id="run3"
jupyter notebook
```

4. Execute notebooks in sequence: PS1 → PS4

---

## Real-World Impact

This project demonstrates how Big Data technologies can be applied in healthcare for:

* Early outbreak detection
* Efficient resource allocation in hospitals
* Real-time patient monitoring
* Data-driven decision making

---

## Future Improvements

* Build real-time dashboards (Streamlit / Power BI)
* Integrate real-world healthcare datasets
* Improve NLP using advanced models (BERT)
* Deploy on cloud platforms (AWS / GCP)

---

## Author

Rupali Goyal

---

## Note

This project was developed as part of hands-on learning in Big Data and distributed systems.
