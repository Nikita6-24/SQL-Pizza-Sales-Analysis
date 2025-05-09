# 🍕 SQL Pizza Sales Analysis

This project performs an in-depth sales analysis using SQL on a fictional pizza shop's transactional data. It highlights business insights such as total revenue, top-selling pizzas, and customer ordering behavior.

## 📊 Project Objectives

- Calculate key metrics like revenue, average order value, and total pizzas sold.
- Identify best and worst-performing pizza types and sizes.
- Analyze peak order times and daily sales trends.

## 🧾 Dataset Structure

The database contains the following tables:

- `orders` – Tracks order timestamps.
- `order_details` – Contains quantity and pizza ID per order.
- `pizzas` – Links pizza IDs to type, size, and price.
- `pizza_types` – Describes pizza names and categories.
- `pizza_sizes` – Includes size variations (S, M, L, XL, XXL).

---

## 🔍 Key SQL Queries

### 1. 💵 Total Revenue

```sql
SELECT ROUND(SUM(od.quantity * p.price), 2) AS total_revenue
FROM order_details od
JOIN pizzas p ON od.pizza_id = p.pizza_id;
