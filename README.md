# E-Commerce Funnel Analysis & Product Profitability

An end-to-end e-commerce analytics project focused on website acquisition, customer purchase behavior, funnel drop-offs, and product performance using Python, Google Colab, and Power BI.

## Project Overview

The objective of this project is to understand how visitors move through an e-commerce website, identify where potential customers leave the purchase funnel, compare acquisition-channel performance, and evaluate product revenue and profitability.

The project combines data cleaning, exploratory data analysis, and an interactive three-page Power BI dashboard to support data-driven business decisions.

## Business Objectives

- Evaluate revenue, orders, website sessions, and purchase conversion.
- Compare conversion rates across acquisition channels.
- Identify the stages with the largest website funnel drop-offs.
- Compare product-detail sessions with sessions that subsequently reach the cart.
- Analyze product revenue, order volume, net profit, and profit margin.
- Develop business recommendations based on verified analytical findings.

## Tools & Technologies

- **Python** — data cleaning and exploratory data analysis.
- **Google Colab** — notebook-based analysis workflow.
- **Power BI** — interactive dashboard development.
- **DAX** — measures for KPIs, conversion rates, and product analysis.

## Project Workflow

1. Inspect and understand the raw datasets.
2. Clean and prepare the data for analysis.
3. Conduct exploratory data analysis using Python.
4. Analyze acquisition channels, website funnel stages, and product performance.
5. Build an interactive Power BI report with date and channel slicers.
6. Summarize the findings and formulate business recommendations.

## Power BI Dashboard

### 1. Executive Overview
![Executive Overview](images/Executive%20overview.png)

This page presents high-level business KPIs, including total revenue, total orders, website sessions, and conversion rate. It also displays monthly revenue trends, monthly order volume, and net profit by product.



### 2. Acquisition & Funnel Analysis
![Acquisition and Funnel Analysis](images/Acquisition%20%26%20Funnel%20page.png)

This page compares acquisition-channel conversion rates, visualizes the website purchase funnel, examines product-detail-to-cart progression, and compares new and returning visitor sessions.



### 3. Product Performance & Profitability
![Product Performance and Profitability](images/Product%20Performance%20page%20.png)

This page compares revenue by product, profit margin, order volume by product, and revenue versus net profit to help assess product-level business performance.



## Key Business Questions

- Which acquisition channels have the highest observed conversion rates?
- At which stage does the website funnel lose the most sessions?
- Which product pages have the strongest progression from product detail to cart?
- Which products generate the most revenue and net profit?
- Which products have the highest profit margins?

## Business Recommendations

The recommendations should be based on verified analysis results. Potential areas for investigation include:

- Investigating the largest funnel drop-off and testing improvements to the customer journey.
- Evaluating acquisition channels using conversion rates alongside traffic volume.
- Comparing product sales, net profit, and profit margin before making merchandising or marketing decisions.
- Monitoring performance across date ranges to identify meaningful changes.

## Repository Structure

```text
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

## Limitations

The Power BI `.pbix` file is not currently included in this repository because of its file-size constraint. The screenshots are provided to preview the report. Interactive access can be added separately if a suitable sharing option is available.

Dataset redistribution permissions and file-size constraints should be checked before publishing datasets publicly.

## Author

**Nijamoddin**

GitHub: [nijamoddin097](https://github.com/nijamoddin097)

