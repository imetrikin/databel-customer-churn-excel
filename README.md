# Customer Churn Analysis — Databel (Excel)

Analyzing 6,687 telecom customers to find out **who is leaving, why, and what it costs** — built as a single-screen Excel dashboard.

**Headline:** a 27% churn rate, with **$1,367,515 in customer revenue** sitting on the churned side of the ledger.

## Background

Databel is a telecom provider losing customers faster than it would like, without a clear picture of the cause. The dataset covers every customer on the books across four areas:

| Area | Fields |
|---|---|
| Customer status | Churn label, churn category, churn reason |
| Demographics | Age, gender, under-30 and senior flags |
| Contract | Contract type, payment method, state, group membership |
| Subscription & usage | Account length, local/international calls and minutes, international plan, avg monthly GB download, unlimited data plan, extra charges, customer service calls, monthly and total charges |

## Questions

1. What is the average churn rate?
2. What are the main reasons customers leave?
3. Does churn differ between customers using under vs. over 3GB of data per month — and does an unlimited subscription change that?
4. What is churn actually costing the business?

## The dashboard




A single screen combining KPI cards, five PivotTables, eight charts and a filled US map:

| Panel | What it shows |
|---|---|
| KPI cards | 6,687 total customers · 1,796 churned · 4,891 retained |
| Churn rate | 27% churned vs. 73% retained |
| Churn by data usage & plan | Churn split across ≤3GB vs. >3GB monthly users, filterable by unlimited data plan |
| Revenue lost to churn | $1,367,515 (churned) vs. $5,879,559 (retained) |
| Churn reasons | Competitor offers 805 · Pricing & product 403 · Customer service 388 · Other 173 |
| Churn % by state | Filled map showing geographic concentration |
| Correlation matrix | Churn label against account length, extra data charges and gender |

## Key findings

**1. Churn rate is 27%** — 1,796 of 6,687 customers, representing $1.37M of the $7.25M total customer revenue.

**2. Competitors are the single biggest driver.** Of the 1,769 customers with a categorized reason, 805 (46%) left for a competitor offer — more than pricing/product (403) and customer service (388) combined.

**3. Heavy data users churn most.** Customers downloading more than 3GB/month account for roughly 71% of churn.

**4. The unlimited plan matters most for light users.** Among customers using ≤3GB/month, the absence of an unlimited data plan raised the churn rate from 30% to 50% — a counterintuitive result, since these are exactly the customers who appear not to need unlimited data.

**5. Tenure reduces churn, moderately.** Account length and churn show a Pearson correlation of **−0.352**: the longer a customer stays, the less likely they are to leave, though the relationship isn't strong enough to rely on alone.

**6. Demographics don't explain churn.** Gender correlates at −0.007 and extra data charges at 0.005 — effectively zero. Worth reporting, because it rules out two intuitive explanations.

## Recommendations

- Build offers that compete directly on the terms customers are leaving for — this is the largest single lever.
- Proactively offer the unlimited plan to customers using ≤3GB/month, where it cuts churn by 20 percentage points.
- Concentrate retention effort on newer accounts, where churn risk is highest.
- Invest in customer support training — 388 departures traced directly to service.
- Review pricing and product gaps flagged by the 403 pricing/product-related departures.

## Techniques demonstrated

- **PivotTables** — five built from one source table, using `Count of Customer ID` and `Sum of Total Charges`
- **Custom grouping** — binned the continuous `Avg Monthly GB Download` field into ≤3GB / >3GB buckets, and collapsed a long list of individual churn reasons into four analysable categories, both inside the PivotCache rather than by editing source data
- **Correlation analysis** — binary-encoded categorical variables (churn, gender) to build a Pearson correlation matrix in Excel
- **Filled map chart** — churn percentage by US state
- **Dashboard design** — KPI cards, pie/bar chart pairings, slicer-driven filtering, and a notes panel, laid out to be read in one screen
- Executive summary translating the analysis into business recommendations

## Tools

Microsoft Excel — PivotTables, PivotCharts, custom grouping, filled maps, correlation analysis

## Files

| File | Description |
|---|---|
| `Databel_-_dashboard.xlsx` | Full workbook: dashboard, source data, and all supporting pivot sheets |
| `dashboard.png` | Dashboard screenshot |

## Notes

Completed as DataCamp's *Analyzing Customer Churn in Excel* case study. The dataset and business scenario are provided by DataCamp; all analysis, dashboard design and conclusions in this repository are my own work.

---

**Ilan Metrikin** — Data Analyst
📧 imetrikin@gmail.com · [LinkedIn](https://www.linkedin.com/in/ilan-metrikin-36a652218/)
