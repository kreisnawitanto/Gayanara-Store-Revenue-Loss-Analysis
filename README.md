# Gayanara Store Revenue Loss Analysis

## Project Overview

This project analyzes 4,986 transactional records from Gayanara Store to evaluate sales performance, identify root causes of revenue loss, assess product and category inefficiencies, and analyze regional logistics performance[cite: 1].

The analysis combines data cleaning, relational data modeling, exploratory data analysis (EDA), business analysis, and interactive dashboard development to transform raw transaction data into actionable business insights for the Sales Manager[cite: 1].

### Project Objectives

The analysis aims to:

- Map the magnitude and patterns of revenue loss over time[cite: 1].
- Identify specific products and categories contributing the most to revenue loss[cite: 1].
- Analyze sales performance geographically to detect underperforming locations[cite: 1].
- Provide data-driven recommendations regarding distribution strategy and product rationalization[cite: 1].
- Develop an interactive Looker Studio dashboard for business monitoring[cite: 1].

---

## Business Questions

This project addresses several core business questions from the Gayanara Store case study:

1. What is the total potential revenue lost during the analysis period, and what is the trend over time?[cite: 1]
2. Which fashion products or categories generate the highest Revenue Loss, and what are the main drivers?[cite: 1]
3. Which locations consistently show low performance and require operational review or sales suspension?[cite: 1]
4. What tactical and strategic insights can be provided to support the Sales Manager's decisions?[cite: 1]

---

# Data Preparation

## Dataset Overview

| Attribute | Description |
|---|---|
| Analysis Period | January 2022 – January 2025[cite: 1] |
| Relational Entities | 5 Tables (Customer, Order_Items, Orders, Products, Reviews)[cite: 1] |
| Final Master Records | 4,986[cite: 1] |
| Total Gross Revenue | Rp1,300,000,000[cite: 1] |
| Total Revenue Loss | Rp235,010,000[cite: 1] |
| Standardized Categories | 6 Categories[cite: 1] |
| Order Statuses | 5 (Delivered, Shipped, Cancelled, Processing, Returned)[cite: 1] |

---

## Data Cleaning

The dataset was prepared before analysis to improve data quality, relational integrity, and consistency[cite: 1].

The main preparation steps included:

- Parsing raw delimited text records into clean tabular columns[cite: 1].
- Standardizing column data types and category formatting[cite: 1].
- Standardizing 14 raw product category variations into 6 canonical categories[cite: 1].
- Imputing missing values with standard placeholders (`Material` $\rightarrow$ "Tidak Diketahui", `review_text` $\rightarrow$ "Tidak ada komentar", `promo_code` $\rightarrow$ "Tanpa Promo")[cite: 1].
- Feature engineering new boolean and numerical metrics (`is_lost_revenue` and `lost_amount_idr`)[cite: 1].
- Designing an Entity-Relationship Diagram (ERD) to establish relational joins[cite: 1].
- Merging 5 distinct tables into a consolidated `Master_Data` table[cite: 1].
- Validating output integrity and data types across all merged records[cite: 1].

### Data Quality Adjustment & Limitations

Certain columns with incomplete data were deliberately left unpopulated after consultation with the Data Lead. Rather than applying artificial imputation, these missing values were preserved to reflect real-world upstream data logging constraints, avoiding unsupported assumptions in the final analysis.

---

# Data Analysis

The analysis was performed using Excel for data modeling and transformation, and Looker Studio for visual exploration[cite: 1].

Key areas analyzed include:

- Overall sales performance and growth[cite: 1]
- Revenue loss trends over time[cite: 1]
- Order status distribution[cite: 1]
- Top loss-contributing products and categories[cite: 1]
- Geographic loss concentration[cite: 1]
- Historical peak loss months[cite: 1]

---

# Key Performance Indicators

The final analysis produced the following core metrics:

| KPI | Result | YoY Growth |
|---|---:|---:|
| Total Revenue | **Rp1,300,000,000** | **+129.8%**[cite: 1] |
| Revenue Loss | **Rp235,010,000** | **+151.7%**[cite: 1] |
| Revenue Loss % | **15.34%** | **+8.1%**[cite: 1] |
| Problematic Orders | **778** | **+151.8%**[cite: 1] |

### KPI Definitions

**Total Revenue**

Total gross transaction subtotal generated during the analysis period[cite: 1].

**Revenue Loss**

Monetary value lost due to cancelled or returned orders[cite: 1].

**Revenue Loss %**

Percentage of total potential revenue lost, exceeding the healthy fashion e-commerce threshold (~10%)[cite: 1].

**Problematic Orders**

Total count of orders flagged with status `cancelled` or `returned`[cite: 1].

---

# Key Findings

## 1. Revenue Loss Outpaces Gross Revenue Growth

Gross Revenue grew by **129.8%** to reach Rp1.30 M, but Revenue Loss grew faster at **151.7%** to reach Rp235.01 Jt[cite: 1].

This indicates that financial losses are expanding faster than top-line sales growth as the business scales[cite: 1].

---

## 2. Order Cancellations Exceed Returns

Order status breakdown shows:

| Status | Proportion |
|---|---:|
| **Delivered** | **59.2%**[cite: 1] |
| **Shipped** | **14.8%**[cite: 1] |
| **Cancelled** | **10.9%**[cite: 1] |
| **Processing** | **10.0%**[cite: 1] |
| **Returned** | **5.0%**[cite: 1] |

Because cancelled orders (10.9%) are double the returned orders (5.0%), revenue loss is primarily driven by pre-fulfillment processing friction rather than post-delivery product defects[cite: 1].

---

## 3. Outerwear and Bottoms Are High-Loss Categories

Jaket generated the highest category-level loss (**~Rp43M**), followed closely by Celana (**~Rp41M**)[cite: 1].

At the SKU level, the top loss-generating products are:

1. *Jacket Denim Tropika Style* — **Rp5.4M**[cite: 1]
2. *Celana Jeans Slim SandangIndo* — **Rp5.0M**[cite: 1]
3. *Dress Wrap Pesona Indo* — **Rp4.2M**[cite: 1]
4. *Dress Mini Casual SandangIndo* — **Rp4.1M**[cite: 1]
5. *Topi Baseball Kanvas Lokal* — **Rp4.0M**[cite: 1]

---

## 4. Specific Peak Months Experience Recurring Loss Spikes

May 2022 recorded the highest single-month loss rate at **~33%**[cite: 1].

Additionally, February appears twice in the Top 10 worst months (2022 and 2023), indicating recurring seasonal operational stress at the start of the year[cite: 1].

---

## 5. Jawa Barat and Manado Demand Regional Intervention

Jawa Barat generated the highest cumulative provincial loss (**~Rp28.6M** combined across Bandung and Depok)[cite: 1].

Manado (Sulawesi Utara) represents the single city with the highest localized loss at **Rp21.28M** across 180 orders[cite: 1].

---

# Looker Studio Dashboard

An interactive Looker Studio dashboard was developed to provide real-time visibility into sales and loss metrics[cite: 1].

### Dashboard Components

**KPI Cards**

- Total Revenue[cite: 1]
- Revenue Loss[cite: 1]
- Revenue Loss %[cite: 1]
- Jumlah Order Bermasalah[cite: 1]

**Visualizations**

- Tren Revenue vs Loss Revenue[cite: 1]
- Proporsi Status Pesanan[cite: 1]
- Top 10 Bulan dengan Revenue Loss % Tertinggi[cite: 1]
- Top 5 Produk Penyumbang Revenue Loss Terbesar[cite: 1]
- Revenue Loss per Kategori[cite: 1]
- Sebaran Revenue Loss per Wilayah[cite: 1]

**Interactive Filters**

- Date Range[cite: 1]
- Category[cite: 1]
- Shipping Province[cite: 1]

### Dashboard Preview

<img width="918" height="522" alt="Looker Studio Dashboard Preview" src="https://bit.ly/4x5g1lg" />

*[View Interactive Dashboard Live](https://bit.ly/4x5g1lg)*[cite: 1]

---

# Business Recommendations

Based on the analysis, several actionable recommendations are provided for the Sales Manager:

### 1. Enforce Pre-Fulfillment Processing SLAs

Address the 10.9% cancellation rate by setting strict packing and courier handoff SLAs during the `processing` phase to minimize pre-shipment customer drop-offs[cite: 1].

### 2. Audit Outerwear and Bottoms Supply Chain

Conduct dedicated quality and inventory audits for *Jacket Denim Tropika Style* and *Celana Jeans Slim SandangIndo* to address stock availability and product consistency[cite: 1].

### 3. Review 3PL Courier Partnerships in Critical Regions

Evaluate courier fulfillment partners servicing Jawa Barat (Bandung & Depok) and Manado to reduce shipping delays and transit issues in high-loss regions[cite: 1].

### 4. Prepare Early Inventory Buffers for Seasonal Peaks

Build inventory and operational buffers 2–3 weeks ahead of historical loss peak periods (specifically February and September) to prevent bottlenecking during demand surges[cite: 1].

---

# Tools & Technologies

### Data Preparation & Data Modeling

- Microsoft Excel (Data Cleaning, VLOOKUP, Power Functions)[cite: 1]
- Visual Paradigm (ERD Maker)[cite: 1]

### Business Intelligence & Visualization

- Google Looker Studio[cite: 1]

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
