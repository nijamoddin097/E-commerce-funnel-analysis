E-Commerce Funnel Analysis & Product Profitability

An end-to-end e-commerce analytics project on website acquisition, customer purchase behavior, funnel drop-offs, refunds and product profitability, built with Python, Google Colab and Power BI.

Project Overview

The project follows visitors of an online toy retailer (4 products, March 2012 to March 2015) from first session to purchase. It identifies where potential customers leave the funnel, which acquisition channels and products drive growth, and how refunds affect profit.

Data was cleaned and explored in Python, then presented in an interactive three-page Power BI dashboard.

Headline numbers

Metric	Value
Revenue (before refunds)	$1.94M
Orders	32.31K
Website sessions	472.87K
Overall conversion rate	6.83%
Average order value	$59.99
Refunds	$85,338.69 (4.40% of revenue)
The 10 Business Questions
#	Business question	Finding
1	Which acquisition channels convert best?	Unattributed 7.34%, bsearch 7.19%, gsearch 6.75%. Socialbook converts at only 3.21%, less than half of any other channel. gsearch brings about two-thirds of all traffic and orders.
2	Where does the funnel lose the most sessions?	Product Detail → Cart: 54.8% of sessions stop here (210,214 → 94,953).
3	Which products progress best from product page to cart?	Hudson River Mini Bear 65.1%, Forever Love Bear 55.6%, Birthday Sugar Panda 46.3%, The Original Mr. Fuzzy 43.0%, even though Mr. Fuzzy gets about 77% of product-page sessions.
4	Do new and returning visitors behave differently?	Returning visitors convert better (7.83% vs 6.64%) and earn more per session ($4.74 vs $3.97). New visitors still produce about 81% of revenue because they are 83% of sessions.
5	Which products generate the most revenue and profit?	Mr. Fuzzy leads with $1.21M revenue and $677K net profit, followed by Forever Love Bear ($210K), Birthday Sugar Panda ($143K) and Hudson River Mini Bear ($101K).
6	Which products have the best margins?	Net margin after refunds: Hudson River 67.9%, Birthday Sugar Panda 66.5%, Forever Love 61.7%, Mr. Fuzzy 58.9%. The top seller has the lowest margin.
7	Which products are refunded most, and is the difference real?	Refund rates: Birthday Sugar Panda 6.04%, Mr. Fuzzy 5.11%, Forever Love 2.23%, Hudson River 1.28%. A chi-square test shows the difference is statistically significant, but Cramér's V of 0.078 shows the effect is small.
8	How does basket size affect order value?	One-item orders (76.1%) average $50.82. Two-item orders (23.9%) average $89.25.
9	How did the business grow over time?	Monthly sessions grew about 15.8× (1,879 in Mar 2012 to 29,722 in Dec 2014). Conversion improved from 3.19% to 8.70% (Feb 2015). 2014 revenue grew roughly 150–240% year over year in every month.
10	Is there seasonality?	Revenue and orders are lowest from April to August and peak in November and December (monthly totals across years). March 2015 is a partial month and is excluded from trend conclusions.
Data and Cleaning

Six tables were used in Python: website_sessions (472,871 rows), website_pageviews (1,188,124), orders (32,313), order_items (40,025), order_item_refunds (1,731) and products (4). In Power BI a date table was added to the model.

Converted all created_at fields from text to datetime.
Checked duplicates and missing values: no duplicate rows or session IDs.
83,328 sessions (17.62%) had no UTM data and were labelled Unattributed. Of these, 43,411 carry a gsearch or bsearch referrer, so they are likely untagged search traffic. The other 39,917 have no referrer and are likely direct visits.
Reviewed outliers (price, COGS, items purchased, refund amount) with box plots. No records needed removal.
Exported six validated clean files that feed the Power BI model.

Power BI data model decisions: removed the refunds → orders relationship, kept orders → order_items as the active relationship, linked a single date table to the cleaned sessions table, and kept the original created_at columns hidden.

## Power BI Dashboard
Three pages with shared Year, Month and utm_source slicers.

### 1. Executive Overview
![Executive Overview](images/Executive%20overview.png)

This page presents high-level business KPIs, including total revenue, total orders, website sessions, and conversion rate. It also displays monthly revenue trends, monthly order volume, and net profit by product.



### 2. Acquisition & Funnel Analysis
![Acquisition and Funnel Analysis](images/Acquisition%20%26%20Funnel%20page.png)

This page compares acquisition-channel conversion rates, visualizes the website purchase funnel, examines product-detail-to-cart progression, and compares new and returning visitor sessions.



### 3. Product Performance & Profitability
![Product Performance and Profitability](images/Product%20Performance%20page%20.png)

This page compares revenue by product, profit margin, order volume by product, and revenue versus net profit to help assess product-level business performance.



Business Problems Identified & Recommendations
Area	Problem	Evidence	Recommended action
Funnel	Customers drop off before adding to cart	Only 45.2% of product-detail sessions reach the cart (54.8% lost, the largest drop in the funnel)	Review product-page content, images and add-to-cart placement, and A/B test changes
Funnel	Cart conversion differs by product	Hudson River Mini Bear 65.13% vs The Original Mr. Fuzzy 43.04%; Mr. Fuzzy gets about 77% of product-page sessions	Fix the Mr. Fuzzy page first; send more traffic to Hudson River
Acquisition	One channel converts poorly	Socialbook converts at 3.21% vs 6.75% to 7.34% for the others	Review spend, targeting and landing page before scaling
Visitors	New visitors convert less than returning visitors	6.64% vs 7.83%	Invest in retention: email and remarketing
Product	Revenue depends on one product	Mr. Fuzzy earns $1.21M of $1.94M (about 62%)	Protect its stock and quality; promote other products
Refunds	One product has high refunds	Birthday Sugar Panda 6.04% vs 4.40% overall	Check quality, descriptions and customer feedback
Profitability	Best seller has the lowest margin	Mr. Fuzzy 58.9% vs Hudson River Mini Bear 67.9% (net margin)	Review costs and pricing before discounting Mr. Fuzzy
Order value	Most orders contain one item	One-item orders average $50.82; two-item orders average $89.25	Introduce bundles and add-on offers
Data quality	Traffic with no source information	83,328 sessions (17.62%) have no UTM data; 43,411 of them carry a search referrer	Improve UTM tagging
Planning	Strong seasonality	Revenue and orders peak in Nov to Dec and dip in Apr to Aug	Plan inventory and campaigns for Q4; run promotions in slow months
Statistical check: are refunds linked to product?

A chi-square test found a statistically significant association between product and refund status. Cramér's V was 0.078, so the effect is small. Each product has a single price, so product effects cannot be separated from price effects, and the data cannot show that the product itself causes refunds.

Tools & Technologies
Python (Pandas, Matplotlib, Seaborn, SciPy): cleaning, EDA and statistical testing
Google Colab: notebook-based analysis
Power BI and DAX: data model, KPIs, conversion rates and product measures

Repository Structure
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
    
#Limitations
Refund and price findings show association, not causation. Each product has a single price, so product effects cannot be separated from price effects. Hypotheses about quality, descriptions or pricing need further testing, for example A/B tests or customer feedback.
Channel conversion differences were measured, but the reasons behind them were not tested.
The Power BI .pbix file is not included because of its file size. The screenshots above preview the report.
Author

#Nijamoddin H | GitHub: nijamoddin097
