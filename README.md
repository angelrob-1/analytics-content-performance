# Analytics Content Performance Project

## Publisher Traffic & Affiliate Revenue Analytics Engineering Project

This project simulates a real-world analytics engineering workflow using publisher traffic and affiliate revenue data.

The goal of this project is to transform raw marketing and monetization exports into analytics-ready data models that can be used for reporting, dashboards, and business insights.

The project combines:

* GA4 traffic data
* Affiliate revenue data from Trackonomics
* SQL transformations in Snowflake
* Data modeling concepts used in analytics engineering

---

# Project Goals

This project was built to:

* Practice analytics engineering workflows
* Build business-ready SQL models
* Standardize messy marketing data
* Create scalable reporting tables
* Demonstrate analytics engineering skills for portfolio purposes

---

# Tech Stack

| Tool                | Purpose                                   |
| ------------------- | ----------------------------------------- |
| Snowflake           | Cloud data warehouse                      |
| SQL                 | Data transformations and modeling         |
| GitHub              | Version control and project documentation |
| GA4 Export          | Traffic and engagement source             |
| Trackonomics Export | Affiliate revenue source                  |

---

# Data Architecture

## Raw Layer

Raw CSV exports uploaded into Snowflake.

Examples:

* Raw GA4 traffic export
* Raw affiliate revenue export

---

## Staging Layer

The staging layer standardizes and cleans source data.

Examples of transformations:

* URL normalization
* Removing trailing slashes
* Lowercasing URLs
* Converting text metrics into numeric data types
* Standardizing column names

Tables:

* `STAGING.CLEANED_GA4`
* `STAGING.COMMISSIONS`

---

## Mart Layer

The mart layer contains business-ready tables used for reporting and analytics.

### MART_CONTENT_PERFORMANCE

Core performance mart combining traffic and affiliate revenue metrics.

Metrics include:

* Sessions
* Pageviews
* Commissions
* Sales
* Orders
* RPM
* Commission Rate
* Orders Per Session

---

### MART_CONTENT_OPPORTUNITIES

Business logic mart used to identify:

* High traffic / low revenue pages
* High traffic / no revenue pages
* High revenue / lower traffic pages
* High-performing content opportunities

---

### MART_MONTHLY_CONTENT_PERFORMANCE

Monthly aggregated performance table.

Used for:

* Trend analysis
* Executive reporting
* Dashboard visualizations
* Monthly KPI reporting

---

# Key Business Metrics

## RPM

Revenue Per Thousand Pageviews.

```sql
(COMMISSIONS / PAGEVIEWS) * 1000
```

---

## Commission Rate

Measures affiliate commission efficiency.

```sql
COMMISSIONS / SALES
```

---

## Orders Per Session

Measures conversion efficiency.

```sql
NUMBER_OF_ORDERS / SESSIONS
```

---

# Example Business Questions Solved

* Which content drives the highest affiliate revenue?
* Which pages generate high traffic but low monetization?
* Which pages have the highest RPM?
* Which URLs convert traffic most efficiently?
* What are the best-performing commerce content opportunities?

---

# SQL Concepts Used

This project demonstrates several core analytics engineering skills:

* Common Table Expressions (CTEs)
* URL normalization
* Data cleaning
* Aggregations
* Full outer joins
* KPI calculations
* Business logic modeling
* Handling null values
* Preventing divide-by-zero errors

---

# Repository Structure

```text
analytics-content-performance/
│
├── sql/
│   ├── staging/
│   ├── marts/
│
├── screenshots/
│
├── dashboards/
│
├── README.md
```

---

# Future Improvements

Planned future enhancements include:

* dbt implementation
* Automated testing
* Data quality checks
* Dashboard integration
* Additional traffic source modeling
* Channel attribution modeling
* Historical trend analysis

---

# About This Project

This project was built as part of a transition from SEO and marketing analytics into analytics engineering.

The project focuses on applying real-world publisher analytics experience to modern data modeling and analytics engineering workflows.

---
