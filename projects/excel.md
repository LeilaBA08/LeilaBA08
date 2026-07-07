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

**Commission Amount**:<br>`=I3*$P$8`, Total Sales x a fixed 1.5% rate. The `$` locks 
the reference so it stays fixed when copied down each row, rather than shifting to a different cell each time.

**Commission Total**:<br>`=SUM(range)` shows the total commission earned across all filtered sales, providing an at-a-glance figure for total earnings.

**Average Commission**:<br> `=AVERAGE(range)` shows the typical commission per sale, which is more useful than the total when the number of sales varies. 

## 2. Bike Sales & SWITCH Dataset

Brief intro: what the dataset was, and what Task 1 vs Task 2 (SWITCH) each involved.

**What I did:**
- Screenshot – [caption/explanation]

**Formulas/functions used:**
- `SWITCH()` – why I used it, what it solved

**What I learned / result:**
- ...

---

## 3. Bike Sales Visualisations

Brief intro: what this task built on from the previous one, and what the visualisation goal was.

**What I did:**
- Screenshot – [caption/explanation]

**Chart types / features used:**
- ...

**What I learned / result:**
- ...

---

## 4. Student Records Table

Brief intro: what the dataset was and what the task involved.

**What I did:**
- Screenshot – [caption/explanation]

**Formulas/functions used:**
- ...

**What I learned / result:**
- ...
