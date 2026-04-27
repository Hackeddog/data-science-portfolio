# 🍕 Sarpino's Sales Analytics — Power BI Dashboard

An interactive Power BI report analyzing sales transaction data for **Sarpino's** — a food & beverage brand. The dashboard covers outlet performance, customer segmentation, merchant offer analysis, order trends, and revenue breakdowns across a 4-page report.

---

## 📁 Dataset

**Source Table:** `SarpinosSalesTransactions_BI`

| Field | Description |
|---|---|
| `customerid` | Unique customer identifier |
| `CustomerName` | Customer display name |
| `outletname` | Branch / outlet location |
| `orderdate` | Date of transaction |
| `ordertype` | Type of order (e.g., Dine-in, Delivery, Takeout) |
| `merchantoffercode` | Promo or merchant offer applied |
| `revenue` | Revenue generated per transaction |
| `total_discount` | Discount amount applied |

---

## ❓ Questions & KPIs

The report is designed to answer the following business questions across its 4 pages:

| # | Business Question | KPI |
|---|---|---|
| 1 | Which outlets and offers drive the most revenue? | Sum of Revenue by Outlet & Merchant Offer |
| 2 | Who are the top and bottom customers by revenue? | Sum of Revenue by Customer Name |
| 3 | How do discounts vary by order type? | Sum of Total Discount by Order Type |
| 4 | How does revenue trend over time by outlet? | Revenue by Quarter / Month |
| 5 | What is the total order volume and revenue? | Count of Orders, Sum of Revenue (KPI Cards) |
| 6 | What is the revenue share by order type? | % Distribution by Order Type |

---

## 🔄 Process

1. **Data Ingestion** — Sales transaction data from `SarpinosSalesTransactions_BI` was loaded into Power BI Desktop.
2. **Data Modeling** — A single flat table was used, with date hierarchy auto-generated from `orderdate` (Year → Quarter → Month).
3. **Measure Creation** — Aggregations built directly in visuals: `Sum of Revenue`, `Sum of Discount`, `Count of Orders`.
4. **Report Design** — Four report pages were built, each themed with a branded dark red (`#63230F`) color scheme with custom background images.
5. **Interactivity** — Slicers for `Outlet`, `Merchant Offer Code`, `Quarter`, and `Month` cross-filter all visuals per page.

---

## 📊 Dashboard Pages
<img width="1177" height="658" alt="image" src="https://github.com/user-attachments/assets/c9b46928-418e-46b1-8415-225aaf6a1f70" />
<img width="1171" height="659" alt="image" src="https://github.com/user-attachments/assets/a020a881-65cc-406e-b9a3-72738ad6a2e0" />
<img width="1159" height="646" alt="image" src="https://github.com/user-attachments/assets/1afdf0a4-d82d-4ae3-9cdd-23b94bfa7140" />
<img width="1165" height="649" alt="image" src="https://github.com/user-attachments/assets/1555df19-8c43-417e-a269-2afdded96311" />
## 💡 Key Insights Enabled

- **Outlet benchmarking** — Compare which branches lead or lag in revenue across all time periods.
- **Offer effectiveness** — Identify which merchant offer codes generate the highest revenue to guide marketing decisions.
- **Customer segmentation** — Top 20 vs. Bottom 10 customer views support loyalty or re-engagement campaigns.
- **Discount impact** — Pie chart breakdown of discounts by order type reveals where discounts are applied most.
- **Time-based trends** — Quarter and Month slicers on Pages 3 and 4 allow seasonal and monthly performance tracking.

---

## 🛠 Tools Used

- **Microsoft Power BI Desktop** — Report authoring and visualization
- **Power BI Theme:** CY24SU10 (custom branded dark red `#63230F` color scheme)
- **Data Source:** Flat transaction table (`SarpinosSalesTransactions_BI`)

---



