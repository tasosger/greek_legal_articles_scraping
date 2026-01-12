# Exercise 1: Areios Pagos Legal Decisions Analysis

## Overview
This exercise involves web scraping, data extraction, and analysis of legal decisions from the Areios Pagos (Greek Supreme Court) website. The project scrapes decision data from 2024, processes it, and performs comprehensive data analysis and visualization.

## Contents

### 1. Web Scraping
- **Link Collection**: Scrapes decision links from the Areios Pagos website for the year 2024
- **Data Crawling**: Downloads HTML content for each decision page
- **Output**: Creates `apofaseis_links.csv` and `apofaseis_raw.csv` files

### 2. Data Extraction
Extracts structured information from the scraped HTML:
- **Decision IDs**: Unique identifiers for each decision
- **Judges**: Names of judges who participated in each case
- **Legal Articles**: References to legal articles (ΚΠολΔ, ΠΚ, ΚΠΔ, ΑΚ)
- **Sections**: Court sections and section numbers
- **Text Components**:
  - Introduction text
  - Legal reasoning
  - Final decision text
- **Dates**: Decision dates extracted from Greek text format
- **Output**: Creates `apofaseis_full.csv` and `apofaseis_final.csv` files

### 3. Data Cleaning
- Removes automatic translation warnings
- Cleans navigation links
- Processes and normalizes text content

### 4. Data Analysis & Visualization

#### Dataset Comparison
- Compares scraped dataset (2,471 decisions from 2024) with HuggingFace GreekLegalSum dataset (8,395 decisions from 2002-2017)
- Analyzes text length distributions
- Calculates summary-to-text ratios

#### Visualizations

1. **Year Distribution**: Histogram showing year coverage of legal decisions

2. **Text Length Analysis**:
   - Histogram of text length distribution in scraped dataset
   - Comparative histogram of text lengths between datasets

3. **Summary Ratio**: Violin plot comparing summary-to-text length ratios between datasets

4. **Section Analysis**:
   - Bar chart showing number of decisions per section
   - Horizontal bar chart for section numbers distribution

5. **Legal Articles**:
   - Top 15 most frequently referenced legal articles
   - Most common legal references including paragraphs

6. **Judges Analysis**:
   - Top 10 most frequently participating judges
   - Distribution of number of judges per case

7. **Case Categories**: Top 10 most common case categories (from HuggingFace dataset)

8. **Legal Verbs**: Most common legal verbs in final decisions (e.g., ΑΠΟΡΡΙΠΤΕΙ, ΔΕΧΕΤΑΙ, ΑΝΑΙΡΕΙ)

9. **Date Analysis**:
   - Top 10 most frequent decision dates (day & month)
   - Heatmap showing decision frequency by day and month in 2024

## Files

- `areios_pagos.ipynb`: Main Jupyter notebook containing all code
- `apofaseis_final.csv`: Final cleaned dataset with extracted information
- `apofaseis_links.csv`: Initial links scraped from the website
- `apofaseis_raw.csv`: Raw HTML content of decision pages
- `greek_legal_sum.csv`: HuggingFace dataset for comparison
- `report.docx`: Written report document

## Key Features

- **Web Scraping**: Automated collection of legal decisions from Areios Pagos website
- **Text Processing**: Advanced regex patterns for extracting structured data from unstructured text
- **Data Enrichment**: Extracts multiple data points including judges, articles, dates, and sections
- **Comparative Analysis**: Compares scraped data with existing HuggingFace dataset
- **Comprehensive Visualizations**: Multiple charts and graphs for data exploration

## Technologies Used

- Python
- BeautifulSoup (HTML parsing)
- Pandas (data manipulation)
- Matplotlib & Seaborn (visualization)
- Requests (web scraping)
- Regex (text pattern matching)
- HuggingFace Datasets (external dataset loading)

## Data Statistics

- **Scraped Dataset**: 2,471 decisions from 2024
- **Average Text Length**: ~5,732 words per decision
- **Average Summary Length**: ~109 words per decision
- **Date Coverage**: 2024 (with 28.94% missing dates)
- **Sections**: Multiple court sections (ΠΟΛΙΤΙΚΕΣ, etc.)
