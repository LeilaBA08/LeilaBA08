# Excel Projects

A collection of Excel projects completed during my Data Analyst bootcamp, covering data cleaning, formulas, pivot tables, and visualisations.<br>
All datasets provided in the bootcamp are sourced from Kaggle. 

## Contents
- [1. Retail Sales Analysis](#1-retail-sales-analysis)
- [2. Bike Sales & SWITCH Dataset](#2-bike-sales--switch-dataset)
- [3. Bike Sales Visualisations](#3-bike-sales-visualisations)
- [4. Student Records Table](#4-student-records-table)

---

## 1. Retail Sales Analysis

For this task, I was given a retail sales dataset. I turned the raw data into a structured Excel table, then used formulas and pivot tables to calculate commission and summarise sales by customer and product category. 

### Building the table

![Retail sales table](../images/retail_sales_table.png)

*Raw data converted into an Excel Table using Ctrl+T. Columns: Transaction ID, Date, Customer ID, 
Gender, Age, Product Category, Quantity, Price per Unit*

Converting the data into an Excel Table makes it easier to sort, filter and reference formulas; it also expands automatically if more rows are added later.  
I then added two calculated columns:

![Total Sales formula](../images/retail_sales_totalsales_formula.png)

*Total Sales column added*

**Total Sales**:<br>`=G2*H2`, I used this formula to multiply the quantity by unit price to calculate the total value of each sale. This turns two raw figures into one meaningful number, which will later feed into calculations such as the commission totals.  

![Customer Category formula](../images/retail_sales_customerformula.png)

*Customer Category column added*

**Customer Category**:<br> `=IFS(E2>=50,"Senior",E2>=30,"Adult",E2<30,"Young Adult")`, This formula checks each customer's age and labels them Senior, Adult, or Young Adult. IFS checks each condition in order and stops at the first true match, making it a cleaner alternative to nesting several IF statements. Adding this column makes it easier to group and compare sales patterns across age groups. 

### Commission calculations

![Commission table filtered by age](../images/retailsalesWcommission.png)
*Filtered to customers aged 64, with Commission Amount added, plus a summary box for 
Commission Rate, Total, and Average.*

Filtered by Age to isolate a specific group, then added:

**Commission Amount Column**:<br>`=I3*$P$8`, Total Sales x a fixed 1.5% rate. The `$` locks 
the reference so it stays fixed when copied down each row, rather than shifting to a different cell each time.

**Commission Total**:<br>`=SUM(range)` shows the total commission earned across all filtered sales, providing an at-a-glance figure for total earnings.

**Average Commission**:<br> `=AVERAGE(range)` shows the typical commission per sale, which is more useful than the total when the number of sales varies. 

The total gives an overview of commission costs for budgeting, while the average shows what a typical sale earns. This is useful for spotting whether costs are changing due to sales volume or sales value. 

### Pivot tables and slicers

![Pivot table with slicers](../images/totalsalesSlicers.png)

*Total Sales by Customer Category and Product Category, with slicers for Gender, 
Product Category, and Customer Category.*

I built a pivot table to summarise sales by category, with slicers so anyone who views the sheet can filter interactively without needing to know Excel's filter menus. The slicers also make it quick to explore different combinations without rebuilding a table each time.<br>This is useful to see which groups and product categories are driving the most sales, so marketing or stock decisions can be focused on what's performing well. 

![Sales by gender percentage breakdown with chart](../images/perc_totalsales_by_gender.png)

*Total Sales by Gender and Product Category, shown as a % of Grand Total, with a clustered column chart.*

This second pivot table shows sales as a **percentage of total** rather than raw figures, which makes it easier to compare proportions between groups (For example, Female customers make up 51% of total sales). I paired this with a clustered column chart to make the comparison visually clear at a glance. 

Showing this as a percentage rather than raw totals makes it easier to compare groups fairly, even if one group has more overall sales. It is useful to highlight where spending is concentrated, for example, whether one gender favours a particular product category more than the other. 


## 2. Bike Sales & SWITCH Dataset

For these tasks, I analysed the bike sales data by country, age group and gender using a pivot table, and used the `SWITCH` function to categorise sales volume into text labels. 

### Bike Sales Pivot Table 

Before building the pivot table, I cleaned the Country column, as some entries were inconsistently capitalised (e.g. "australia" vs "Australia"). I duplicated the column, used a formula to correct the casing, then pasted the corrected values back over the original.

![Bike sales pivot table and chart](../images/pivot_sales.png)

*Pivot table and stacked column chart showing Sum of Order Quantity by Country, Age Group, and Customer Gender.*

**Findings**<br>
- The United States is the most profitable market overall. Within it, the Adult age group generates the highest sales, and female customers outperform male customers by 38%.<br>
- Australia and the United Kindgom  are the only countries with sales across all market categories, with Australia having 350% more customers than the UK.<br> 
- Germany's customers are exclusively Adults, with females making up 61% of that group.<br> 
- Canada is the lowest performing market, with customers only in the Young Adult group, suggesting its marketing or product positioning may need further investigation. 

### SWITCH function task

![SWITCH formula categorising sales volume](../images/switch_task.png)

*Sales Volume By Text column using `=SWITCH(TRUE, C2>600,"High", C2>=300,"Medium","Low")`.*

Used `SWITCH` combined with `TRUE` to categorise each sale's volume into High, Medium, 
or Low bands, rather than nesting multiple `IF` statements. `SWITCH(TRUE, ...)` checks 
each condition in order and returns the label for the first one that matches, it's a 
cleaner way to handle multiple thresholds in one formula.

---

## 3. Bike Sales Visualisations

Built three chart types in Excel a line, a stacked column, and pie, to visualise bike sales revenue and profit trends over time, by country, and by age group.

### Revenue vs. Profit by year

![Revenue vs profits line chart](../images/revenue_vs_profits.png)

*Line chart comparing Annual Profit and Annual Revenue from 2017–2021.*

For this task I built a line chart to track how revenue and profit changed year on year. Revenue and profit both trend upward overall, but the gap between them widens over time, revenue grows faster than profit, particularly from 2019 onwards.

### Product revenue by country

![Product revenue by country stacked column chart](../images/product_rev_by_country.png)

*Stacked column chart showing revenue by product category (Accessories, Bikes, Clothing) across six countries.*

I used a stacked column chart to compare revenue by product category across countries in one view. Bikes are clearly the dominant product across every country, and the United States generates by far the most total revenue, more than double the next-highest country (Australia).

### Revenue by age group

![Revenue comparison by age group pie chart](../images/rev_by_age_group.png)

*Pie chart showing revenue share by age group, with category names and percentages displayed.*

I used a pie chart to show revenue split by age group as a proportion of the whole. Adults (35–64) account for half of all revenue, followed by Young Adults (25–34) at 36%, while Seniors make up a negligible share, useful for seeing at a glance which age group to prioritise for marketing.



---

## 4. Student Records Table

For this task, I analysed a small classroom dataset. I calculated averages and the 
highest score, sorted and filtered for top performers, and highlighted the results 
using conditional formatting. As a stretch task, I extended the analysis by identifying 
additional meaningful insights that could be drawn from the table.

![Average formula](../images/average.png)

*Average column filled in using `=AVERAGE(B2:D2)` for each student.*

Calculated each student's average across English, Mathematics, and Science.

![Highest score formula](../images/student_highestscore.png)

*Highest score column using `=MAX(B3,C3,D3)`.*

Used `MAX` to pull out each student's single highest subject score, useful for quickly 
identifying a student's strongest subject without scanning all three columns individually.

![Sorted table with conditional formatting](../images/conditional_formatting.png)

*Table sorted by Highest Score (descending), with a colour scale applied to the Average 
column using green for higher averages, red for lower.*

Sorted the table to surface top performers by highest score, then applied conditional 
formatting to the Average column so strong and weak performers stand out visually 
without needing to read every number individually.

### Stretch task

![Stretch task with support columns](../images/stretch_task.png)

*Added three columns: Support Required, Subject in Need of Support, and Number of 
Subjects Passed.*

**Support Required**:<br> `=IF(E2<70,"Yes","No")`, flags students whose average fell 
below 70. A student sitting exactly at 70 still gets "No", since 70 is the pass 
threshold rather than a fail point.<br>
**Subject in Need of Support**:<br> `=IFS(B2=MIN($B2:$D2),"English",C2=MIN($B2:$D2),"Mathematics",D2=MIN($B2:$D2),"Science")`, identifies which of the three subjects is each student's weakest by checking which 
score matches the row's minimum.<br>
**Number of Subjects Passed**:<br> `=COUNTIF(B2:D2,">=70")`, counts how many subjects 
each student scored 70 or above in, using 70 as the pass threshold.

This kind of flagging is useful in a classroom setting because it turns raw scores into 
something actionable, helping a teacher quickly spot who needs help and in which 
subject, rather than manually reviewing every row.
