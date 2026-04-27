# Dealer Car Analysis — Southeast Asia

A data analysis project examining car sales performance across dealerships in the Philippines, Malaysia, and Singapore. The analysis covers sales volume, revenue, profit margins, and brand performance using structured Excel data and pivot-based dashboards.

---

## Dataset

The workbook (`Dealer_Car_Analysis.xlsx`) contains three core data tables:

| Sheet | Description |
|---|---|
| `Dealers` | 10 dealerships across 3 countries (Philippines, Malaysia, Singapore) |
| `Models` | 15 car models from 8 brands, with price and profit per unit |
| `Sales` | 218 sales transactions with quantity, revenue, and profit |

**Key fields:** `DealerID`, `ModelID`, `Date`, `Quantity`, `TotalPrice`, `Total Profit`, `Country`, `City`, `Brand`, `Segment`, `Fuel`, `Price (USD)`

**Coverage:** 10 dealers · 15 models · 8 brands · 3 countries · 218 transactions

---

## ❓ Questions & KPIs

The analysis was designed to answer the following business questions:

1. **Which country generates the most revenue?**
   - KPI: Total Profit by Country

2. **What are the top 3 best-selling car models and brands?**
   - KPI: Sum of Quantity Sold by Model and by Brand

3. **How does profit compare to sales volume across brands?**
   - KPI: Total Profit vs. Quantity Sold per Brand

4. **Which cities and dealerships lead in revenue and sales?**
   - KPI: Total Revenue and Profit by City and Dealer

---

## 🔄 Process

1. **Data Collection** — Sales records were compiled across 10 dealers spanning 3 Southeast Asian countries.
2. **Data Structuring** — Three relational tables were created: `Dealers`, `Models`, and `Sales`, linked by `DealerID` and `ModelID`.
3. **Data Enrichment** — The `Sales` sheet was enriched with lookup columns for `Country`, `City`, `Dealer`, `Brand`, and `Cars` for easier pivot analysis.
4. **Pivot Analysis** — Four pivot tables were built to answer each business question independently (Sheets: `Number1` through `Number4`).
5. **Visualization** — Charts were created from pivot tables to support the dashboard and insights.

---

#Dashboards
**Which country generates the most revenue?**
<img width="752" height="435" alt="image" src="https://github.com/user-attachments/assets/44458ba0-12a3-491f-a218-b7099ed9cc1b" />

**What are the top 3 best-selling car models and brands?**
<img width="555" height="274" alt="image" src="https://github.com/user-attachments/assets/6ad793c0-f99b-4a34-ac93-7d574f99cb98" />
<img width="603" height="290" alt="image" src="https://github.com/user-attachments/assets/c51f9d49-50ef-4163-a58c-ca86b3e868c8" />

**How does profit compare to sales volume across brands?**
<img width="752" height="433" alt="image" src="https://github.com/user-attachments/assets/15dd05a5-eaee-4a0d-b21b-fca29637243c" />

**Which cities and dealerships lead in revenue and sales?**
<img width="1505" height="777" alt="image" src="https://github.com/user-attachments/assets/ada0cffc-01f1-43e7-b4cf-2db2373d9fa2" />


## 💡 Project Insights

- **Philippines dominates** total profit with $717,300 — over 75% of combined revenue — largely because it has the most dealers (7 out of 10) spread across major cities.
- **Mitsubishi leads in units sold** (63 units) but ranks 3rd in profit, while **Hyundai** achieves the highest total profit ($169,800) at only 52 units — indicating a strong profit-per-unit advantage for Hyundai.
- **Honda and Proton** present a similar pattern: both generate disproportionately high profit relative to volume, suggesting premium or high-margin model mixes.
- **Iloilo Motors** is the single highest-performing dealership, generating $166,900 in profit and $1,323,000 in total revenue — outperforming even city-level competitors by a significant margin.
- **Nissan vs. Proton** is a notable comparison: Nissan sold more units (49 vs. 30) but earned less profit ($98,600 vs. $119,600), highlighting how model mix matters more than volume.
- **Singapore**, despite having only one dealer, achieves a competitive profit-per-dealer ratio, suggesting high-value transactions in a premium market.

---

## ✅ Conclusion
This analysis reveals that **profit efficiency** — not just volume — is the key differentiator among brands and dealerships. The Philippines market drives the bulk of revenue due to dealer count, but individual dealerships like Iloilo Motors demonstrate that strong local performance can rival multi-city competitors. Brands like Hyundai and Honda consistently extract higher profit per unit sold, making them strategically valuable despite lower volumes than Mitsubishi. Future analyses could explore seasonal trends, fuel-type preferences, and model-segment profitability to further guide inventory and sales strategy.

---

## 🛠 Tools Used

- Microsoft Excel (Pivot Tables, Charts)
- Data structured across relational sheets for cross-referencing

---


