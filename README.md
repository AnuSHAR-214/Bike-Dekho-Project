# Bike Dekho — Customer Purchase Analysis

An end-to-end Excel analytics project examining **1,000 customer records** to answer one question: *what separates the people who buy a bike from the people who don't?*

**[View the live dashboard →](https://anushar-214.github.io/Bike-Dekho-Project/)**

The interactive web version lets you filter the customer base by gender, region, age, education, occupation and home ownership, with every chart recalculating against the 48.1% baseline purchase rate.

---

## The headline result

Of 1,000 customers, **481 purchased a bike (48.1%)**. Demographics you would expect to matter mostly don't — gender moves the rate by 1.5 points, home ownership by 1.6. What actually predicts a purchase is **how far someone commutes and how many cars they already own**.

| Strongest signals | Purchase rate |
|---|---|
| Owns no car | **61.1%** |
| Commutes 10+ miles | **29.7%** |
| Owns 2+ cars | **36.9%** |
| Pacific region | **58.9%** |
| Has 5 children | **22.2%** |

---

## Key findings

**Car ownership is the sharpest predictor.** Customers with no car convert at 61.1% and those with one car at 56.9%, but the rate collapses to 36.3% at two cars and stays near 36–39% beyond that. A bike competes with the second car, not the first.

**Long commutes kill the sale.** Purchase rates fall from 54.6% at 0–1 miles to 29.7% at 10+ miles. The 2–5 mile band is the single best segment at 58.6% — far enough to need transport, close enough to cycle.

**Region matters more than gender.** The Pacific region converts at 58.9% against North America's 43.3%, a 15.6-point spread. Gender, by contrast, splits 48.9% female to 47.4% male — effectively no difference.

**Life stage beats income.** Single customers buy at 54.1% versus 42.9% for married ones, and middle-aged customers at 54.6% versus 31.2% for older ones. Average income among buyers is ₹57,963 against ₹54,875 for non-buyers — a real but small gap next to those swings.

**Education tracks upward, with one cliff.** Bachelors (55.2%) and Graduate Degree (54.0%) holders lead, while Partial High School sits at 26.3% — the weakest segment in the entire dataset.

---

## Data cleaning

The raw export contained **1,026 rows with only 1,000 unique customer IDs**. Cleaning steps applied:

- Removed **26 duplicate records** identified by customer ID
- Standardised inconsistent category labels (`M`/`F` → `Male`/`Female`, `Yes`/`No` normalised across columns)
- Corrected spelling variants in Commute Distance and Education
- Converted Income and Age to proper numeric types
- Derived an **Age Bracket** column — Adolescent (under 30), Middle Age (30–54), Old (55+)
- Verified no blanks remained across all 14 fields

Final working dataset: **1,000 rows × 14 columns**, zero duplicates, zero nulls.

## Analysis performed

- **PivotTables** cross-tabulating Purchased Bike against Gender, Region, Marital Status, Income group, Cars owned and Commute Distance
- **Pivot Charts** — clustered columns and bar charts for each relationship
- **Functions used** — `IF` for age bracketing, `SUMIFS` and `COUNTIFS` for conditional aggregates, `VLOOKUP` for label mapping, `TRIM` and `PROPER` for text cleanup
- **Interactive dashboard** with KPI cards and slicers for filtering across every dimension

---

## Dataset

| Field | Values |
|---|---|
| ID | 1,000 unique customers |
| Gender | Female (489), Male (511) |
| Marital Status | Married (538), Single (462) |
| Income | ₹10,000 – ₹170,000 |
| Children | 0 – 5 |
| Education | Partial High School → Graduate Degree (5 levels) |
| Occupation | Manual, Clerical, Skilled Manual, Management, Professional |
| Home Owner | Yes (683), No (317) |
| Cars | 0 – 4 |
| Commute Distance | 0-1, 1-2, 2-5, 5-10, 10+ Miles |
| Region | Europe (300), North America (508), Pacific (192) |
| Age | 25 – 89 (mean 44.2) |
| Age Bracket | Adolescent (110), Middle Age (701), Old (189) |
| Purchased Bike | Yes (481), No (519) |

## Repository contents

| File | Purpose |
|---|---|
| `index.html` | Interactive web dashboard — the live site |
| `Raw Data changeddd.xlsx` | Original export, 1,026 rows before cleaning |
| `data cleaning.xlsx.xlsx` | Cleaning process with the working sheet |
| `dashboard.xlxs.xlsx` | PivotTables, Pivot Charts and dashboard build |
| `Completed Final project 1.xlxs.xlsx` | Final workbook with the full dashboard and slicers |

## How to view

**The dashboard** — open the [live link](https://anushar-214.github.io/Bike-Dekho-Project/); it runs entirely in the browser with no setup.

**The Excel work** — download `Completed Final project 1.xlxs.xlsx` and open the **Dashboard** sheet. Slicers require Excel 2013 or later; they will not render in Google Sheets or in GitHub's file preview.

## Tools

Microsoft Excel — PivotTables, Pivot Charts, slicers, conditional formatting, lookup and logical functions. The web dashboard is plain HTML, CSS and JavaScript with no dependencies.

---

## What I'd do next

Cars owned, commute distance and marital status are strong enough individually that a **logistic regression** would likely predict purchase intent well above the 48% base rate. Segmenting on the intersection of those three — single, car-free, short-commute customers — would be the obvious first target list for a marketing campaign.

---

*Built by [AnuSHAR-214](https://github.com/AnuSHAR-214)*
