# EDA-Online-Retail-UK
Exploratory Data Analysis of 1M+ transactions from a UK wholesale retailer using Python and Power BI
## Dataset
**Name:** Online Retail II  
**Source:** UCI Machine Learning Repository  
**URL:** https://archive.ics.uci.edu/dataset/502/online+retail+ii  
**Format:** .xlsx (two sheets: 2009-2010, 2010-2011)  
**Size:** ~45MB, 1,067,371 rows, 8 columns  
The dataset features two primary tables representing different timeframes:
* `Year 2009-2010`
* `Year 2010-2011`

### Data Attributes
* **Invoice:** Unique 6-digit identifier for each transaction (cancelled orders start with 'C').
* **StockCode:** Unique product identifier.
* **Description:** Product name.
* **Quantity:** The quantities of each product per transaction.
* **InvoiceDate:** The day and time when a transaction was generated.
* **Price:** Product price per unit.
* **Customer ID:** Unique customer identifier.
* **Country:** The name of the country where each customer resides.

## Project Overview
The objective of this project is to analyze historical transactions to identify revenue drivers, evaluate customer purchasing behavior, and uncover operational inefficiencies. By cleaning and aggregating millions of data points, this analysis provides clear visibility into product performance, regional growth, and customer lifetime value.
A UK-based wholesale giftware retailer selling to small shop owners and businesses (B2B).Customers order in pack sizes of 12, 24, 48 units. 91% of revenue from UK. 43 countries in total.
<img width="2465" height="1482" alt="EDA-Project" src="https://github.com/user-attachments/assets/002f2176-f01f-4f38-8087-9944a62f195c" />
## Key Findings

## Finding 1 — Zero revenue growth over 2 years
Revenue in 2010: £9,833,100. Revenue in 2011: £9,820,676. 
Growth: -0.1%. The business is in maintenance mode, not growth mode.
New customers are replacing churned ones, not adding to the base.
<img width="1589" height="985" alt="monthly_trend" src="https://github.com/user-attachments/assets/4017f70b-ef8b-4428-acc3-a4ef85af3689" />

## Finding 2 — Q4 drives 37% of all revenue
November is the biggest month every year (£2.97M combined across both years).
October, November, December = £7.56M out of £20.47M total revenue.
February experiences the slowest sales of the year, dipping down to a performance that is 2.8 times smaller than the November peak.
<img width="1389" height="490" alt="seasonality" src="https://github.com/user-attachments/assets/58314bf4-d9d1-4f72-893b-9d05e2aa9acf" />

## Finding 3 — Repeat buyers generate 96.8% of revenue
One-time buyers = 27.6% of customers but only 3.2% of revenue (£560K).
Repeat buyers = 72.4% of customers and generate £16.8M.
974 loyal customers (10+ orders) are the backbone of the business.
<img width="1250" height="495" alt="customer_loyalty" src="https://github.com/user-attachments/assets/2a3af350-90d3-4ad1-916b-03a86d72b1f4" />

## Finding 4 — 34% cancellation rate: a severe operational vulnerability
13,676 of 40,077 orders were cancelled or returned.
Revenue lost: £1,620,726 (7.9% of clean revenue).
At typical wholesale margins, true profit cost is £600K–£800K annually.
<img width="1189" height="490" alt="returns_by_country" src="https://github.com/user-attachments/assets/b96beaac-78d9-4815-9a49-847c909929e3" />

## Finding 5 — 23% of customers generate 80% of revenue
1,353 customers out of 5,878 drive 80% of all revenue.
Top 10 customers alone = 16% of total revenue (£3.27M).
Top customer (ID 18102) = £580,987 — 2.8% of total revenue from one account.
<img width="1389" height="490" alt="customer_concentration" src="https://github.com/user-attachments/assets/2639ef9b-b359-43bd-b4af-f1ea1a9b1c6c" />

## Finding 6 — International markets are underdeveloped
UK = 85% of revenue (£17.4M). Only 15% from 42 other countries.
EIRE (£658K), Netherlands (£554K), Germany (£425K) are proven markets.
Australia shows high average order value despite few customers.
<img width="1589" height="611" alt="country_distribution" src="https://github.com/user-attachments/assets/f74753b9-74f7-4715-971b-ae38e272df75" />

## Finding 7 — Revenue is driven by volume, not price
Quantity → Revenue correlation: 0.81 (very strong).
Price → Revenue correlation: 0.25 (weak).
63% of products priced £1–5. Median unit price: £2.10.

Note: Price elasticity analysis was considered but not executed.The dataset lacks sufficient price variation per product to produce statistically valid elasticity coefficients.
<img width="742" height="590" alt="correlation_heatmap" src="https://github.com/user-attachments/assets/779f4057-14bb-4678-9363-a2ad69ad28c6" />


## Project Workflow

### 1. Data Cleaning & Preparation
* Consolidated transactional data across both fiscal years.
* Handled missing values within critical fields such as `Customer ID` and `Description`.
* Filtered and separated negative transactions to accurately isolate successful sales from returns and cancellations.
* Formatted dates and created time-based fields (`YearMonth`, `Year`) for chronological tracking.

### 2. Exploratory Data Analysis & Aggregation
* Engineered a `Revenue` metric computed as $Quantity \times Price$.
* Grouped transactions chronologically to map out the monthly revenue trajectory.
* Segmented the customer base to distinguish revenue shares between one-time buyers and loyal repeat customers.
* Aggregated revenue metrics by product descriptions and geographic regions to extract top performers.

### 3. Dashboard Design & Reporting
* Developed an intuitive dashboard layout to present high-level KPIs clearly.
* Built trend lines, bar charts, and composition metrics to visualize complex commercial patterns at a glance.

## Technologies Used
* **Python** (Pandas, NumPy for data manipulation)
* **Matplotlib & Seaborn** (For statistical visualization during data exploration)
* **Jupyter Notebook**
* **Power BI** (For interactive dashboard and business reporting)
  





