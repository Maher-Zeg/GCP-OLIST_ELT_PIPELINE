# 🛒 Olist E-Commerce Data Mart — BigQuery

## 🎯 Business Objective
Build a complete e-commerce data mart on GCP BigQuery to:
- Measure **overall commercial performance** (revenue, AOV, retention)
- Analyze **real profitability** by product, seller, and region
- Identify **high-value customers** through RFM analysis
- Track **logistics performance** (delivery times, delay rates)
- Produce **actionable and scalable KPIs** for reporting

---

## 📌 Why This Dataset?
This project is built on **real-world data** generously shared by
[Olist](https://olist.com), a leading Brazilian e-commerce platform.
The dataset was chosen for two key reasons:
- It reflects **genuine business complexity** — real orders, real customers,
  real sellers, real logistics chains
- It offers **rich data engineering challenges** : multi-table joins,
  missing values, duplicates, inconsistent types, and text fields
  requiring careful handling
  
---

## 🧱 Architecture

GCS (immutable CSV source) → raw_olist (raw BigQuery tables) → cleaned_olist (cleaning, typing, enrichment) → mart_olist (star schema — analytics & KPIs)

---

## 📦 Deliverables

| Layer | BQ Dataset | Content |
|---|---|---|
| Raw | `raw_olist` | Olist CSV loaded as-is |
| Clean | `cleaned_olist` | Deduplication, typing, enrichment |
| Mart | `mart_olist` | Star schema, KPIs, aggregates |

### Fact Table
- `fact_order_items` — grain = **1 row per order item**

### Dimensions
- `dim_customer`, `dim_product`, `dim_seller`, `dim_date`

### Reporting
- **Tableau Dashboard** — Business KPIs visualization
  (revenue trends, RFM segments, logistics performance, top sellers)

---

## 📊 KPIs
- Total revenue, Average Order Value (AOV)
- Customer retention rate
- Average delivery time / delay rate
- Top sellers, top product categories

---

## ⚙️ Cloud Optimization
- **Partitioning** : date columns (order_purchase_timestamp, review_creation_date)
- **Clustering** : frequent join and filter columns
- **Audit** before every transformation (NULLs, duplicates, consistency)

---

## 🛠️ Tech Stack
- **GCP BigQuery** — Data Warehouse
- **GCS** — Source storage (bucket `gs://olist_wh/olist/`)
- **Standard SQL** (BigQuery dialect)
- **GitHub** — Version control & documentation

---

## 🧠 Strategic Goal
> This project demonstrates the ability to build and maintain a production-grade
> e-commerce data mart in BigQuery — optimized for cost, scalable, and ready
> to deliver business KPIs. **Analytics Engineer positioning.**
