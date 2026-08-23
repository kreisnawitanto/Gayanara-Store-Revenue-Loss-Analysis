# Gayanara Store Revenue Loss Analysis

## Project Overview

This project analyzes 4,986 transactional records from Gayanara Store to evaluate sales performance, identify root causes of revenue loss, assess product and category inefficiencies, and analyze regional logistics performance.

The analysis combines data cleaning, relational data modeling, exploratory data analysis (EDA), business analysis, and interactive dashboard development to transform raw transaction data into actionable business insights for the Sales Manager.

### Project Objectives

The analysis aims to:

- Map the magnitude and patterns of revenue loss over time.
- Identify specific products and categories contributing the most to revenue loss.
- Analyze sales performance geographically to detect underperforming locations.
- Provide data-driven recommendations regarding distribution strategy and product rationalization.
- Develop an interactive Looker Studio dashboard for business monitoring.

---

## Business Questions

This project addresses several core business questions from the Gayanara Store case study:

1. What is the total potential revenue lost during the analysis period, and what is the trend over time?
2. Which fashion products or categories generate the highest Revenue Loss, and what are the main drivers?
3. Which locations consistently show low performance and require operational review or sales suspension?
4. What tactical and strategic insights can be provided to support the Sales Manager's decisions?

---

# Data Preparation

## Dataset Overview

| Attribute | Description |
|---|---|
| Analysis Period | January 2022 – January 2025 |
| Relational Entities | 5 Tables (Customer, Order_Items, Orders, Products, Reviews) |
| Final Master Records | 4,986 |
| Total Gross Revenue | Rp1,300,000,000 |
| Total Revenue Loss | Rp235,010,000 |
| Standardized Categories | 6 Categories |
| Order Statuses | 5 (Delivered, Shipped, Cancelled, Processing, Returned) |

---

## Data Cleaning

The dataset was prepared before analysis to improve data quality, relational integrity, and consistency.

The main preparation steps included:

- Parsing raw delimited text records into clean tabular columns.
- Standardizing column data types and category formatting.
- Standardizing 14 raw product category variations into 6 canonical categories.
- Imputing missing values with standard placeholders (`Material` $\rightarrow$ "Tidak Diketahui", `review_text` $\rightarrow$ "Tidak ada komentar", `promo_code` $\rightarrow$ "Tanpa Promo").
- Feature engineering new boolean and numerical metrics (`is_lost_revenue` and `lost_amount_idr`).
- Designing an Entity-Relationship Diagram (ERD) to establish relational joins.
- Merging 5 distinct tables into a consolidated `Master_Data` table.
- Validating output integrity and data types across all merged records.

  ERD Design
  <img width="626" height="528" alt="ERD Model_ Master Data_Gayanara" src="https://github.com/user-attachments/assets/8b9b64d3-a913-4b72-b96e-a6ce7c13721d" />


### Data Quality Adjustment & Limitations

Certain columns with incomplete data were deliberately left unpopulated after consultation with the Data Lead. Rather than applying artificial imputation, these missing values were preserved to reflect real-world upstream data logging constraints, avoiding unsupported assumptions in the final analysis.

---

# Data Analysis

The analysis was performed using Excel for data modeling and transformation, and Looker Studio for visual exploration.

Key areas analyzed include:

- Overall sales performance and growth
- Revenue loss trends over time
- Order status distribution
- Top loss-contributing products and categories
- Geographic loss concentration
- Historical peak loss months

---

# Key Performance Indicators

The final analysis produced the following core metrics:

| KPI | Result | YoY Growth |
|---|---:|---:|
| Total Revenue | **Rp1,300,000,000** | **+129.8%** |
| Revenue Loss | **Rp235,010,000** | **+151.7%** |
| Revenue Loss % | **15.34%** | **+8.1%** |
| Problematic Orders | **778** | **+151.8%** |

### KPI Definitions

**Total Revenue**

Total gross transaction subtotal generated during the analysis period.

**Revenue Loss**

Monetary value lost due to cancelled or returned orders.

**Revenue Loss %**

Percentage of total potential revenue lost, exceeding the healthy fashion e-commerce threshold (~10%).

**Problematic Orders**

Total count of orders flagged with status `cancelled` or `returned`.

---

# Key Findings

## 1. Revenue Loss Outpaces Gross Revenue Growth

Gross Revenue grew by **129.8%** to reach Rp1.30 M, but Revenue Loss grew faster at **151.7%** to reach Rp235.01 Jt.

This indicates that financial losses are expanding faster than top-line sales growth as the business scales.

---

## 2. Order Cancellations Exceed Returns

Order status breakdown shows:

| Status | Proportion |
|---|---:|
| **Delivered** | **59.2%** |
| **Shipped** | **14.8%** |
| **Cancelled** | **10.9%** |
| **Processing** | **10.0%** |
| **Returned** | **5.0%** |

Because cancelled orders (10.9%) are double the returned orders (5.0%), revenue loss is primarily driven by pre-fulfillment processing friction rather than post-delivery product defects.

---

## 3. Outerwear and Bottoms Are High-Loss Categories

Jaket generated the highest category-level loss (**~Rp43M**), followed closely by Celana (**~Rp41M**).

At the SKU level, the top loss-generating products are:

1. *Jacket Denim Tropika Style* — **Rp5.4M**
2. *Celana Jeans Slim SandangIndo* — **Rp5.0M**
3. *Dress Wrap Pesona Indo* — **Rp4.2M**
4. *Dress Mini Casual SandangIndo* — **Rp4.1M**
5. *Topi Baseball Kanvas Lokal* — **Rp4.0M**

---

## 4. Specific Peak Months Experience Recurring Loss Spikes

May 2022 recorded the highest single-month loss rate at **~33%**.

Additionally, February appears twice in the Top 10 worst months (2022 and 2023), indicating recurring seasonal operational stress at the start of the year.

---

## 5. Jawa Barat and Manado Demand Regional Intervention

Jawa Barat generated the highest cumulative provincial loss (**~Rp28.6M** combined across Bandung and Depok).

Manado (Sulawesi Utara) represents the single city with the highest localized loss at **Rp21.28M** across 180 orders.

---

# Looker Studio Dashboard

An interactive Looker Studio dashboard was developed to provide real-time visibility into sales and loss metrics.

### Dashboard Components

**KPI Cards**

- Total Revenue
- Revenue Loss
- Revenue Loss %
- Jumlah Order Bermasalah

**Visualizations**

- Tren Revenue vs Loss Revenue
- Proporsi Status Pesanan
- Top 10 Bulan dengan Revenue Loss % Tertinggi
- Top 5 Produk Penyumbang Revenue Loss Terbesar
- Revenue Loss per Kategori
- Sebaran Revenue Loss per Wilayah

**Interactive Filters**

- Date Range
- Category
- Shipping Province

### Dashboard Preview

<img width="714" height="529" alt="Screenshot 2026-08-20 173944" src="https://github.com/user-attachments/assets/862a3cd8-9c4e-459d-a135-fa5a4859a78a" />
<img width="686" height="514" alt="Screenshot 2026-08-20 193501" src="https://github.com/user-attachments/assets/bccf2807-85de-4bc6-902c-28285d593831" />

*[View Interactive Dashboard Live](https://bit.ly/4x5g1lg)*

---

# Business Recommendations

Based on the analysis, several actionable recommendations are provided for the Sales Manager:

### 1. Enforce Pre-Fulfillment Processing SLAs

Address the 10.9% cancellation rate by setting strict packing and courier handoff SLAs during the `processing` phase to minimize pre-shipment customer drop-offs.

### 2. Audit Outerwear and Bottoms Supply Chain

Conduct dedicated quality and inventory audits for *Jacket Denim Tropika Style* and *Celana Jeans Slim SandangIndo* to address stock availability and product consistency.

### 3. Review 3PL Courier Partnerships in Critical Regions

Evaluate courier fulfillment partners servicing Jawa Barat (Bandung & Depok) and Manado to reduce shipping delays and transit issues in high-loss regions.

### 4. Prepare Early Inventory Buffers for Seasonal Peaks

Build inventory and operational buffers 2–3 weeks ahead of historical loss peak periods (specifically February and September) to prevent bottlenecking during demand surges.

---

# Tools & Technologies

### Data Preparation & Data Modeling

- Microsoft Excel (Data Cleaning, VLOOKUP, Power Functions)
- Visual Paradigm (ERD Maker)

### Business Intelligence & Visualization

- Google Looker Studio

### Documentation

- GitHub

---

# Project Workflow

```text
Raw Datasets (5 Tables)
     │
     ▼
Entity-Relationship Modeling (ERD)
     │
     ▼
Data Cleaning & Transformation
     │
     ▼
Feature Engineering (Loss Metrics)
     │
     ▼
Master_Data Consolidation
     │
     ▼
Looker Studio Dashboard
     │
     ▼
Business Findings
     │
     ▼
Actionable Recommendations
