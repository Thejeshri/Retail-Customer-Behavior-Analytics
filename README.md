Retail Customer Shopping Behavior

By Thejeshri Rajesh

To do: Analysis of customer shopping behavior using transactional data from 3,900 purchases
across various product categories. The goal is to uncover insights into spending patterns,
customer segments, product preferences, and subscription behavior to guide strategic business
decisions.

Business Problem:
A leading retail company wants to better understand its customers' shopping behavior in order to
improve sales, customer satisfaction, and long-term loyalty. Management has noticed changes in
purchasing patterns across demographics, product categories, and sales channels, and wants to
know which factors — discounts, reviews, seasons, payment preferences — drive consumer
decisions and repeat purchases.

Question we're trying to answer!
How can the company leverage consumer shopping data to identify trends, improve customer
engagement, and optimize marketing and product strategies?

Dataset Summary:
- Rows: 3,900
- Columns: 18
- Key features:
- Customer demographics (Age, Gender, Location, Subscription Status)
- Purchase details (Item Purchased, Category, Purchase Amount, Season, Size,
Color)
- Shopping behavior (Discount Applied, Promo Code Used, Previous Purchases,
Frequency of Purchases, Review Rating, Shipping Type)
- Missing data: 37 values in the Review Rating column
- 
Exploratory Data Analysis (Python):
Data preparation and cleaning was done in Python:
- Data loading: imported the dataset with pandas
- Initial exploration: used df.info() to check structure and .describe() for summary stats
- Missing data handling: checked for nulls and imputed the missing Review Rating
values using the median rating of each product category
- Column standardization: renamed columns to snake_case for readability
- Feature engineering:
- age_group column, created by binning customer ages into Young Adult / Adult /
Middle-aged / Senior
- purchase_frequency_days, created by mapping the purchase frequency data to a
number of days
- Data consistency check: verified discount_applied and promo_code_used were identical
for every row, and dropped promo_code_used
- Database integration: connected the Python script to PostgreSQL and loaded the
cleaned dataframe in for SQL analysis

SQL Analysis:
Ran structured queries in PostgreSQL to answer 10 business questions, with results below.
1. Revenue by gender Male customers generated $157,890 in revenue vs. $75,191 for female
customers.
2. High-spending discount users 839 customers used a discount but still spent above the overall
average purchase amount.
3. Top 5 products by average review rating Gloves (3.86), Sandals (3.84), Boots (3.82), Hat
(3.80), Skirt (3.78).
4. Standard vs. Express shipping Average purchase amount is $58.46 for Standard shipping
and $60.48 for Express.
5. Subscribers vs. non-subscribers 1,053 subscribers, avg spend $59.49, total revenue $62,645.
2,847 non-subscribers, avg spend $59.87, total revenue $170,436.
6. Products most dependent on discounts Hat (50%), Sneakers (49.66%), Coat (49.07%),
Sweater (48.17%), Pants (47.37%) of purchases involved a discount.
7. Customer segmentation (New / Returning / Loyal) Loyal: 3,116. Returning: 701. New: 83.
8. Top 3 products per category Accessories — Jewelry, Sunglasses, Belt. Clothing — Blouse,
Pants, Shirt. Footwear — Sandals, Shoes, Sneakers. Outerwear — Jacket, Coat.
9. Repeat buyers and subscriptions Of customers with more than 5 previous purchases, 2,518
are non-subscribers and 958 are subscribers.
10. Revenue by age group Young Adult ($62,143), Middle-aged ($59,197), Adult ($55,978),
Senior ($55,763).
Full queries in the SQL Queries document inside the repository

Dashboard (Power BI):
Built an interactive dashboard to present the insights visually — filters for subscription status,
gender, category, and shipping type, with visuals for number of customers, average purchase
amount, average review rating, subscriber split, revenue and sales by category, and revenue and
sales by age group.
Business Recommendations
- Boost subscriptions — promote exclusive benefits for subscribers, since non-subscribers
currently drive far more total revenue
- Customer loyalty programs — reward repeat buyers to move them into the "Loyal"
segment
- Review discount policy — several products are discounted on close to half of all
purchases, so balance sales boosts with margin control
- Product positioning — highlight top-rated and best-selling products in campaigns
- Targeted marketing — focus efforts on high-revenue age groups and express-shipping
users
Tools Used:
- Python (pandas, SQLAlchemy, psycopg2)
- PostgreSQL
- Power BI
- 
Author:
Thejeshri Rajesh
LinkedIn: www.linkedin.com/in/thejeshrirajesh
