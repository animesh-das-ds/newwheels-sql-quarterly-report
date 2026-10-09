# New Wheels — Quarterly Business Report (SQL Analytics)

![Course](https://img.shields.io/badge/Course-Introduction%20to%20SQL-336791)
![Grade](https://img.shields.io/badge/Grade-A%20(4.0)-success)
![Type](https://img.shields.io/badge/Type-SQL%20%C2%B7%20Business%20Intelligence-blue)
![Tool](https://img.shields.io/badge/Tool-SQL%20%C2%B7%20Window%20Functions-orange)

A SQL-driven business intelligence project: query a relational database of a pre-owned vehicle resale company and produce a **quarterly report for the CEO** explaining why sales are falling.

---

## Business Problem

New-Wheels is a vehicle resale app offering end-to-end service from listing to shipping, and it captures after-sales feedback. Sales have been **dropping steadily for a year** and online ratings are poor, so new customers are falling away each quarter. The CEO wants a quarterly report with all key metrics to assess the health of the business.

## Objective

Import the database dump, answer **ten leadership questions using SQL**, and turn the results into a quarterly business report with recommendations.

## Data

| Attribute | Detail |
|---|---|
| Tables | Customer, order, product |
| Orders | 1,000 |
| Unique customers | 994 |
| States/regions | 49 |
| Feedback | Ratings across four quarters |

## The Ten SQL Questions

Each was answered with a purpose-built query using joins, aggregations, `CASE` statements, window functions and date arithmetic:

1. Total customers who placed orders, and their distribution across states.
2. Top 5 vehicle makers preferred by customers.
3. Most preferred vehicle maker in each state — `RANK() OVER (PARTITION BY state)`.
4. Overall average rating and average rating per quarter ("Very Bad"→1 … "Very Good"→5).
5. Percentage distribution of feedback by quarter — are customers getting more dissatisfied?
6. Trend of order volume by quarter.
7. Net revenue and quarter-over-quarter % change — `LAG()`.
8. Trend of net revenue and orders together by quarter.
9. Average discount offered by credit card type.
10. Average shipping time per quarter — `julianday` date arithmetic.

## Key Findings

**Thin, concentrated customer base**
- Only **994 customers** have ever ordered. Texas (97) and California (97) lead, then Florida (86) and New York (69), with a long tail of states below 30 customers. This is concentration risk, not nationwide reach.

**Brand preference is concentrated and regional**
- Chevrolet (83), Ford (63), Toyota (52), then Pontiac and Dodge clustered around 50–52.
- Different states have different top makers, and many states show ties with single-digit customer counts — immature, low-volume markets.

**Customer satisfaction is mediocre and falling**
- Overall average rating **3.135** (just above "Okay").
- It falls every quarter: **3.55 (Q1) → 2.40 (Q4)**, crossing into negative territory by Q3.
- Negative feedback ("Bad" + "Very Bad") rises every quarter, peaking near **60% in Q4**, while positive feedback collapses from ~59% (Q1) to ~20% (Q4).

**Orders and revenue erode every quarter**
- Orders fall **~36%** over the year — 310 (Q1) to 199 (Q4) — with the steepest drop after Q2, exactly when sentiment worsened.
- The steepest quarter-over-quarter revenue drop is in Q4 (**−20.13%**).

**Shipping time is the smoking gun**
- Average shipping time balloons from **57.17 days (Q1) to 174.10 days (Q4)** — nearly three times longer.

**Discounts are not being used as a lever**
- Discounts are uniform across credit card types (0.61%–0.64%).

## Recommendations

1. **Fix shipping before touching pricing or marketing.** Delivery time is the single strongest driver of falling ratings and repeat orders. Audit logistics partners, capacity planning and shipper SLAs immediately.
2. **Concentrate resources on high-demand states** (Texas, California, Florida, New York) — priority inventory, faster shipping lanes, stricter service quality.
3. **Shift spend from discounts to experience recovery** — after-sales support, faster dispute resolution, proactive communication. Restoring trust has a far higher return than marginal price cuts.

## Skills Demonstrated

SQL joins · `GROUP BY` aggregations · `CASE`-based recoding · window functions (`RANK`, `LAG`) · date arithmetic · percentage-distribution queries · converting query output into an executive narrative.

## Headline Metrics

| Metric | Value |
|---|---|
| Total revenue | ~₹115–120M |
| Orders | 1,000 |
| Unique customers | 994 |
| Average rating | 3.14 (falling) |
| Average days to ship | ~115 (57 → 174 across quarters) |

## Repository Structure

```
├── reports/
│   └── New_Wheels_Quarterly_Business_Report.pdf
├── screenshots/
│   └── report_page_01.png … report_page_06.png
└── README.md
```

---

*PGP in Data Science & Business Analytics · Great Lakes Executive Learning / The University of Texas at Austin, McCombs School of Business. Content drawn from the project report and course transcript.*
