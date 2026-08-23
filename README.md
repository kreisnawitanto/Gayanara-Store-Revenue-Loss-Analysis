# Gayanara Fashion Online — Revenue Loss Analysis

## Project Overview

Gayanara Fashion Online is a sales performance and revenue loss analysis project developed to identify patterns of revenue leakage from cancelled and returned orders.

The project integrates customer, order, order item, product, and review data into a single analytical dataset. The analysis focuses on revenue loss across products, categories, locations, order status, and time periods.

The final analysis is presented through an interactive Power BI dashboard designed to support sales management decision-making.

---

## Business Problem

Gayanara Fashion Online experienced increasing business scale accompanied by revenue loss from cancelled and returned orders.

The key business concern is not only whether revenue is growing, but whether revenue loss is also increasing as the business grows.

This project addresses the following business questions:

1. How significant is the revenue loss?
2. Which products contribute the most to revenue loss?
3. Which categories have the highest revenue loss?
4. Which locations require further operational review?
5. Which periods show higher revenue-loss patterns?
6. How do cancelled and returned orders contribute to revenue loss?

---

## Business Objective

The objectives of this analysis are to:

- Measure the amount and rate of revenue loss.
- Identify products and categories with the highest revenue loss.
- Identify locations with significant revenue loss.
- Analyze revenue-loss patterns over time.
- Analyze order status associated with revenue loss.
- Provide data-driven recommendations for further operational investigation.

---

## Dataset

The project uses five source datasets:

| Dataset | Rows | Description |
|---|---:|---|
| Customer | 800 | Customer information |
| Orders | 3,000 | Order-level information |
| Order_Items | 4,986 | Order item and transaction information |
| Products | 300 | Product information |
| Reviews | 1,500 | Customer review information |

The five source tables were integrated into a single `Master_Data` dataset containing 4,986 rows and 25 columns.

---

## Data Preparation

The data preparation process included:

- Splitting delimited data into separate columns.
- Standardizing data formats and data types.
- Standardizing inconsistent category values.
- Reducing 14 category variations into 6 standardized categories.
- Handling missing values.
- Creating the `is_lost_revenue` indicator.
- Creating the `lost_amount_idr` metric.
- Designing an Entity Relationship Diagram (ERD).
- Integrating five source tables into `Master_Data`.
- Validating the merged dataset.

---

## Revenue Loss Definition

In this project, **Revenue Loss** is defined as revenue lost from orders with the following statuses:

- `Cancelled`
- `Returned`

Orders with these statuses are identified through the `is_lost_revenue` indicator.

The associated revenue loss is measured using `lost_amount_idr`.

### Revenue Loss Logic

```text
Order Status
     │
     ├── Cancelled ──→ Revenue Loss
     │
     ├── Returned ───→ Revenue Loss
     │
     └── Other ──────→ No Revenue Loss
