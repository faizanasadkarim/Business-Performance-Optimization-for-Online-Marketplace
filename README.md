Marketing Analytics for E-commerce Company
This project focuses on the analysis of marketing data from an e-commerce company, with the goal of gaining insights into various aspects of the business. The dataset spans from September 2016 to October 2018, and includes detailed information on customers, sellers, products, orders, and payment behavior. The business objective is to answer critical business questions, segment customers and sellers, understand sales trends, and provide recommendations based on data-driven insights.

Available Data
The dataset includes the following tables:

Customers: Information about customers such as demographics, contact details, etc.
Sellers: Information about sellers, including seller ID, name, etc.
Products: Product-level information including IDs, categories, pricing, etc.
Orders: Information about orders such as product IDs, order dates, status, etc.
Order_Items: Information at the order-item level (e.g., quantity, product details).
Order_Payments: Payment details for each order.
Order_Review_Ratings: Customer ratings for products at the order level.
Geo-Location: Location details such as customer or seller addresses, states, cities, etc.
Data Model


Business Objective
The primary goal is to address the following sample business questions and perform detailed analysis. You are encouraged to add further analyses as you explore the data.

1. Detailed Exploratory Analysis
High-Level Metrics: Calculate total revenue, quantity sold, total products, total categories, total sellers, total locations, total channels, total payment methods, etc.

Customer Acquisition: Determine how many new customers were acquired each month.

Customer Retention: Analyze customer retention on a month-to-month basis.

Revenue Analysis: Evaluate the revenues from existing vs. new customers on a month-to-month basis.

Sales Trends: Analyze trends and seasonality of sales, quantity sold by category, location, month, week, day, time, channel, and payment method.

Popular Products: Identify the most popular products by month, seller, state, and category.

Popular Categories: Identify popular categories by state and month.

Top 10 Most Expensive Products: List the top 10 most expensive products sorted by price.

2. Customer/Seller Segmentation
Customer Segmentation: Divide customers into groups based on revenue generated.

Seller Segmentation: Divide sellers into groups based on revenue generated.

3. Cross-Selling Analysis
Product Combinations: Identify the top 10 combinations of products that are commonly bought together in each transaction (combinations of 2 or 3 products).
4. Payment Behavior
Payment Methods: Understand how customers are paying for their orders.

Most Popular Payment Channels: Identify which payment channels are used by most customers.

5. Customer Satisfaction Analysis
Top Rated Categories: Identify which categories are the highest and lowest rated by customers.

Top Rated Products: Identify which products are the highest and lowest rated.

Average Rating Analysis: Calculate the average rating by location, seller, product, category, and month.

Getting Started
To run this project locally, follow the steps below:

Prerequisites
Ensure you have the following installed:

Python 3.x
Jupyter Notebook (or any Python IDE)
Required libraries (listed below)
Installation
Clone the repository to your local machine:

bash
Copy code
git clone https://github.com/your-username/Marketing-Analytics-python-ecommerce-company.git
cd Marketing-Analytics-python-ecommerce-company
Install the required Python libraries:

bash
Copy code
pip install -r requirements.txt
Data Setup
Download the dataset (CSV or SQL dump) and place it in the data/ folder in the project directory.
Ensure the database connections (if applicable) are correctly set up in your environment.
Running the Analysis
Open exploratory_analysis.ipynb (or your preferred notebook) and start exploring the data.
Run through the cells to calculate metrics, segment customers/sellers, and generate insights.
Files
exploratory_analysis.ipynb: Jupyter notebook for performing detailed analysis.
customer_segmentation.py: Python script for customer segmentation based on revenue.
seller_segmentation.py: Python script for seller segmentation based on revenue.
cross_selling.py: Python script for identifying product combinations.
payment_behavior.py: Python script to analyze payment methods.
ratings_analysis.py: Python script to analyze customer ratings.
Example Use Case
If you're interested in understanding customer retention, you can load the data, group it by customer, and then calculate the retention rate by comparing the number of returning customers month-over-month.

python
Copy code
import pandas as pd

# Load data
orders = pd.read_csv('data/orders.csv')
customers = pd.read_csv('data/customers.csv')

# Example: Customer Retention - Month over month
orders['order_month'] = pd.to_datetime(orders['order_date']).dt.to_period('M')
customer_retention = orders.groupby(['order_month', 'customer_id']).size().unstack(fill_value=0)

# Count number of returning customers per month
customer_retention = customer_retention[customer_retention > 0].count(axis=1)
print(customer_retention)
Contributing
Contributions are welcome! Feel free to fork the repository and submit pull requests.

Fork the repo
Create a new branch (git checkout -b feature-name)
Make your changes
Commit your changes (git commit -am 'Add feature')
Push to the branch (git push origin feature-name)
Create a new Pull Request
License
This project is licensed under the MIT License - see the LICENSE file for details.
