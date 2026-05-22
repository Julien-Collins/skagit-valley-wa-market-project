# Skagit Valley WA Real Estate Market Project

## Project Overview

This project is an end-to-end real estate analytics pipeline built using Python, PostgreSQL, SQL, and Tableau. The goal of the project was to transform raw MLS exports into a structured analytics platform capable of generating market intelligence and visual dashboards for Skagit Valley residential real estate trends.

The dashboard focuses on analyzing market behavior across multiple Skagit County cities between 2023–2026, including:

- Median Price Per Square Foot (PPSF)
- Days on Market (DOM)
- Sale-to-List Ratios
- Percentage of Homes Sold Over Asking Price
- City and subdivision-level trend analysis

---

# Technologies Used

| Technology | Purpose |
|---|---|
| Python | Data cleaning and transformation |
| Pandas | ETL and preprocessing workflows |
| PostgreSQL | Relational database and analytics layer |
| SQL | Analytical view creation and KPI calculations |
| Tableau | Interactive dashboard visualization |

---

# Project Architecture

```text
Raw MLS CSV Exports
        ↓
Python ETL / Data Cleaning
        ↓
PostgreSQL Database
        ↓
SQL Analytical Views
        ↓
Tableau Dashboard
        ↓
Business Intelligence Insights
```

---

# Python Data Cleaning Pipeline

The project began with multiple raw MLS export files covering different yearly periods.

## Objectives of the Python Workflow

The Python pipeline was designed to:

- Combine multiple MLS exports into one unified dataset
- Standardize column names
- Remove duplicate columns
- Handle inconsistent schemas across exports
- Create PostgreSQL-friendly naming conventions
- Prepare clean structured data for ingestion into PostgreSQL

---

## Key Python Features Used

- Pandas DataFrames
- Iterative file processing
- Path automation with `pathlib`
- Dynamic column validation
- Missing column handling
- CSV export automation

---

# Python ETL Script

The ETL workflow automated the ingestion and cleaning process before loading the data into PostgreSQL.

## Example Python Logic

```python
# Combine all files
final_df = pd.concat(dfs, ignore_index=True)

# Rename columns for PostgreSQL-friendly names
final_df.columns = final_col_names

# Save cleaned combined CSV
final_df.to_csv(OUTPUT_FILE, index=False)
```

---

# Python Cleaning Workflow Screenshots

## Data Cleaning Script (Part 1)

<img width="681" height="624" alt="pythonscriptmls" src="https://github.com/user-attachments/assets/03ce9e71-f768-4f20-a2fb-bc887f0ef369" />


## Data Cleaning Script (Part 2)

<img width="681" height="715" alt="pythonscriptmls2" src="https://github.com/user-attachments/assets/19cf61e5-a8aa-4b45-a0aa-472cd29fc705" />

---

# PostgreSQL Database Design

A PostgreSQL database was designed to simulate a production-style analytics platform.

The database architecture separated:
- raw ingestion layers
- staging transformations
- analytical reporting schemas

This structure improves scalability, organization, and downstream reporting efficiency.

---

# Database Schemas

| Schema | Purpose |
|---|---|
| raw_data | Raw imported MLS data |
| staging | Cleaned transformation layer |
| analytics | Analytical reporting views |
| api_integration | Future API expansion |
| public | Default PostgreSQL schema |

---

# PostgreSQL Database Structure

## Database Schema Architecture

<img width="375" height="715" alt="Screenshot 2026-05-22 at 2 29 32 PM" src="https://github.com/user-attachments/assets/dfe8ccda-7d37-4d5f-8a4b-ffd32e60218c" />


## Analytics Views

<img width="306" height="653" alt="Screenshot 2026-05-22 at 2 31 21 PM" src="https://github.com/user-attachments/assets/a574b441-cb25-4ba9-a33a-a8e579a9d81b" />

---

# SQL Analytics Layer

The SQL layer transformed transactional real estate data into analytical reporting datasets optimized for Tableau.

The project used analytical SQL views to create reusable KPIs and market intelligence metrics.

---

# Core SQL Views

## 1. analytics.mls_base_metrics

This foundational analytical view created:

- Price per square foot
- Sale-to-list ratios
- Sold-over-list indicators
- Time-series date extraction
- Market performance metrics

<img width="306" height="653" alt="mlsbasemetrics" src="https://github.com/user-attachments/assets/247a3949-e929-4f07-92de-6cbba78f5f0c" />

---

## 2. analytics.city_yearly_summary

This view aggregated yearly city-level metrics including:

- Total sales
- Median PPSF
- Average DOM
- Average sale-to-list %
- Percentage sold over asking

<img width="619" height="534" alt="yearlysumcity" src="https://github.com/user-attachments/assets/5756ae8b-8d77-4f73-8f4a-f3da556a27b4" />

### Advanced SQL Concepts Used

- Aggregations
- Statistical median calculations
- CASE statements
- Percent-based KPI logic
- Grouped analytics

<img width="375" height="715" alt="advsql" src="https://github.com/user-attachments/assets/b13d177c-607f-4b2d-88f7-694d2b8d1605" />


## 3. analytics.subdivision_yearly_summary

This view enabled:
- subdivision-level reporting
- neighborhood comparisons
- localized market analysis

<img width="616" height="427" alt="Screenshot 2026-05-22 at 3 31 01 PM" src="https://github.com/user-attachments/assets/7ed7dce6-31fb-4ef0-aa2e-184a29718250" />

---

## 4. analytics.monthly_market_summary

This view supported:
- seasonal trend analysis
- monthly market behavior tracking
- time-series market comparisons

---


# Tableau Dashboard

The Tableau dashboard was built to provide executive-level real estate market insights through interactive visual analytics.

---

# Dashboard Features

## KPI Cards

The dashboard includes high-level KPIs such as:
- Average DOM
- Median PPSF
- Sale-to-list %

---

# Visualizations Included

## 1. City Price Per Square Foot Trends

Tracks yearly pricing trends across major Skagit County cities.


## 2. DOM vs Sale-to-List Analysis

Analyzes competitiveness and seller leverage by market.

## 3. Percentage Sold Over Asking

Highlights market strength and buyer competition levels.

---

# Tableau Dashboard Screenshot

## Final Interactive Dashboard

<img width="1160" height="682" alt="tableauimage" src="https://github.com/user-attachments/assets/7fcd98da-c31d-411b-86d3-19f06a5ae51f" />

---

# Business Questions Addressed

This project was designed to answer questions such as:

- Which cities experienced the strongest PPSF growth?
- Which markets were most competitive?
- Where did homes sell above asking most frequently?
- How did DOM vary across cities?
- Which subdivisions demonstrated stronger pricing trends?

---

# Skills Demonstrated

## Data Engineering

- ETL pipeline development
- Data cleaning workflows
- Structured schema design

## SQL & Databases

- PostgreSQL
- View architecture
- Analytical SQL
- KPI calculations
- Aggregations and statistical functions

## Data Visualization

- Tableau dashboarding
- Interactive filtering
- Executive KPI reporting
- Dashboard layout design

## Real Estate Analytics

- Market trend analysis
- Seller leverage metrics
- Price-per-square-foot analysis
- Time-series market reporting

---

# Future Improvements

Potential future enhancements include:

- Automated MLS API ingestion
- Predictive pricing models
- Geographic heat maps
- Subdivision-level drilldowns
- Forecasting models using machine learning
- Web deployment of dashboard analytics

---

# Tableau Public Dashboard

https://public.tableau.com/views/SkagitValleyRealEstate/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link


---

# Author

Julien Collins

MS Data Analytics Candidate | Real Estate Broker | Data Analytics & Real Estate Intelligence Projects
