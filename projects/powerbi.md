# Power BI

A collection of Power BI labs completed during my Data Analyst bootcamp.

## Contents
- [1. Retail Sales Dashboard](#1-retail-sales-dashboard)
- [2. Data Preparation in Power BI Lab](#2-data-preparation-in-power-bi-lab)
- [3. Designing a Power BI Report Lab](#3-designing-a-power-bi-report-lab)
- [4. Visual Calculations in Power BI Lab](#4-visual-calculations-in-power-bi-lab)


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

## 2. Data Preparation in Power BI Lab

I worked through two connected labs covering how to get, clean, and load data into 
Power BI, importing from multiple sources, fixing data quality issues, and shaping tables ready for reporting.<br>
<br>

![Data profiling showing misspelled Warehouse value](../images/lab1_1.png)

I used Power Query's column profiling tools to check data quality across the imported 
tables. This surfaced a data entry issue; some rows had "Ware House" instead of 
"Warehouse", which needed fixing before the data could be trusted for analysis.<br>
<br><br>
<br>

![Final set of queries loaded, including CSV import](../images/lab1_4.png)

I imported an additional CSV file (Reseller Sales Targets) alongside the data already 
pulled from other sources, bringing the total to 8 queries ready to be shaped and 
loaded into the data model.<br>
<br><br>
<br>

![Merging and renaming columns to build a Salesperson table](../images/lab2_1.png)

I merged columns (combining first and last name into a single "Salesperson" field) 
and renamed others for clarity, for example, `EmployeeNationalIDAlternateKey` to 
`EmployeeID`, and `EmailAddress` to `UPN` (User Principal Name).<br>
<br><br>
<br>

![Replace Values fixing the Warehouse spelling issue](../images/lab2_2.png)

I used Replace Values to fix the "Ware House" data quality issue spotted earlier, 
correcting it to "Warehouse" across the dataset, then renamed several columns 
(Business Type, Reseller, State-Province, Country-Region) for consistency.<br>
<br><br>
<br>

![Merging queries and expanding ColorFormats columns](../images/lab2_3.png)

I merged the Product query with a ColorFormats lookup table, then expanded the 
Background Colour Format and Font Colour Format columns into the main table, adding 
extra formatting detail without manually re-entering it.<br>
<br><br>
<br>

![Final data model loaded into Power BI Desktop](../images/lab2_4.png)

Once all queries were cleaned and shaped, I loaded the final data model into Power BI 
Desktop, ready to build visuals and reports from.

---

## 3. Designing a Power BI Report Lab

I built a multi-page report with slicers, filters, and a combination chart to explore 
sales performance across years, regions, and product categories.<br>
<br>

![Year and Region slicers added to the report](../images/lab3_1.png)

I added a Year slicer and a Region slicer (using the Region hierarchy field) to let anyone viewing the report filter the whole page by year or region interactively.<br>
<br><br>
<br>

![Combo chart showing sales and profit margin by month](../images/lab3_2.png)

I built a combination chart, columns for Sum of Sales, with a line overlay for 
Profit Margin, broken down by month, alongside supporting charts for Sales by 
Country and Category, and Quantity by Category. I turned on data labels so exact 
values are visible without hovering.<br>
<br><br>
<br>

![Filters pane showing Category, Subcategory, Product, and Colour filters](../images/lab3_3.png)

I added page-level filters for Category, Subcategory, Product, and Colour, giving viewers control over which products' sales they want to focus on.

---

## 4. Visual Calculations in Power BI Lab

I used Power BI's visual calculations feature to add running totals, moving 
averages, and period-over-period comparisons directly onto a chart.<br>
<br>

![Base bar chart of sales and cost by year](../images/lab4_1.png)

I started with a simple bar chart comparing Sum of Sales and Sum of Cost by year, 
sorted ascending, as the base for the calculations that follow.<br>
<br><br>
<br>

![Running sum and moving average added as tooltip calculations](../images/lab4_2.png)

I added Profit, Profit versus previous period, Running sum, and Moving average as 
visual calculations, setting the latter two to display as tooltips, so the chart 
stays clean while still showing the extra detail on hover.<br>
<br><br>
<br>

![Running sum chart resetting at the start of each fiscal year](../images/lab4_4.png)

I updated the Running sum calculation using the `HIGHESTPARENT` reset parameter, so the running total restarts at the beginning of each new fiscal year rather than 
accumulating indefinitely, which is useful for year-on-year comparisons rather than an 
all-time total.<br>
<br>

---

## Skills Demonstrated

- Importing and merging data from multiple sources (CSV, database tables)
- Cleaning and transforming data using Power Query (Replace Values, renaming, merging columns)
- Building relationships between tables in the data model
- Creating pie, bar, and combination charts
- Using slicers and filters (page-level and visual-level) for interactive reports
- Building KPI cards and decomposition trees
- Creating visual calculations (running sum, moving average, period-over-period comparisons)
- Publishing and sharing interactive dashboards

<br>
