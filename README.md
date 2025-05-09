Pizza Sales Analysis using SQL

Welcome to the Pizza Sales Analysis Project! This project explores key sales insights from a fictional pizza restaurant using SQL queries on structured data. It's designed to answer business questions around revenue, customer behavior, and product performance.

📁 Project Structure
The project is built using SQL queries to analyze a pizza sales database and answer the following questions:

🔍 Business Questions Answered
Retrieve the total number of orders placed
Calculate the total revenue generated from pizza sales
Identify the highest-priced pizza
Find the total quantity of each pizza category ordered
Determine the distribution of orders by hour of the day
Find the category-wise distribution of pizzas
Group orders by date and calculate the average number of pizzas ordered per day
Determine the top 3 most ordered pizza types based on revenue
🧠 SQL Queries
1. Total Number of Orders
'''sql
SELECT COUNT(DISTINCT order_id) AS total_orders FROM orders;
'''

3. Total Revenue Generated
'''sql
SELECT SUM(quantity * price) AS total_revenue FROM order_details JOIN pizzas ON order_details.pizza_id = pizzas.pizza_id;
'''

5. Highest-Priced Pizza
''' sql SELECT name, price FROM pizzas ORDER BY price DESC LIMIT 1; '''

6. Quantity of Each Pizza Category Ordered
''' sql SELECT category, SUM(quantity) AS total_quantity FROM order_details JOIN pizzas ON order_details.pizza_id = pizzas.pizza_id JOIN pizza_types ON pizzas.pizza_type_id = pizza_types.pizza_type_id GROUP BY category; '''

7. Order Distribution by Hour
''' sql SELECT EXTRACT(HOUR FROM order_time) AS hour, COUNT(*) AS order_count FROM orders GROUP BY hour ORDER BY hour; '''

8. Category-Wise Pizza Distribution
''' sql SELECT category, COUNT(DISTINCT pizzas.pizza_id) AS total_pizzas FROM pizzas JOIN pizza_types ON pizzas.pizza_type_id = pizza_types.pizza_type_id GROUP BY category; '''

9. Average Number of Pizzas Ordered Per Day
''' sql SELECT order_date, AVG(quantity) AS avg_pizzas FROM order_details JOIN orders ON order_details.order_id = orders.order_id GROUP BY order_date; '''

10. Top 3 Most Ordered Pizza Types (by Revenue)
''' sql SELECT name, SUM(quantity * price) AS revenue FROM order_details JOIN pizzas ON order_details.pizza_id = pizzas.pizza_id GROUP BY name ORDER BY revenue DESC LIMIT 3; '''

🛠 Tools Used
SQL (MySQL)

Relational Database Schema

Pizza Sales Dataset

👩‍💻 Author
Nikita Dhawale

📌 Conclusion
This project highlights how SQL can be used to perform business analysis and make data-driven decisions in the food and beverage industry.
