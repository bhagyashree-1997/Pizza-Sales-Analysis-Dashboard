# 🍕 PizzaHut Sales Data Analysis using SQL

## 📊 Project Overview

This SQL-based project explores and analyzes a fictional PizzaHut sales dataset to extract key business insights, improve operations, and understand customer preferences. The analysis is done using structured SQL queries involving subqueries, joins, DDL/DML, and views.

---

## 🎯 Objectives

- Design a relational schema using ER modeling.
- Create and manage tables using **DDL**.
- Modify and populate data using **DML** operations.
- Retrieve insights through complex SQL queries.
- Generate views and analyze ordering patterns.
- Optimize menu and pricing strategies based on insights.

---

## 🗃️ Dataset Details

### 📌 Tables Used:

- **ORDERS** – Stores order-level information  
- **ORDERS_DETAIL** – Itemized detail of pizzas in each order  
- **PIZZAS** – Contains pizza size and price  
- **PIZZA_TYPES** – Defines pizza categories and names

---

## 🧾 Queries & Analysis Performed

| 🔢 Query No. | 🔍 Analysis Title                                              |
|-------------|----------------------------------------------------------------|
| #1          | Create table for seasonal pizzas (DDL)                         |
| #2          | Add a new pizza type to menu (DML)                             |
| #3          | Retrieve total number of orders                                |
| #4          | Create view excluding size 'S' pizzas                          |
| #5          | Find the most expensive pizza (Subquery)                       |
| #6          | Find the least expensive pizza (Subquery)                      |
| #7          | Calculate average price of all pizzas                          |
| #8          | Count unique pizza categories                                  |
| #9          | Show category-wise pizza distribution                          |
| #10         | Analyze order distribution by hour                             |
| #11         | Identify most common pizza size                                |
| #12         | Calculate total revenue from pizza sales (Join)                |
| #13         | Top 3 most ordered pizza types based on revenue (Join + Sort)  |

---

## 🛠 Tools & Technologies Used

- **SQL (Structured Query Language)**
- **MySQL / PostgreSQL** (Database engine independent)
- **ER Modeling Tools** (for schema/ER diagram)
- **Relational DBMS Concepts**: Joins, Views, Subqueries, DDL, DML

---

## 📌 Project Accomplishments

- ✅ Designed an ER diagram and normalized schema.
- ✅ Created and connected multiple tables representing a restaurant system.
- ✅ Used SQL queries to extract actionable insights from sales data.
- ✅ Created views for filtered insights.
- ✅ Identified best-selling pizza types and their revenue contribution.
- ✅ Analyzed patterns in ordering time and preferences by pizza size.
- ✅ Recommended data-driven improvements for menu, pricing, and operations.

---

## 📁 Files Included

- `PizzaHut_SQL_Project.sql` – SQL script with all queries  
- `SQL Project.pptx` – Presentation slides  
- `README.md` – This documentation file  

---

## 🚀 Future Improvements

- Add triggers for inventory alerts on low stock.
- Include customer demographics for better targeting.
- Build Power BI/Tableau dashboards for visualization.
- Automate daily sales reporting with scheduled views.

---

## 📧 Contact

For queries or collaborations:  
**Author**: *Bhagyashree Murkute*  
**Email**: [bhagyashreem03@gmail.com]

---

⭐ *If you found this helpful, consider giving it a star or sharing with others!*

---

## 🔍 Sample Insight

> **Top 3 Most Ordered Pizza Types by Revenue**
```sql
SELECT pt.name AS Pizza_Name, 
       SUM(od.quantity * p.price) AS Total_Revenue
FROM orders_detail od
JOIN pizzas p ON od.pizza_id = p.pizza_id
JOIN pizza_types pt ON p.pizza_type_id = pt.pizza_type_id
GROUP BY pt.name
ORDER BY Total_Revenue DESC
LIMIT 3;
