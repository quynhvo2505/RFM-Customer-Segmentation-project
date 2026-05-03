# RFM Customer Segmentation

> Segmenting an e-commerce customer base by Recency, Frequency, and Monetary value to direct marketing spend toward the customers most likely to respond.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?logo=powerbi&logoColor=black&style=flat-square) ![Excel](https://img.shields.io/badge/Excel-217346?logo=microsoftexcel&logoColor=white&style=flat-square) ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white&style=flat-square)

---

## The business question

A growing online retailer wanted to spend its email-marketing budget more selectively. Leadership suspected most revenue came from a small share of customers, but the team had no segmentation in place — every customer was getting the same campaign. The question: **which customers should we double down on, which should we try to win back, and which aren't worth the cost of contacting?**

---

## Key findings

_Numbers below are placeholders — replace with the actual figures from the Power BI dashboard._

1. **The top [TBD]% of customers (Champions) drove ~[TBD]% of total revenue.** A small, identifiable cohort is doing the heavy lifting; the marketing budget should reflect that.
2. **About [TBD]% of customers fall into "At Risk" or "Hibernating"** — high past value, no recent activity. This is the highest-leverage group for a win-back campaign.
3. **Roughly [TBD]% are "Lost"** — single low-value purchase, no return. Continuing to email them costs more in deliverability damage than it's worth.

---

## What I recommended

- **Tier the email program into 4 streams**: Champions (loyalty + early access), Loyal (cross-sell), At Risk (win-back with incentive), Hibernating/Lost (suppress or send 1 final reactivation).
- **Reallocate [TBD]% of campaign budget toward the top two tiers**, where response is most likely.
- **Re-score monthly** — RFM segments shift; a customer flagged Champion in March may slip to Loyal by June.

---

## Approach

1. Joined the source tables in Power BI: `EcomSales` (transactions) with `Customer`, `Product`, and `Region` for context.
2. Cleaned and prepared the data — removed cancellations, dropped rows with missing customer IDs, computed line-level revenue.
3. Computed RFM scores in Excel ([`RFM_Ranking.xlsx`](RFM_Ranking.xlsx)) — quintile-ranked each customer on Recency (days since last purchase), Frequency (number of orders), and Monetary (total spend).
4. Mapped scores to named segments — Champions, Loyal, Potential Loyalist, At Risk, Hibernating, Lost.
5. Built the dashboard ([`RFM analysis project.pbix`](RFM%20analysis%20project.pbix)) showing segment sizes, revenue share, and the recommended action per segment.

**Notebook:** [`RFM_Customer_Segementation.ipynb`](RFM_Customer_Segementation.ipynb) — exploratory analysis and feature engineering in Python.

**Dashboard:** [`RFM analysis project.pbix`](RFM%20analysis%20project.pbix) — open in Power BI Desktop.

---

## Dataset

| File | Description |
| --- | --- |
| [`Customer.csv`](Customer.csv) | Customer master — IDs, demographics, region |
| [`EcomSales.csv`](EcomSales.csv) | Transaction-level e-commerce orders |
| [`Product.csv`](Product.csv) | Product catalog — IDs, categories, prices |
| [`Region.csv`](Region.csv) | Region lookup |

---

## Tools used

- **Power BI Desktop** — dashboard and segment visualization
- **Excel** — RFM score calculation and ranking
- **Python (pandas)** — exploratory analysis in Jupyter

---

## Repository structure

- `README.md` — you are here
- `Customer.csv` — customer master data
- `EcomSales.csv` — transaction data
- `Product.csv` — product catalog
- `Region.csv` — region lookup
- `RFM_Customer_Segementation.ipynb` — Jupyter exploratory analysis
- `RFM_Ranking.xlsx` — Excel RFM score calculation
- `RFM analysis project.pbix` — Power BI dashboard

---

## How to view the dashboard

1. Download [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).
2. Clone or download this repo.
3. Open `RFM analysis project.pbix` in Power BI Desktop.

---

## Author

**Quynh Vo** — Business Analyst, Boston, MA

[LinkedIn](https://www.linkedin.com/in/qvo2505/) | [GitHub](https://github.com/quynhvo2505)
