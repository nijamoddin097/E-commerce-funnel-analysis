
# E-Commerce Funnel Analysis & Product Profitability

An end-to-end e-commerce analytics project on website acquisition, customer purchase behavior, funnel drop-offs, refunds and product profitability, built with **Python, Google Colab and Power BI**.

---

## Project Overview

The project follows visitors of an online toy retailer (4 products, March 2012 to March 2015) from first session to purchase. It shows where potential customers leave the funnel, which channels and products drive growth, and how refunds affect profit.

Data was cleaned and explored in Python, then presented in an interactive three-page Power BI dashboard.

### Headline Numbers

| Metric | Value |
|:--|:--|
| Revenue (before refunds) | $1.94M |
| Orders | 32.31K |
| Website sessions | 472.87K |
| Overall conversion rate | 6.83% |
| Average order value | $59.99 |
| Refunds | $85,338.69 (4.40% of revenue) |

---

## The 10 Business Questions

### 1. Which acquisition channels convert best?

- Unattributed 7.34%, bsearch 7.19%, gsearch 6.75%.
- Socialbook converts at only **3.21%**, less than half of every other channel.
- gsearch brings about two-thirds of all traffic and orders.

### 2. Where does the funnel lose the most sessions?

- The biggest drop is **Product Detail to Cart**.
- 54.8% of sessions stop here (210,214 sessions fall to 94,953).

### 3. Which products progress best from product page to cart?

- Hudson River Mini Bear 65.1%
- Forever Love Bear 55.6%
- Birthday Sugar Panda 46.3%
- The Original Mr. Fuzzy 43.0%, even though it receives about 77% of product-page sessions.

### 4. Do new and returning visitors behave differently?

- Returning visitors convert better: 7.83% vs 6.64%.
- Returning visitors earn more per session: $4.74 vs $3.97.
- New visitors still produce about 81% of revenue because they make up 83% of sessions.

### 5. Which products generate the most revenue and profit?

- The Original Mr. Fuzzy: $1.21M revenue, $677K net profit.
- Forever Love Bear: $0.35M revenue, $210K net profit.
- Birthday Sugar Panda: $0.23M revenue, $143K net profit.
- Hudson River Mini Bear: $0.15M revenue, $101K net profit.

### 6. Which products have the best margins?

- Net margin after refunds: Hudson River 67.9%, Birthday Sugar Panda 66.5%, Forever Love 61.7%, Mr. Fuzzy 58.9%.
- The top-selling product has the lowest margin.

### 7. Which products are refunded most, and is the difference real?

- Refund rates: Birthday Sugar Panda 6.04%, Mr. Fuzzy 5.11%, Forever Love 2.23%, Hudson River 1.28%.
- A chi-square test shows the difference is statistically significant.
- Cramér's V is 0.078, so the effect is small.

### 8. How does basket size affect order value?

- One-item orders (76.1% of orders) average $50.82.
- Two-item orders (23.9% of orders) average $89.25.

### 9. How did the business grow over time?

- Monthly sessions grew about 15.8x, from 1,879 (Mar 2012) to 29,722 (Dec 2014).
- Conversion improved from 3.19% to 8.70% (Feb 2015).
- Revenue grew roughly 150% to 240% year over year in every month of 2014.

### 10. Is there seasonality?

- Revenue and orders are lowest from April to August and peak in November and December (monthly totals across years).
- March 2015 is a partial month and is excluded from trend conclusions.

---

## Data and Cleaning

Six tables were used in Python:

- website_sessions (472,871 rows)
- website_pageviews (1,188,124 rows)
- orders (32,313 rows)
- order_items (40,025 rows)
- order_item_refunds (1,731 rows)
- products (4 rows)

A date table was added in Power BI.

**Cleaning steps**

- Converted all `created_at` fields from text to datetime.
- Checked duplicates and missing values: no duplicate rows or session IDs.
- Labelled 83,328 sessions (17.62%) with no UTM data as **Unattributed**. Of these, 43,411 carry a gsearch or bsearch referrer (likely untagged search traffic) and 39,917 have no referrer (likely direct visits).
- Reviewed outliers in price, COGS, items purchased and refund amount with box plots. No records needed removal.
- Exported six validated clean files that feed the Power BI model.

**Power BI data model decisions**

- Removed the refunds to orders relationship.
- Kept orders to order_items as the active relationship.
- Linked a single date table to the cleaned sessions table.
- Kept the original `created_at` columns and hid them.

---

## Power BI Dashboard

The dashboard has three pages with shared Year, Month and utm_source slicers.

### 1. Executive Overview

KPI cards, monthly revenue trend, monthly orders and net profit by product.

![Executive Overview](images/Executive%20overview.png)

### 2. Acquisition & Funnel Analysis

Conversion by channel, seven-stage funnel, product detail to cart by product, and new vs returning visitors.

![Acquisition and Funnel Analysis](images/Acquisition%20%26%20Funnel%20page.png)

### 3. Product Performance & Profitability

Revenue, profit margin, orders, and revenue vs net profit by product.

![Product Performance and Profitability](images/Product%20Performance%20page%20.png)

> Dashboard margins are calculated on gross revenue, so they are slightly lower than the net margins above. Net profit values are identical.

---

## Business Problems Identified & Recommendations

### Funnel and conversion

**1. Customers drop off before adding to cart**
- Evidence: only 45.2% of product-detail sessions reach the cart (the largest drop in the funnel).
- Action: review product-page content, images and add-to-cart placement, then A/B test changes.

**2. Cart conversion differs by product**
- Evidence: Hudson River Mini Bear 65.13% vs The Original Mr. Fuzzy 43.04%.
- Action: fix the Mr. Fuzzy page first and send more traffic to Hudson River.

**3. One acquisition channel converts poorly**
- Evidence: socialbook converts at 3.21% vs 6.75% to 7.34% for the others.
- Action: review spend, targeting and landing page before scaling.

**4. New visitors convert less than returning visitors**
- Evidence: 6.64% vs 7.83%.
- Action: invest in retention through email and remarketing.

### Product and refunds

**5. Revenue depends on one product**
- Evidence: Mr. Fuzzy earns $1.21M of $1.94M (about 62%).
- Action: protect its stock and quality, and promote other products.

**6. One product has high refunds**
- Evidence: Birthday Sugar Panda 6.04% vs 4.40% overall.
- Action: check quality, descriptions and customer feedback.

**7. The best seller has the lowest margin**
- Evidence: Mr. Fuzzy 58.9% vs Hudson River Mini Bear 67.9% (net margin).
- Action: review costs and pricing before discounting Mr. Fuzzy.

**8. Most orders contain one item**
- Evidence: one-item orders average $50.82; two-item orders average $89.25.
- Action: introduce bundles and add-on offers.

### Marketing and planning

**9. Traffic with no source information**
- Evidence: 83,328 sessions (17.62%) have no UTM data.
- Action: improve UTM tagging.

**10. Strong seasonality**
- Evidence: revenue and orders peak in Nov to Dec and dip in Apr to Aug.
- Action: plan inventory and campaigns for Q4, and run promotions in slow months.

### Statistical check: are refunds linked to product?

A chi-square test found a statistically significant association between product and refund status. Cramér's V was 0.078, so the effect is small. Each product has a single price, so product effects cannot be separated from price effects, and the data cannot show that the product itself causes refunds.

---

## Tools & Technologies

- **Python** (Pandas, Matplotlib, Seaborn, SciPy): cleaning, EDA and statistical testing
- **Google Colab**: notebook-based analysis
- **Power BI and DAX**: data model, KPIs, conversion rates and product measures
- **AI Tools** (**Chatgpt** it is for deep Analysis ,**Claude** for Documentation for this Project)

---

## Repository Structure

```
E-commerce-funnel-analysis/
├── README.md
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   └── 02_data_analysis.ipynb
├── data/
│   ├── raw/
│   └── cleaned/
└── images/
    ├── Acquisition & Funnel page.png
    ├── Executive overview.png
    └── Product Performance page .png
```

---

## Limitations

- Refund and price findings show association, not causation. Hypotheses about quality, descriptions or pricing need further testing, for example A/B tests or customer feedback.
- Channel conversion differences were measured, but the reasons behind them were not tested.
- The Power BI `.pbix` file is not included because of its file size. The screenshots above preview the report.

---

## Author

**Nijamoddin**

GitHub: [nijamoddin097](https://github.com/nijamoddin097)
