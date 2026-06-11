# Analytics Content Performance Project

## Publisher Traffic & Affiliate Revenue Analytics Engineering Project

This project simulates a real-world analytics engineering workflow by transforming raw publisher traffic and affiliate revenue data into analytics-ready datasets for reporting, dashboarding, and business decision-making.

The project combines website traffic metrics from Google Analytics 4 (GA4) with affiliate revenue performance data to create scalable reporting tables that support content monetization analysis and performance measurement.

## Project Objectives

This project was designed to:

* Transform raw traffic and affiliate revenue exports into analytics-ready reporting tables
* Apply data modeling concepts commonly used in analytics engineering workflows
* Standardize and clean marketing data from multiple sources
* Create reusable business metrics for reporting and analysis
* Build scalable data models that support self-service reporting and dashboard development
* Demonstrate modern analytics engineering practices using Snowflake and SQL

---

# Tech Stack

| Tool               | Purpose                                   |
| ------------------ | ----------------------------------------- |
| Snowflake          | Cloud data warehouse                      |
| SQL                | Data transformation and modeling          |
| GitHub             | Version control and project documentation |
| Google Analytics 4 | Traffic and engagement data source        |
| Trackonomics       | Affiliate revenue data source             |

---

# Data Architecture

The project follows a layered analytics engineering architecture consisting of Raw, Staging, and Mart layers.

## Raw Layer

Raw CSV exports are loaded directly into Snowflake without modification.

Source data includes:

* GA4 traffic exports
* Affiliate revenue exports from Trackonomics

---

## Staging Layer

The staging layer standardizes and cleans source data before it is used in business models.

Key transformations include:

* URL normalization
* Removal of trailing slashes
* URL standardization and lowercasing
* Numeric data type conversion
* Standardized naming conventions
* Data cleaning and validation

Tables:

* `STAGING.CLEANED_GA4`
* `STAGING.COMMISSIONS`

---

## Mart Layer

The mart layer contains business-ready datasets designed for reporting, dashboarding, and analysis.

### MART_CONTENT_PERFORMANCE

Core reporting mart combining traffic and affiliate revenue metrics.

Key metrics include:

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

Business logic mart designed to identify content monetization opportunities.

Use cases include:

* High-traffic pages with low revenue
* High-traffic pages with no revenue
* High-revenue pages with lower traffic
* Content optimization opportunities

---

### MART_MONTHLY_CONTENT_PERFORMANCE

Monthly aggregated reporting table used for trend analysis and executive reporting.

Use cases include:

* Monthly KPI reporting
* Dashboard visualizations
* Revenue trend analysis
* Performance monitoring

---

# Key Business Metrics

## RPM (Revenue Per Thousand Pageviews)

Measures revenue efficiency relative to pageviews.

```sql
(COMMISSIONS / PAGEVIEWS) * 1000
```

## Commission Rate

Measures affiliate commission efficiency.

```sql
COMMISSIONS / SALES
```

## Orders Per Session

Measures conversion efficiency relative to traffic.

```sql
NUMBER_OF_ORDERS / SESSIONS
```

---

# Business Questions Solved

This project supports analysis such as:

* Which content drives the highest affiliate revenue?
* Which pages generate high traffic but low monetization?
* Which URLs have the highest revenue efficiency?
* Which content converts traffic most effectively?
* What content opportunities should be prioritized for optimization?

---

# Business Impact

This project demonstrates how raw publisher traffic and affiliate revenue data can be transformed into business-ready datasets that support content monetization decisions.

The resulting data models enable stakeholders to:

* Prioritize high-traffic pages with low revenue potential
* Identify high-performing content that can be replicated or expanded
* Evaluate revenue efficiency using standardized KPI calculations
* Support repeatable reporting and dashboard development
* Create scalable analytics assets for ongoing business monitoring

---

# Data Quality Considerations

To improve reporting accuracy and data reliability, the project includes:

* URL standardization prior to joins
* Numeric type conversion for exported metrics
* Null handling for incomplete records
* Divide-by-zero protection in KPI calculations
* Full outer joins to preserve unmatched traffic and revenue records
* Consistent business metric definitions

---

# SQL Concepts Demonstrated

This project demonstrates several analytics engineering and data modeling concepts, including:

* Common Table Expressions (CTEs)
* Data cleaning and transformation
* URL normalization
* Full outer joins
* Aggregations
* KPI calculations
* Business logic modeling
* Null handling
* Conditional logic
* Data validation techniques

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

# Future Enhancements

Potential future improvements include:

* dbt implementation
* Automated testing and validation
* Additional data quality monitoring
* Dashboard integration
* Marketing channel attribution modeling
* Historical trend analysis
* Documentation of data lineage and model dependencies

---

# About This Project

This project applies real-world publisher analytics experience to modern analytics engineering workflows.

The focus is on building clean, reliable, and business-ready datasets that support reporting, performance analysis, and decision-making through scalable data modeling practices.
