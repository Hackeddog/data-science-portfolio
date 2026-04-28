# 📊 Sales & Profit Performance Dashboard — Power BI

An interactive single-page Power BI report analyzing sales revenue across salespeople, regions, channels, and product types. Built as part of a workshop project, the dashboard provides a comprehensive view of business performance through KPI cards, trend charts, and distribution visuals — all filterable via six dynamic slicers.

---

## 📁 Dataset

**Source Tables:** `Data` · `Sales and Profit`

| Field | Description |
|---|---|
| `Order ID` | Unique order identifier |
| `Sales Person` | Name of the salesperson who handled the transaction |
| `Region` | Geographic region of the sale |
| `Products Type` | Category/type of product sold |
| `Sales Channel` | Channel through which the sale was made (e.g., Online, Retail) |
| `Sales` | Revenue value per transaction |
| `Count Sales` | Number of sales / order count |
| `Month Name` | Month of the transaction |
| `Date` | Full date of the transaction (with Year/Month hierarchy) |

---

## ❓ Questions & KPIs

| # | Business Question | KPI |
|---|---|---|
| 1 | What is the total sales revenue? | Sum of Sales (Revenue Card) |
| 2 | How many total orders were placed? | Count of Sales (Quantity Card) |
| 3 | How does revenue trend across months? | Sales Revenue by Month Name (Area Chart) |
| 4 | Which salesperson generates the most revenue? | Sales Revenue by Sales Person (Bar Chart + Pivot Table) |
| 5 | Which region contributes the most to revenue? | Sales Revenue by Region (Clustered Bar Chart) |
| 6 | How is revenue distributed across sales channels? | Sales Revenue by Channel (Donut Chart) |
| 7 | Which product type drives the most revenue? | Sales Revenue by Product Type (Funnel Chart) |
| 8 | How does each order contribute to overall revenue? | Sales Revenue by Order ID (Bar Chart) |

---

## 🔄 Process

1. **Data Loading** — Two tables (`Data` and `Sales and Profit`) were loaded into Power BI Desktop and connected via the date field.
2. **Data Modeling** — A date hierarchy (Year → Month) was applied to the `Date` column to enable time-based filtering.
3. **Measure Creation** — Key measures used: `Sum of Sales` for revenue and `Count Sales` for order volume.
4. **Report Design** — A single-page dashboard was built using the CY24SU10 Power BI theme with a branded layout and background.
5. **Slicer Configuration** — Six slicers were added for dynamic cross-filtering: Year, Month, Sales Person, Region, Products Type, and Sales Channel.
6. **Visualization** — Eight visuals were arranged to cover KPI summary cards, trend analysis, and categorical breakdowns.

---

## 📊 Dashboard — Page 1 (Sales Overview)
<img width="1164" height="651" alt="image" src="https://github.com/user-attachments/assets/55a7fa64-cad6-4223-9fe6-bca57f375ac5" />

## 💡 Key Insights Enabled

- **Salesperson benchmarking** — The bar chart and pivot table together allow comparison of both volume and revenue per salesperson, revealing who sells more vs. who sells higher value.
- **Monthly trend tracking** — The area chart highlights seasonal peaks and dips in revenue across the year.
- **Channel strategy** — The donut chart shows which sales channels (e.g., online vs. in-store) contribute most, informing channel investment decisions.
- **Product prioritization** — The funnel chart shows how revenue tapers across product types, helping identify high-performing vs. underperforming categories.
- **Regional performance** — The clustered bar chart allows quick identification of top-performing regions for sales focus or expansion planning.

---

## ✅ Conclusion

This dashboard delivers a complete single-page sales performance overview, combining summary KPIs with granular breakdowns by person, region, channel, and product. The six interactive slicers make it easy to drill into any combination of filters — by time period, salesperson, or business segment. Future enhancements could include a dedicated profit margin page, month-over-month growth metrics, and target vs. actual comparisons per salesperson.

---
