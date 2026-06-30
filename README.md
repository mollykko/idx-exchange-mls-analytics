# IDX Exchange MLS Analytics

Data analyst internship project analyzing Southern California MLS transaction data from CRMLS (California Regional Multiple Listing Service).

## Overview
This repository contains Python scripts for processing and analyzing monthly MLS listing and sold transaction data. The final deliverable is two interactive Tableau dashboards covering market analysis and competitive intelligence.

## Objectives
- Aggregate monthly MLS listing and sold transaction data into unified datasets
- Clean and validate raw MLS data including date consistency and geographic checks
- Enrich datasets with 30-year fixed mortgage rate data from FRED
- Engineer key housing market metrics including price ratios, price per square foot, and days on market
- Detect and handle outliers using statistical methods
- Build interactive Tableau dashboards for market trend analysis and competitive intelligence
- Produce a 1-page market intelligence report and 5-minute presentation

## Data
- Source: CRMLS via CoreLogic Trestle API
- Coverage: January 2024 through May 2026
- Residential listings: 591,977 rows
- Residential sold transactions: 430,635 rows

## Tools
- Python (pandas)
- Tableau Public

## Week 1 — Monthly Dataset Aggregation

Completed:
- Found and loaded all monthly CRMLS listing files (`CRMLSListing*.csv`) from the `Data/` folder — 29 files total.
- Found and loaded all monthly CRMLS sold files (`CRMLSSold*.csv`) from the `Data/` folder, including `_filled` versions — 29 files total.
- Dropped the extra `latfilled` and `lonfilled` columns present in `_filled` sold files (where applicable).
- Concatenated each set of monthly files into two combined datasets:
  - `listings.csv`
  - `sold.csv`
- Filtered both datasets to `PropertyType == "Residential"` only.
- Printed row counts before and after concatenation.
- Printed row counts before and after the Residential filter.

### Week 1 Row Counts

Listing dataset:
- Files found: 29
- Rows after concatenation: 930,311
- Rows after Residential filter: 591,977

Sold dataset:
- Files found: 29
- Rows after concatenation: 640,335
- Rows after Residential filter: 430,635

## How to Run

Place the raw monthly CSV files in a local folder named `Data/` (relative to the `Scripts/` folder).

Then run:
python week1_listings.py
python week1_sold.py

Each script creates an `Outputs/` folder (if it doesn't already exist) and saves:
- `listings.csv` (from `week1_listings.py`)
- `sold.csv` (from `week1_sold.py`)

## Repository Notes

This repository is updated weekly throughout the internship. It includes Python scripts, documentation, and project notes, but excludes raw MLS data and generated CSV files.
