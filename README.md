# Superstore Sales & Profit Dashboard

An interactive Power BI dashboard built on the classic Superstore retail dataset. It answers a core set of business questions — where is the money coming from, where is it being lost, who are the best customers, and how efficient are operations — across 4 focused pages.

---

## 📊 Project Goal

Raw transactional data (one row per order line) is hard to act on. This dashboard aggregates ~5,000+ orders into a small set of visuals, each designed to answer **one specific business question** rather than just "showing data." The guiding principle: every chart on this dashboard exists because it answers a question a manager would actually ask.

---

## 🖼️ Screenshots

> Add screenshots of each page here before publishing.

```markdown
![Page 1 - Executive Overview](screenshots/page1-overview.png)
![Page 2 - Product & Segment Analysis](screenshots/page2-products.png)
![Page 3 - Geography & Customer Analysis](screenshots/page3-geography.png)
![Page 4 - Operations](screenshots/page4-operations.png)
```

---

## 📄 Page 1 — Executive Overview

**Business question answered:** *"How is the business doing overall, and is that trend improving or getting worse?"*

| Visual | Fields | Why this chart |
|---|---|---|
| **Sales & Profit Trend by Month** (combo chart: columns + line) | Month Year (axis), Total Sales (columns), Total Profit (line) | A combo chart was chosen deliberately instead of two separate charts. Sales and Profit are on different scales and don't always move together — a discount campaign can push Sales up while Profit stays flat or drops. Overlaying both on one timeline makes that divergence visible at a glance, which a manager scanning quickly would otherwise miss. |
| **6 KPI Cards** | Total Sales, Total Profit, Avg Order Value, Total Orders, Total Quantity, Profit Margin % | Cards were used instead of a table because an executive needs the headline numbers in under 2 seconds, with no reading required. These 6 specifically were chosen to cover volume (Orders, Quantity), value (Sales, Avg Order Value), and health (Profit, Profit Margin %) — so no single card can be misread in isolation (e.g. high Sales alone means nothing without Profit Margin next to it). |

---

## 📄 Page 2 — Product & Segment Analysis

**Business question answered:** *"Which products and customer types actually make us money — and is our discounting strategy hurting margin?"*

| Visual | Fields | Why this chart |
|---|---|---|
| **Discount Impact on Profit Margin by Sub-Category** (scatter chart) | X: Avg Discount, Y: Profit Margin %, size: Total Sales, category: Sub-Category | A scatter chart is the right tool here because the question is about the *relationship* between two numeric variables (discount vs. margin), not a ranking. Each bubble is one sub-category, sized by sales volume — so a sub-category that's both heavily discounted AND high-volume AND low-margin stands out immediately as a place to investigate pricing. A bar chart couldn't show this three-way relationship at once. |
| **Sales by Category** (column chart) | Category, Total Sales | Only 3 categories exist (Furniture, Office Supplies, Technology), so a simple column chart is the clearest way to rank them — no need for anything more complex with so few data points. |
| **Sales & Profit by Customer Segment** (bar chart) | Segment, Total Sales, Total Profit | Segment (Consumer / Corporate / Home Office) is compared on both Sales and Profit side by side, because a segment can generate strong revenue while being disproportionately less profitable — the two bars together reveal that instead of hiding it. |
| **Top Product Performance** (table) | Product Name, Total Sales, Total Profit, Profit Margin % | Individual products (hundreds of them) don't work well as a chart — there are too many to visualize meaningfully. A sortable table lets the viewer drill into specific product-level numbers on demand, which is what a table is for and a chart is not. |

---

## 📄 Page 3 — Geography & Customer Analysis

**Business question answered:** *"Where are our customers, and who are the ones we can't afford to lose?"*

| Visual | Fields | Why this chart |
|---|---|---|
| **Sales by State** (column chart, all states) | State, Total Sales | Shown as a full ranked column chart rather than a map, because the goal here is precise comparison ("is California really that far ahead of New York?"), which a bar/column chart supports better than a map — maps are great for spatial pattern recognition but weaker for exact ranking comparisons. |
| **Top 10 Customers by Sales** (bar chart, filtered) | Customer Name, Total Sales — Top N filter (10) | With hundreds of customers, showing all of them would be unreadable. A Top N filter narrows this to the customers who matter most for revenue concentration — useful for identifying key accounts that deserve retention focus. |
| **Average Discount by Category** (column chart) | Category, Avg Discount | Placed on this page (rather than Page 2) because it's framed here as a *customer-facing* pricing question — which categories are customers getting the best deals on — complementing the customer-focused visuals around it. |

---

## 📄 Page 4 — Operations

**Business question answered:** *"How does the business perform logistically — by region and by how orders are shipped?"*

| Visual | Fields | Why this chart |
|---|---|---|
| **Sales by Region** (bar chart) | Region, Total Sales | Only 4 regions (East, West, Central, South), so a simple bar chart gives a fast, unambiguous comparison without any visual clutter. |
| **Sales by Shipping Mode** (column chart) | Ship Mode, Total Sales | Shows how much revenue moves through each shipping method (Standard Class, Second Class, First Class, Same Day) — relevant for understanding shipping cost exposure and customer delivery preferences, which ties sales performance to operational/logistics decisions. |

---

## 🗂️ Data Source

The dashboard uses the classic **Superstore** retail dataset, containing order-level transaction data:

- **Order details:** Order ID, Order Date, Ship Date, Ship Mode
- **Customer details:** Customer ID, Customer Name, Segment
- **Geography:** Country, State, City, Region, Postal Code
- **Product details:** Category, Sub-Category, Product Name
- **Financials:** Sales, Discount, Profit, Quantity

---

## 📌 Key Measures

| Measure | Definition | Why it matters |
|---|---|---|
| Total Sales | Sum of order sales | Top-line revenue |
| Total Profit | Sum of order profit | Bottom-line result — the number that actually matters more than revenue alone |
| Avg Order Value | Total Sales ÷ Total Orders | Signals whether growth is coming from more orders or bigger orders |
| Profit Margin % | Total Profit ÷ Total Sales | Health indicator — high sales with low margin is a warning sign, not a win |
| Avg Discount | Average discount applied per order | Tracks how much margin is being given away to drive sales |

---

## 🛠️ Tech Stack

- **Power BI Desktop** — data modeling, DAX measures, and report design
- **Custom Power BI theme** — consistent color palette applied across all visuals

---

## 🚀 How to Use

1. Download `dashboard/superstore-dashboard.pbix`
2. Open it with [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free, Windows only)
3. Explore each page using the tabs at the bottom of the report

---

## 📁 Repository Structure

```
├── dashboard/
│   └── superstore-dashboard.pbix     # Main Power BI report
├── data/
│   └── superstore-data.xlsx          # Source data
├── screenshots/
│   ├── page1-overview.png
│   ├── page2-products.png
│   ├── page3-geography.png
│   └── page4-operations.png
├── README.md
└── LICENSE
```

---

## 📃 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## ✍️ Author

Built as a personal / portfolio data analytics project using Power BI.
