
# E-Commerce Funnel Analysis & Product Profitability

An end-to-end e-commerce analytics project exploring website acquisition, customer purchase behavior, funnel drop-offs, and product performance using Python, Google Colab, and Power BI.

## Project Overview

The goal of this project is to understand how visitors move through an e-commerce website, identify stages where potential customers drop off, compare acquisition-channel performance, and evaluate product revenue and profitability.

The project combines data cleaning, exploratory analysis, and an interactive three-page Power BI dashboard to support data-driven business decisions.

## Business Objectives

- Evaluate overall revenue, orders, website sessions, and purchase conversion.
- Compare acquisition-channel conversion performance.
- Identify drop-offs throughout the website purchase funnel.
- Compare product-detail sessions with sessions that subsequently reach the cart.
- Analyze product revenue, order volume, net profit, and profit margin.
- Translate analytical findings into actionable business recommendations.

## Tools & Technologies

- **Python** — data preparation and exploratory data analysis.
- **Google Colab** — notebook-based workflow.
- **Power BI** — interactive dashboard development and reporting.
- **DAX** — measures for KPIs and funnel/product analysis.

## Project Workflow

1. Inspect and clean the raw datasets.
2. Prepare analysis-ready datasets.
3. Perform exploratory data analysis in Python.
4. Analyze acquisition channels, website funnel stages, and product performance.
5. Build an interactive Power BI report with date and channel slicers.
6. Summarize findings and develop business recommendations.

## Power BI Dashboard

### 1. Executive Overview

Provides a high-level view of revenue, orders, website sessions, conversion rate, monthly revenue trends, monthly orders, and product-level net profit.

![Executive Overview](images/executive_overview.png)

### 2. Acquisition & Funnel Analysis

Compares acquisition-channel conversion rates, visualizes the website purchase funnel, examines product-detail-to-cart progression, and compares new and returning visitor sessions.

![Acquisition and Funnel Analysis](images/acquisition_funnel.png)

### 3. Product Performance & Profitability

Compares revenue by product, profit margin, product order volume, and revenue versus net profit.

![Product Performance and Profitability](images/product_performance.png)

## Initial Business Questions

- Which acquisition channels have the highest observed conversion rates?
- At which stage does the website funnel lose the most sessions?
- Which products have the strongest product-detail-to-cart progression?
- Which products generate the most revenue and net profit?
- Which products have the highest profit margins?

## Business Recommendations

The final recommendations will be based on verified results from the analysis. Potential areas for investigation include improving high-drop-off funnel stages, evaluating acquisition-channel quality, and comparing product sales with profitability before making marketing or merchandising decisions.

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
├── powerbi/
└── images/
    ├── executive_overview.png
    ├── acquisition_funnel.png
    └── product_performance.png
```

## Limitations

The Power BI report file is not currently included in this repository because of its file-size constraint. The dashboard screenshots are provided for preview. Interactive report access can be added separately if a suitable sharing option is available.

## Author

**Nijamoddin**

GitHub: [nijamoddin097](https://github.com/nijamoddin097)


