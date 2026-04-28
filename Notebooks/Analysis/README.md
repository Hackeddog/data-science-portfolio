<img width="1557" height="701" alt="image" src="https://github.com/user-attachments/assets/aeb679cc-bbb6-4949-a7c3-58da1b26c47c" /># 🛒 Retail Transactions Data Analysis

An exploratory data analysis (EDA) project on a retail transactions dataset with 1,000,000 records. The analysis uncovers transaction patterns by time, city, and customer behavior using Python in Google Colab.

---

## 📁 Dataset

**File:** `Retail_Transactions_Dataset.csv`
**Rows:** 1,000,000 transactions

| Column | Description |
|---|---|
| `Transaction_ID` | Unique transaction identifier |
| `Date` | Date and time of transaction |
| `Customer_Name` | Name of the customer |
| `Product` | List of products purchased (stored as string list) |
| `Total_Items` | Number of items in the transaction |
| `Total_Cost` | Total cost of the transaction |
| `Payment_Method` | Payment method used (Cash, Credit Card, Mobile Payment, etc.) |
| `City` | City where the transaction occurred |
| `Store_Type` | Type of store (Warehouse Club, Specialty Store, Department Store, Pharmacy, etc.) |
| `Discount_Applied` | Whether a discount was applied (TRUE/FALSE) |
| `Customer_Category` | Customer segment (Homemaker, Professional, etc.) |
| `Season` | Season of the transaction (Winter, Spring, Summer, Fall) |
| `Promotion` | Promotion applied (e.g., BOGO, No Promotion) |

**Date Range:** January 2020 – March 2024

---

## ❓ Questions & KPIs

| # | Business Question | KPI |
|---|---|---|
| 1 | What is the average number of transactions per day? | Avg. Daily Transaction Count |
| 2 | Which cities have the most transactions? | Transaction Count by City |
| 3 | What is the average number of items sold per transaction? | Avg. Items per Transaction |
| 4 | What are the peak hours for transactions? | Transaction Count by Hour of Day |
| 5 | Which days of the week are busiest? | Transaction Count by Day of Week |
| 6 | What are the most frequently purchased products? | Product Frequency Count |

---

## 🔄 Process

1. **Data Loading** — Loaded raw CSV from Google Drive into a Pandas DataFrame.
2. **Exploratory Analysis** — Inspected shape, data types, unique values, and missing value counts using `.info()`, `.isnull().sum()`, and `.unique()`.
3. **Data Cleaning**
   - Filled missing values in `Promotion` column with `'No Promotion'`.
   - Parsed the `Product` column from string representation into actual Python lists using `ast.literal_eval`.
   - Converted `Date` column to `datetime` format.
4. **Feature Engineering** — Extracted `Hour` and `Day_of_Week` from the `Date` column for time-based analysis.
5. **Aggregation & Analysis**
   - Computed daily transaction counts and average transactions per day.
   - Counted transactions grouped by `City`, `Hour`, and `Day_of_Week`.
   - Exploded the product list to get individual product frequency counts.
6. **Visualization** — Built bar charts using `seaborn` and `matplotlib` for hourly and daily transaction distributions.

---
<img width="820" height="481" alt="image" src="https://github.com/user-attachments/assets/09e6b90e-c8a9-4334-96bd-ef1e24933c17" />
<img width="1463" height="716" alt="image" src="https://github.com/user-attachments/assets/68aa76a4-58a2-49d4-83b0-b32943f150d2" />
<img width="1557" height="701" alt="image" src="https://github.com/user-attachments/assets/95b7409d-a5a7-410f-9a92-a45c3ecd3bff" />

## 💡 Key Insights

- **Product parsing** — The `Product` column stores lists as strings, requiring `ast.literal_eval` to properly count individual product frequencies across all transactions.
- **Missing data** — Only the `Promotion` column contained null values, which were replaced with `'No Promotion'` to retain all rows for analysis.
- **Time patterns** — Extracting `Hour` and `Day_of_Week` from the timestamp unlocks behavioral insights around when customers shop most.
- **City-level analysis** — Grouping by `City` reveals geographic concentration of transactions, supporting store-level resource planning.
- **Scale** — With 1 million rows, the dataset is large enough to surface statistically meaningful patterns across all dimensions.

---

## ✅ Conclusion

This EDA establishes a solid foundation for understanding retail transaction behavior at scale. The analysis reveals clear time-based patterns (peak hours and days) and geographic transaction distribution. Future work could include customer segmentation analysis, promotion effectiveness modeling, basket analysis on product co-purchases, and predictive modeling of transaction volume by season or city.

---

## 🛠 Tools & Libraries

| Tool | Purpose |
|---|---|
| Python 3 | Core programming language |
| Pandas | Data manipulation and aggregation |
| NumPy | Numerical operations |
| Matplotlib | Base plotting |
| Seaborn | Statistical visualizations |
| ast | Parsing product lists from string format |
| Google Colab | Cloud notebook environment |
| Google Drive | Dataset storage and access |

---


