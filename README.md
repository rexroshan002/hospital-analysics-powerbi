# 🏥 Hospital Operations & Financial Analytics

![Power BI](https://img.shields.io/badge/Power_BI-Analytics-F2C811?style=for-the-badge\&logo=powerbi\&logoColor=black)
![Data Engineering](https://img.shields.io/badge/Data_Engineering-ETL-blue?style=for-the-badge)
![Star Schema](https://img.shields.io/badge/Data_Model-Star_Schema-darkgreen?style=for-the-badge)
![Business Intelligence](https://img.shields.io/badge/Business_Intelligence-Dashboard-success?style=for-the-badge)

---

# 📊 Executive Summary

**Hospital Operations & Financial Analytics** is a production-grade Business Intelligence solution designed to transform messy healthcare operational logs into a structured analytics platform capable of supporting executive-level decision making.

The system processes **67,000+ medical visit records** and converts fragmented, inconsistent operational data into **clear financial, operational, and patient behavior insights**.

The solution was engineered using a **strict dimensional modeling approach**, supported by robust **ETL pipelines**, semantic analytics logic, and a **dual-layer dashboard architecture** for both strategic and operational stakeholders.

---

# 🎯 Business Objective

Hospital leadership requires clear answers to questions such as:

**Financial Performance**

* How much revenue is the hospital generating?
* Which departments drive the highest financial value?
* Which providers generate the most revenue relative to their patient volume?

**Operational Capacity**

* Which days experience the highest patient traffic?
* Are there identifiable workload spikes requiring staffing adjustments?

**Patient Behavior**

* What percentage of patients return for follow-up care?
* Which demographics generate the highest healthcare revenue?
* Which acquisition channels bring the most valuable patients?

This project builds a **scalable analytics model** to answer those questions reliably.

---

# 📈 Key Quantitative Insights

After processing and modeling the dataset, the dashboard produced the following operational insights:

| Metric                      | Result             |
| --------------------------- | ------------------ |
| **Total Revenue Processed** | **$98.8M**         |
| **Total Visits Recorded**   | **67,476**         |
| **Unique Patients**         | **12,476**         |
| **Patient Follow-up Rate**  | **81.5%**          |
| **Top Revenue Department**  | **Radiology**      |
| **Top Performing Provider** | **Dr. Kavya Iyer** |

The **81.5% follow-up rate** indicates extremely strong patient retention and suggests a large proportion of recurring care such as diagnostics and chronic treatment monitoring.

---

# 🏗 System Architecture

The analytical system was designed using a **strict Star Schema**, a best-practice architecture for high-performance Business Intelligence models.

This structure separates **transactional facts** from **descriptive dimensions**, enabling faster aggregation and clean filtering behavior.

### Fact Table

**visits**

Contains a row for every recorded hospital encounter.

Key attributes include:

* visit identifier
* patient identifier
* doctor identifier
* service identifier
* visit type
* visit date
* revenue generated

---

### Dimension Tables

**patients**

Stores patient demographics including:

* age
* gender
* acquisition source
* demographic attributes

---

**doctors**

Contains provider information including:

* doctor name
* department
* specialization

---

**services**

Defines medical services and consultation categories.

---

**DateTable**

A generated calendar dimension enabling chronological analytics and operational time-series reporting.

---

# 🧹 Data Engineering & ETL

Real healthcare datasets contain numerous inconsistencies that must be resolved before analytics can be trusted.

The project includes a robust **Power Query ETL pipeline** responsible for transforming raw operational logs into structured analytical data.

---

## Indestructible Date Parsing

The raw dataset contained mixed international date formats including:

* `MM/DD/YYYY`
* `DD-MM-YYYY`
* `YYYY/MM/DD`
* textual date representations

A defensive **nested parsing strategy using Power Query M-Code** was implemented using multiple `try...otherwise` branches to safely interpret these formats.

This ensures **automated refresh pipelines never fail due to date format inconsistencies**.

---

## String Sanitization

Categorical values were heavily fragmented in the source data.

Examples included:

| Issue               | Example                      |
| ------------------- | ---------------------------- |
| Gender variation    | Male / male / M / Female / F |
| Visit type mismatch | Follow-up / Follow up        |
| Hidden whitespace   | "Referral "                  |

Transformations included:

* categorical consolidation
* whitespace trimming
* consistent label standardization

These steps prevent **dimension table fragmentation**, which can severely distort analytics results.

---

## Data Quality Improvements

Additional data reliability safeguards included:

* duplicate detection
* null value normalization
* column data type enforcement
* categorical consolidation

The resulting dataset provides **consistent, analytics-ready information** suitable for reporting and modeling.

---

# 🧠 Analytical Logic & Business Modeling

The semantic analytics layer was designed to calculate key operational metrics including:

* patient retention rates
* service demand distribution
* provider performance value
* demographic revenue segmentation

---

## Time Intelligence Modeling

A custom calendar table was generated with helper attributes to ensure proper chronological ordering and operational reporting.

Key derived attributes include:

* numeric month-year keys
* operational weekday indexing (Monday-first scheduling)
* calendar hierarchies for time-based analysis

This enables accurate **weekly operational load analysis and month-over-month trend evaluation**.

---

## Patient Retention Modeling

Patient engagement depth was calculated by analyzing repeat visits across the fact table.

Instead of relying on simple distinct counts, the model evaluates **visit frequency per patient** to determine true follow-up behavior.

This logic produced the **81.5% follow-up rate**, revealing strong recurring patient engagement.

---

## Demographic Segmentation

Patients were dynamically segmented into age groups to analyze revenue contribution patterns:

| Segment    | Age Range |
| ---------- | --------- |
| Pediatric  | 0 – 18    |
| Adult      | 19 – 40   |
| Middle Age | 41 – 60   |
| Senior     | 60+       |

This segmentation enables hospital leadership to understand **which population groups drive medical demand**.

---

# 📊 Dashboard Design

The final analytics interface is structured into **two analytical modules**.

---

## Page 1 — Executive Overview

Designed for hospital leadership and financial decision-makers.

Key visualizations include:

* Total revenue KPIs
* Patient volume indicators
* Service revenue composition charts
* Provider performance matrix comparing **value vs volume**

This page provides a **rapid operational snapshot of hospital performance**.

---

## Page 2 — Analytical Deep Dive

Designed for operational and strategic analysis.

Key insights include:

* visit distribution by day of week
* identification of **Monday patient surges**
* demographic revenue analysis
* acquisition source performance matrices

This layer supports **staffing optimization and marketing strategy evaluation**.

---

# 📂 Repository Structure

```
hospital-analytics
│
├── dashboard
│   └── hospital_analytics_dashboard.pbix
│
├── dataset
│   ├── patients.csv
│   ├── doctors.csv
│   ├── services.csv
│   └── visits.csv
│
├── images
│   ├── dashboard_overview.png
│   ├── revenue_analysis.png
│   └── provider_performance.png
│
└── README.md
```

---

# 🚀 Running the Project

### Requirements

Install **Power BI Desktop**

https://powerbi.microsoft.com/desktop/

---

### Setup

1. Clone the repository

```
git clone https://github.com/yourusername/hospital-analytics.git
```

2. Open the dashboard file

```
dashboard/hospital_analytics_dashboard.pbix
```

3. Update dataset paths if prompted.

4. Refresh the dataset to load the CSV files from `/dataset`.

---

# 💡 Skills Demonstrated

This project demonstrates practical **Business Intelligence engineering capabilities** including:

**Data Modeling**

* dimensional modeling
* star schema architecture
* relationship optimization

**Data Engineering**

* messy data normalization
* ETL transformation pipelines
* defensive data parsing

**Analytics Development**

* operational KPI modeling
* retention and engagement analysis
* demographic segmentation

**Data Visualization**

* executive dashboards
* operational performance analytics
* strategic decision-support reporting

---

# 👨‍💻 Author

**Rex Roshan**

Business Intelligence & Data Analytics
