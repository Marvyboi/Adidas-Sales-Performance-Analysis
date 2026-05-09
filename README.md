# 👟 Adidas Sales Performance Analysis
### Beginner Capstone — Group 10

An Excel-based business intelligence project analyzing Adidas sales data across US regions, retailers, product categories, and sales channels to generate actionable insights for strategic decision-making.

---

## 📌 Project Overview

Adidas collects large volumes of transactional sales data through multiple retail partners and distribution channels, but that data had not been fully leveraged to identify trends, performance gaps, or optimization opportunities. This project transforms raw sales records into a clean, interactive dashboard that surfaces revenue drivers, profitability patterns, and customer behavior insights.

---

## 🎯 Objectives

- Measure overall sales and profitability performance across the analysis period
- Identify top-performing and underperforming product categories, regions, and channels
- Compare sales contributions of major retail partners
- Assess the effectiveness of different sales methods (in-store, outlet, online)
- Generate data-driven recommendations for sales, marketing, and inventory strategies

---

## 📁 File Structure

| Sheet | Description |
|---|---|
| `Data Sales Adidas` | Cleaned raw transactional data with derived columns |
| `Pivot Tables` | Aggregated summaries by product, region, retailer, method, month, and state |
| `Analysis` | Heat map and geographic state-level breakdown |
| `Dashboard` | Interactive visual dashboard with KPI cards and slicers |

---

## 📊 Dataset Details

**Source:** Adidas US Sales Database  
**Period:** 2020 (monthly data, Jan–Dec)  
**Retailers:** Foot Locker, West Gear, Sports Direct, Kohl's, Walmart, Amazon

### Columns

| Column | Description |
|---|---|
| Retailer | Retail partner name |
| Retailer ID | Unique retailer identifier |
| Invoice Date | Transaction date |
| Region | US region (West, Northeast, South, Southeast, Midwest) |
| State / City | Geographic location |
| Product | Product line description |
| Price per Unit | Unit selling price ($) |
| Units Sold | Number of units per transaction |
| Total Sales | Revenue (Price × Units) |
| Operating Profit | Profit (Total Sales × Operating Margin) |
| Operating Margin | Profit margin (%) |
| Sales Method | In-store / Outlet / Online |
| Year / Month / Quarter | Derived time fields |
| Product Category | Footwear or Apparel (derived) |
| Profit per Unit | Derived profitability metric |

---

## 🧹 Data Cleaning & Preparation

### Financial Recalculation
Original `Total Sales` and `Operating Profit` values contained errors and were corrected:

```
Total Sales      = Price per Unit × Units Sold
Operating Profit = Total Sales × Operating Margin
```

### Date Transformation
`Invoice Date` was split into three derived fields using Excel formulas:
- **Year** — `=YEAR()`
- **Month** — `=TEXT(...,"MMMM")`
- **Quarter** — `="Q"&ROUNDUP(MONTH(date)/3, 0)`

### Product Categorization
A `Product Category` column was derived:
```excel
=IF(ISNUMBER(SEARCH("Footwear", H6)), "Footwear",
  IF(ISNUMBER(SEARCH("Apparel", H6)), "Apparel", "Accessories"))
```

### Consistency Checks
- Standardized region and retailer naming conventions
- Uniform formatting of sales method values
- Removed duplicates and inconsistent entries

---

## 📈 KPIs

| Metric | Value |
|---|---|
| **Total Sales** | $120,166,650 |
| **Operating Profit** | $47,224,968 |
| **Average Operating Margin** | 42.30% |
| **Average Units Sold** | ~257 per transaction |

---

## 🔍 Key Insights

### 🏆 Sales by Product

| Product | Total Sales | Operating Profit |
|---|---|---|
| Men's Street Footwear | $27,680,769 | $11,629,046 |
| Women's Apparel | $23,870,985 | $9,685,221 |
| Men's Athletic Footwear | $20,577,180 | $7,437,457 |
| Women's Street Footwear | $17,201,563 | $6,494,017 |
| Men's Apparel | $16,520,632 | $6,381,405 |
| Women's Athletic Footwear | $14,315,521 | $5,597,822 |

> **Footwear accounts for ~66% of total sales; Apparel ~34%.**

### 🏪 Sales by Retailer

| Retailer | Total Sales |
|---|---|
| West Gear | $32,409,558 |
| Foot Locker | $29,024,945 |
| Sports Direct | $24,616,622 |
| Kohl's | $13,512,453 |
| Walmart | $10,506,085 |
| Amazon | $10,096,987 |

> West Gear and Foot Locker together account for over 50% of total revenue.

### 🛒 Sales by Channel

| Sales Method | Total Sales |
|---|---|
| Online | $44,965,657 |
| Outlet | $39,536,618 |
| In-store | $35,664,375 |

> **Online is the highest-performing channel.**

### 🌎 Profit by Region

| Region | Operating Profit |
|---|---|
| West | $13,017,584 |
| Northeast | $9,732,774 |
| South | $9,221,605 |
| Southeast | $8,393,059 |
| Midwest | $6,859,945 |

> The **West region consistently leads** in both sales and profit.

### 📅 Monthly Sales Trend

| Month | Total Sales |
|---|---|
| Jul | $12,550,419 |
| Aug | $12,293,226 |
| Dec | $11,415,332 |
| May | $10,741,720 |
| Jun | $9,803,147 |
| Mar | $7,694,984 *(lowest)* |

---

## 🛠️ Tools & Methodology

- **Microsoft Excel** — data cleaning and formula-based transformations
- **Pivot Tables** — aggregations by product, region, retailer, channel, month, and state
- **Pivot Charts** — bar, donut, and line charts
- **Slicers** — interactive filtering
- **Dashboard Design** — KPI cards, heat maps, and geographic visualization

---

## 🎛️ Dashboard Features

- **KPI Cards** — Total Sales, Operating Profit, Operating Margin, Avg Units Sold
- **Monthly Sales Trend** — seasonal pattern chart
- **Product Line × Region Heatmap** — cross-tab of all products across 5 US regions
- **Sales by Category** — donut chart (Footwear vs Apparel split)
- **Profit by Region** — bar chart
- **Sales by Retailer** — bar chart
- **Revenue by Sales Method** — column chart
- **Geographic State Map** — sales visualization across 20 US states
- **Slicers** — filter by Quarter, Region, Sales Method, and Product Category

---

## 💡 Recommendations

| Area | Recommendation |
|---|---|
| **Product Strategy** | Expand footwear offerings; optimize underperforming apparel lines |
| **Channel Optimization** | Prioritize online growth while maintaining outlet and in-store efficiency |
| **Regional Focus** | Increase investment in the West; develop targeted strategies for the Midwest |
| **Demand Forecasting** | Leverage monthly trends for inventory and production planning |
| **Retailer Management** | Deepen partnerships with West Gear & Foot Locker; reassess weaker retail partners |

---

## 👥 Team

**Group 10** — TS Academy Beginner Capstone

---

*This project demonstrates how structured data cleaning, pivot analysis, and dashboard design can transform raw transactional data into strategic business intelligence.*
