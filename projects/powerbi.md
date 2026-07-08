# Power BI

A collection of Power BI labs completed during my Data Analyst bootcamp.

## Contents
- [1. Retail Sales Dashboard](#1-retail-sales-dashboard)

---

## 1. Retail Sales Dashboard

For this project, I explored Power Query in Excel to clean and shape a retail sales dataset, then exported it into Power BI to build an interactive dashboard.

🔗 [View live dashboard](https://app.powerbi.com/view?r=eyJrIjoiZDllZjE0YjItOWY0OC00ZmJlLWEyY2ItMmQ1ODk5ZjUwNmVmIiwidCI6IjNlYTdjMTI4LWM2MDEtNDQ3OS1hMDAzLWUxNGQwMGMwYjVjYiJ9)

![Retail Sales dashboard](../images/retail_powerbi_dash.png)

*Note: the decomposition tree (bottom right) doesn't render in the shared/embedded 
version due to a known Power BI limitation with AI-powered visuals. It's fully 
functional in Power BI Desktop, shown in the screenshot above.*

### What I built:

**Sum of Sales by Segment** <br>
A pie chart showing the proportion of total sales coming from Consumer, Corporate, and 
Home Office segments <br>

**Count of Segment by Category** <br>
A bar chart showing how many transactions fall into each product category (Office 
Supplies, Furniture, Technology) <br>

**Sum of Sales (KPI card)** <br>
A card visual highlighting the overall sales total (651K) at a glance <br>

**Sales Details** <br>
A table showing order-level data: Discount, Sales, Profit, Quantity, and Category,
for anyone wanting to look at individual transactions rather than summaries <br>

**Sales Breakdown by Region, Country, and City** <br>
A decomposition tree letting you drill down from total sales through Region → Country 
→ City, with filters for each level <br>

### Why this is useful:
Bringing all of this together into one dashboard means a business doesn't have to dig through raw spreadsheet rows to understand performance. At a glance, they can see which customer segment and product category drive the most sales, then use the decomposition tree to drill into exactly which region, country, or city is performing well or underperforming, which is much quicker than filtering a spreadsheet manually. The interactivity (filters, drill-down) also means the same dashboard can answer many different questions without needing to rebuild it each time.
