# Go-To-Market Funnel Analytics

## Overview

This project simulates a real-world B2B analytics scenario where data from multiple CRM systems is consolidated, cleaned, and transformed into actionable business insights.

It covers the full pipeline from raw data ingestion to a Power BI dashboard, with a strong focus on funnel performance, conversion analysis, and data quality validation.

---

## Problem Statement

Organizations often operate with multiple CRM systems, leading to:

* Duplicate records across systems
* Inconsistent data formats
* Misaligned funnel stage tracking
* Unreliable conversion metrics

This project addresses these challenges by building a unified analytics layer for lead lifecycle tracking.

---

## End-to-End Data Pipeline

### 1. Raw Data Ingestion

* Two separate CRM datasets (simulating multiple HubSpot instances)

### 2. Data Standardization

* Harmonized schema across both sources
* Standardized fields such as lifecycle stages, timestamps, and identifiers

### 3. Merge & Deduplication

* Combined datasets into a single dataset
* Applied deduplication logic using unique identifiers

### 4. KPI & Funnel Logic

* Created lifecycle stage flags:

  * Lead
  * MQL (Marketing Qualified Lead)
  * SQL (Sales Qualified Lead)
  * Opportunity
  * Customer

* Built metrics:

  * Stage-wise conversion rates
  * Funnel progression
  * Drop-off analysis

### 5. Data Quality Validation (Critical Layer)

* Identified invalid funnel sequences:

  * SQL created before MQL
  * MQL created before Lead
  * Opportunity created before SQL
  * Customer created before Opportunity

* Ensures reliability of funnel metrics before business decisions are made

---

## Dashboard Features

### Funnel Overview

* End-to-end lifecycle visualization
* Stage-wise conversion tracking
* Lead-to-customer conversion rate

### Source Performance

* Lead volume vs conversion efficiency
* Channel-level performance comparison

### Owner Performance

* Individual-level performance tracking
* Lead ownership vs conversion efficiency

### Data Quality Insights

* Detection of invalid funnel progression
* Drill-down into problematic records

---

## Key Insights

* High lead volume sources do not always yield high conversion rates
* Some lower-volume sources show stronger conversion efficiency
* Owner performance varies across both volume and quality
* Data quality issues can distort funnel metrics if not identified

---

## Tech Stack

* Python (Pandas, Data Processing)
* Jupyter Notebooks
* Power BI (Data Modeling & Visualization)
* Excel (Intermediate outputs)

---

## Project Structure

data/
  raw/
    hubspot_instance_a_contacts.xlsx
    hubspot_instance_b_contacts.xlsx

  interim/
    hubspot_a_standardized.xlsx
    hubspot_b_standardized.xlsx
    combined_with_dedup_flags.xlsx

  processed/
    master_deduplicated_leads.xlsx
    master_leads_with_kpis.xlsx

notebooks/
  01_data_audit_and_eda.ipynb
  02_data_standardization.ipynb
  03_merge_and_dedup.ipynb
  04_funnel_kpis_and_validation.ipynb

outputs/
  tables/
    conversion_summary.xlsx
    funnel_summary.xlsx
    owner_summary.xlsx
    source_summary.xlsx
    stage_distribution.xlsx
    time_summary.xlsx
    validation_summary.xlsx

  dashboard/
    funnel_analytics_dashbaord.pbix

---
  
## How to Use

1. Run notebooks in sequence:

   * 01 → 04
2. Review processed datasets in `/data/processed`
3. Open Power BI dashboard in `/outputs/dashboard`
4. Explore funnel, source, and owner insights

---

## Author

Namrit Sheth
