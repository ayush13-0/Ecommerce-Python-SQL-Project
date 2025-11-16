# 📦 E-Commerce Database Analysis Using SQL & Python
This project performs data analysis on an E-commerce database using MySQL, Python, and Pandas.
A Jupyter Notebook (Ecommerce Python+SQL Project) is used to execute SQL queries directly from Python and analyze the results.

🎯 Project Objectives
Connect Python to a MySQL E-commerce database
Run SQL queries from Jupyter Notebook
Analyze customers, orders, sales, and product category performance
Visualize insights using Matplotlib & Seaborn

🧰 Tech Stack
- Languages:
 - Python
 - SQL
- Libraries Used:
 - mysql-connector-python
 - pandas
 - matplotlib
 - seaborn
 - numpy

Database:
MySQL (Localhost)

🗄️ Database Tables Used
From the notebook, the database contains
- customers
- orders
- products
- order_items
- order_payments
- sellers
- geolocation

# 🔧 Project Workflow
1️⃣ Connect Python to MySQL
The notebook uses:

db = mysql.connector.connect(
    host='localhost',
    user='root',
    password='your_password',
    database='Ecommerce'
)
cur = db.cursor()
- Enables running SQL queries directly from Python.

2️⃣ Execute SQL Queries
- The notebook contains multiple business-focused SQL queries including:

✔ 1. List all unique customer cities
- SELECT DISTINCT customer_city FROM customers;

✔ 2. Count number of orders placed in 2017
- SELECT COUNT(order_id)
  FROM orders
  WHERE YEAR(order_purchase_timestamp) = 2017;

✔ 3. Total sales by product category
SELECT 
    UPPER(products.product_category) AS category,
    SUM(order_items.price) AS sales
FROM order_items
JOIN products
    ON order_items.product_id = products.product_id
GROUP BY category;

- Results are loaded into Pandas DataFrames for further analysis.

3️⃣ Data Visualization
Visualizations created using:
- import matplotlib.pyplot as plt
- import seaborn as sns

Examples:
- Bar chart of sales by category
- Distribution plots of sales
- Geographic insights (cities, states)

📊 Sample Analysis Performed
✔ Customer locations
✔ Order volume trends
✔ Sales by product category
✔ Seller performance
✔ Payment type distribution

📁 Project Structure:
ecommerce_sql_python_project/
│
├── data/
│   ├── raw/
│   │   ├── customers.xlsx
│   │   ├── geolocation.xlsx
│   │   ├── order_items.xlsx
│   │   ├── orders.xlsx
│   │   ├── payments.xlsx
│   │   ├── products.xlsx
│   │   ├── sellers.xlsx
│   │   ├── Ecommerce Database.sql        ← original SQL DB file
│   │
│   ├── processed/
│       ├── merged_data.csv              ← optional (if you combine tables)
│       ├── analysis_outputs.csv         ← query results saved
│
├── notebooks/
│   ├── Ecommerce Python+SQL Project.ipynb
│
├── src/
│   ├── __init__.py
│   ├── db_connection.py                 ← MySQL connection script
│   ├── sql_queries.py                   ← all SQL queries reused in notebook
│   ├── data_loader.py                   ← loading Excel files into DataFrames
│   ├── visualization.py                 ← charts (matplotlib/seaborn)
│
├── reports/
│   ├── ecommerce_analysis_report.pdf    ← export (optional)
│   ├── insights_summary.md              ← optional summary
│
├── README.md
├── requirements.txt
└── .gitignore


# ▶️ How to Run the Project
1️⃣ Install dependencies
- pip install -r requirements.txt

2️⃣ Start MySQL server locally
- Ensure the Ecommerce database is imported.

3️⃣ Run the notebook
- jupyter notebook Ecommerce Python+SQL Project

🧾 Requirements
- mysql-connector-python
- pandas
- matplotlib
- seaborn
- numpy

👨‍💻 Developed By
-- Ayush
Data Analysis | SQL | Python | Machine Learning
- 🔗GitHub: https://github.com/ayush13-0
- 🔗LinkedIn: https://www.linkedin.com/in/ayush130

