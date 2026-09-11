# Superstore Sales & Profit Dashboard

An interactive Power BI dashboard built on the classic "Superstore" retail dataset. It answers a core set of business questions — where is the money coming from, where is it being lost, who are the best customers, and how efficient are operations — across 4 focused pages.

## 📊 Project Goal

Raw transactional data (one row per order line) is hard to act on. This dashboard aggregates 9,994 order lines across 5,009 orders (2014–2017) into a small set of visuals, each designed to answer one specific business question rather than just "showing data." The guiding principle: every chart on this dashboard exists because it answers a question a manager would actually ask.

## 🖼️ Screenshots

| Page 1 - Executive Overview | Page 2 - Product & Segment Analysis |
|---|---|
| ![Page 1 - Executive Overview](screenshot%20(1).png) | ![Page 2 - Product & Segment Analysis](screenshot%20(2).png) |

| Page 3 - Geography & Customer Analysis | Page 4 - Operations |
|---|---|
| ![Page 3 - Geography & Customer Analysis](screenshot%20(3).png) | ![Page 4 - Operations](screenshot%20(4).png) |

## 📄 Page 1 — Executive Overview

**Business question answered:** "How is the business doing overall, and is that trend improving or getting worse?"

![Page 1 - Executive Overview](screenshot%20(1).png)

| Visual | Fields | Why this chart | What it shows |
| --- | --- | --- | --- |
| Sales & Profit Trend by Month (combo chart: columns + line) | Month Year (axis), Total Sales (columns), Total Profit (line) | A combo chart was chosen deliberately instead of two separate charts. Sales and Profit are on different scales and don't always move together — a discount campaign can push Sales up while Profit stays flat or drops. Overlaying both on one timeline makes that divergence visible at a glance, which a manager scanning quickly would otherwise miss. | Profit grew **+89%** from 2014 to 2017 ($49.5K → $93.4K) while Sales grew only **+51%** ($484K → $733K) — profitability is improving faster than revenue, meaning the business is getting more efficient over time, not just bigger. |
| 6 KPI Cards | Total Sales, Total Profit, Avg Order Value, Total Orders, Total Quantity, Profit Margin % | Cards were used instead of a table because an executive needs the headline numbers in under 2 seconds, with no reading required. These 6 specifically were chosen to cover volume (Orders, Quantity), value (Sales, Avg Order Value), and health (Profit, Profit Margin %) — so no single card can be misread in isolation (e.g. high Sales alone means nothing without Profit Margin next to it). | Across the full dataset: **Total Sales $2,297,201**, **Total Profit $286,397**, **5,009 Orders**, **Profit Margin 12.47%**. |

## 📄 Page 2 — Product & Segment Analysis

**Business question answered:** "Which products and customer types actually make us money — and is our discounting strategy hurting margin?"

![Page 2 - Product & Segment Analysis](screenshot%20(2).png)

| Visual | Fields | Why this chart | What it shows |
| --- | --- | --- | --- |
| Discount Impact on Profit Margin by Sub-Category (scatter chart) | X: Avg Discount, Y: Profit Margin %, size: Total Sales, category: Sub-Category | A scatter chart is the right tool here because the question is about the relationship between two numeric variables (discount vs. margin), not a ranking. Each bubble is one sub-category, sized by sales volume — so a sub-category that's both heavily discounted AND high-volume AND low-margin stands out immediately as a place to investigate pricing. A bar chart couldn't show this three-way relationship at once. | The pattern is exactly what the chart is built to catch: **Tables** (26% avg. discount) sits at **-8.6% margin** on $207K of sales, and **Bookcases** (21% avg. discount) sits at **-3.0% margin** — both are losing money. By contrast, low-discount sub-categories like **Labels** (44.4% margin, <7% discount) and **Paper** (43.4% margin, <8% discount) prove the relationship: less discounting, more margin. |
| Sales by Category (column chart) | Category, Total Sales | Only 3 categories exist (Furniture, Office Supplies, Technology), so a simple column chart is the clearest way to rank them — no need for anything more complex with so few data points. | Technology leads sales ($836K) and margin (17.4%). **Furniture is the weak link**: #2 by sales ($742K) but only **2.5% margin** — a top-line-healthy, bottom-line-weak category that a sales-only view would hide. |
| Sales & Profit by Customer Segment (bar chart) | Segment, Total Sales, Total Profit | Segment (Consumer / Corporate / Home Office) is compared on both Sales and Profit side by side, because a segment can generate strong revenue while being disproportionately less profitable — the two bars together reveal that instead of hiding it. | Consumer is the largest segment by both Sales ($1.16M) and Profit ($134K), but Corporate holds a similar profit-to-sales ratio, while Home Office runs slightly leaner on both metrics. |
| Top Product Performance (table) | Product Name, Total Sales, Total Profit, Profit Margin % | Individual products (hundreds of them) don't work well as a chart — there are too many to visualize meaningfully. A sortable table lets the viewer drill into specific product-level numbers on demand, which is what a table is for and a chart is not. | Top seller: **Canon imageCLASS 2200 Advanced Copier** ($61.6K sales, $25.2K profit). Biggest loss-makers: the **Cubify CubeX 3D Printer** (Double and Triple Head variants, -$8.9K and -$3.8K respectively) — worth a pricing or discontinuation review. |

## 📄 Page 3 — Geography & Customer Analysis

**Business question answered:** "Where are our customers, and who are the ones we can't afford to lose?"

![Page 3 - Geography & Customer Analysis](screenshot%20(3).png)

| Visual | Fields | Why this chart | What it shows |
| --- | --- | --- | --- |
| Sales by State (column chart, all states) | State, Total Sales | Shown as a full ranked column chart rather than a map, because the goal here is precise comparison ("is California really that far ahead of New York?"), which a bar/column chart supports better than a map — maps are great for spatial pattern recognition but weaker for exact ranking comparisons. | California leads by a wide margin ($458K), followed by New York ($311K). **Texas is the standout red flag**: it ranks #3 in Sales ($170K) but posts the **worst Profit of any state (-$25.7K)** — a gap invisible on a sales-only ranking. Ohio (-$17K), Pennsylvania (-$15.6K), and Illinois (-$12.6K) form a cluster of similarly high-volume, loss-making states. |
| Top 10 Customers by Sales (bar chart, filtered) | Customer Name, Total Sales — Top N filter (10) | With hundreds of customers, showing all of them would be unreadable. A Top N filter narrows this to the customers who matter most for revenue concentration — useful for identifying key accounts that deserve retention focus. | Top customer is **Sean Miller** ($25,043), followed by **Tamara Chand** ($19,052) and **Raymond Buch** ($15,117) — the clearest starting list for account-retention outreach. |
| Average Discount by Category (column chart) | Category, Avg Discount | Placed on this page (rather than Page 2) because it's framed here as a customer-facing pricing question — which categories are customers getting the best deals on — complementing the customer-focused visuals around it. | Furniture carries the heaviest average discounting of the three categories, which lines up directly with it also being the lowest-margin category on Page 2 — the two pages tell the same story from different angles. |

## 📄 Page 4 — Operations

**Business question answered:** "How does the business perform logistically — by region and by how orders are shipped?"

![Page 4 - Operations](screenshot%20(4).png)

| Visual | Fields | Why this chart | What it shows |
| --- | --- | --- | --- |
| Sales by Region (bar chart) | Region, Total Sales | Only 4 regions (East, West, Central, South), so a simple bar chart gives a fast, unambiguous comparison without any visual clutter. | **West leads on both Sales ($725K) and Profit ($108K)**. **Central is the weakest performer relative to its size** — 3rd in raw sales but disproportionately behind on profit ($40K), lagging even South ($47K profit on lower sales). |
| Sales by Shipping Mode (column chart) | Ship Mode, Total Sales | Shows how much revenue moves through each shipping method (Standard Class, Second Class, First Class, Same Day) — relevant for understanding shipping cost exposure and customer delivery preferences, which ties sales performance to operational/logistics decisions. | Standard Class dominates with $1.36M in sales (59% of total) — the majority of operational cost exposure sits in one shipping tier, which matters for any future logistics-cost analysis. |

## 🗂️ Data Source

The dashboard uses the classic "Sample - Superstore" retail dataset, originally distributed as a built-in sample dataset with Tableau Desktop and widely re-hosted on platforms like Kaggle for analytics practice. It contains order-level transaction data:

- **Order details:** Order ID, Order Date, Ship Date, Ship Mode
- **Customer details:** Customer ID, Customer Name, Segment
- **Geography:** Country, State, City, Region, Postal Code
- **Product details:** Category, Sub-Category, Product Name
- **Financials:** Sales, Discount, Profit, Quantity

## 📌 Key Measures (DAX)

| Measure | DAX | Why it matters |
| --- | --- | --- |
| Total Sales | `SUM(Superstore[Sales])` | Top-line revenue |
| Total Profit | `SUM(Superstore[Profit])` | Bottom-line result — the number that actually matters more than revenue alone |
| Total Orders | `DISTINCTCOUNT(Superstore[Order ID])` | Order-level volume, since each order can span multiple line items |
| Total Quantity | `SUM(Superstore[Quantity])` | Units moved, independent of price |
| Avg Order Value | `DIVIDE([Total Sales], [Total Orders], 0)` | Signals whether growth is coming from more orders or bigger orders. `DIVIDE()` avoids `#DIV/0!` on filtered views with zero orders |
| Profit Margin % | `DIVIDE([Total Profit], [Total Sales], 0)` | Health indicator — high sales with low margin is a warning sign, not a win |
| Avg Discount | `AVERAGE(Superstore[Discount])` | Tracks how much margin is being given away to drive sales |

All figures quoted throughout this README were computed independently in Python/pandas directly from `Superstore_Cleaned.xlsx` to cross-check the Power BI measures — Total Sales, Total Profit, and Profit Margin % reconcile exactly between the two.

## 🛠️ Tech Stack

- Power BI Desktop — data modeling, DAX measures, and report design
- Custom Power BI theme — consistent color palette applied across all visuals

## 🚀 How to Use

1. Download `superstore-dashboard.pbix`
2. Open it with Power BI Desktop (free, Windows only)
3. Explore each page using the tabs at the bottom of the report

## 📁 Repository Structure

```
├── superstore-dashboard.pbix     # Main Power BI report
├── Superstore_Cleaned.xlsx       # Source data
├── screenshot (1).png            # Page 1 - Executive Overview
├── screenshot (2).png            # Page 2 - Product & Segment Analysis
├── screenshot (3).png            # Page 3 - Geography & Customer Analysis
├── screenshot (4).png            # Page 4 - Operations
├── README.md
├── LICENSE
└── .gitignore
```

## 📃 License

This project is licensed under the MIT License — see the LICENSE file for details.

## ✍️ Author

Built as a personal / portfolio data analytics project using Power BI.
