# Bank Marketing Campaign Analysis

A full end-to-end data analytics project on the **UCI Bank Marketing Dataset**, covering data cleaning, exploratory data analysis (EDA), and an interactive Excel dashboard — built as part of the **Future Interns Program**.

---

## Project Overview

This project analyses a Portuguese bank's telemarketing campaign to understand what factors influence whether a client subscribes to a **term deposit**. The dataset contains **45,211 client records** and **17 features** including client demographics, financial details, and campaign interaction data.

---

## Repository Structure

```
bank-marketing-analysis/
│
├── bank_marketing_analysis.ipynb     # Full Python notebook: EDA + Cleaning pipeline
├── bank_full_cleaned.csv             # Cleaned dataset exported from the notebook
├── bank_marketing_dashboard.xlsx     # Excel dashboard with KPIs and charts
├── bank marketing dashboard.png      # Dashboard preview image
└── README.md                         # Project documentation
```

---

## Dataset

| Detail | Info |
|---|---|
| Source | [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Bank+Marketing) |
| File used | `bank-full.csv` |
| Rows | 45,211 |
| Columns | 17 |
| Target variable | `y` — whether the client subscribed to a term deposit (yes/no) |

### Key Features

- **Client info** — age, job, marital status, education, default status, balance
- **Loan info** — housing loan, personal loan
- **Campaign info** — contact type, month, call duration, number of contacts
- **Previous campaign** — days since last contact (pdays), previous outcome

---

## EDA Highlights

Key findings from the exploratory analysis:

- **Class imbalance** — 88.3% of clients did not subscribe vs 11.7% who did
- **Top subscribing jobs** — Students and retired clients had the highest subscription rates
- **Education** — Clients with tertiary education were more likely to subscribe
- **Call duration** — Longer calls were strongly linked to higher subscription rates
- **Best months** — March, September, October, and December showed the highest conversion rates
- **Campaign contacts** — Clients contacted fewer times were more likely to subscribe
- **Balance** — Subscribers tended to have slightly higher average account balances

---

## Data Cleaning Steps

| Step | Action | Reason |
|---|---|---|
| Unknown values | Replaced `unknown` in `job` (0.6%) and `education` (4.1%) with column mode | Low percentage — safe to impute |
| Unknown values | Kept `contact` (28.8%) and `poutcome` (81.7%) as-is | Too many unknowns to impute without introducing bias |
| pdays column | Created `was_previously_contacted` flag, replaced `-1` with `0` | -1 means never contacted — needed numeric handling |
| Target encoding | Added `y_binary` column (yes=1, no=0) | Enables correlation analysis |
| Duplicates | Checked — none found | Dataset was already clean in this regard |

---

## Excel Dashboard

The dashboard covers three focus areas across a 3-sheet workbook:

**Sheet 1 — Dashboard**
- 6 KPI cards: Total Clients, Total Subscribed, Subscription Rate, Avg Balance, Avg Call Duration, Avg Age
- Pie chart: Subscription overview
- Bar chart: Subscription rate by job type
- Column charts: Subscription rate by month, education level, and marital status

**Sheet 2 — Charts Data**
- Clean summary tables feeding all dashboard charts

**Sheet 3 — Raw Data**
- Full 45,211-row cleaned dataset

![Dashboard Preview](bank%20marketing%20dashboard.png)

---

## Tools & Libraries

| Tool | Purpose |
|---|---|
| Python | Data cleaning and EDA |
| Pandas | Data manipulation |
| Matplotlib & Seaborn | Visualisations |
| Jupyter Notebook / Google Colab | Development environment |
| Microsoft Excel | Interactive dashboard |
| GitHub | Version control and portfolio hosting |

---

## How to Run

1. Clone this repository
2. Open `bank_marketing_analysis.ipynb` in Google Colab or Jupyter Notebook
3. Upload `bank-full.csv` to your environment
4. Run all cells in order — the notebook will output `bank_full_cleaned.csv`
5. Open `bank_marketing_dashboard.xlsx` in Microsoft Excel to explore the dashboard

---

## 👩🏽‍💻 Author
Naomi Sirya

**Naomi Sirya**
Future Interns Program
[GitHub: umiSirya](https://github.com/umiSirya)
