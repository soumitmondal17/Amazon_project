---
# Amazon_project
### **Difficulty level : Advanced**
---
## Project overview

I have worked on analysing dataset over multiple sales records from an Amazon-like e-commerce platform. This project involves extensive querying of customer behaviour, product performance, and sales trends using PostgreSQL. Through this project I have tackled various SQL problems, including revenue analysis, customer segmentation, and inventory management. 

This project also focused on solving real world business scenarios using standard procedure/structured queries. 
An ERD diagram is included to visually represent the database schema and relationship between tables. 

---
## **Database setup and Design**
- The database contains 8 tables: 'customers','sellers','products','orders', 'order_items', 'inventory', 'payments' and 'shippings'.
- These tables are designed with primary keys, foreign key constraints and proper indexing to maintain integrety and optimize query perfomracne.

## **Objective**
The primary object of this project is to showcase SQL profficiency through complex queries that address real-world e-commerce business challenges. The analysis covers various business operations including:
- Customer behavior
- Sales trend
- Inventory management
- Payment and shipping analysis
- Revenue analysis based on product categories.

- ## **Identyfying business problems**
- Top selling products 
Query the top 10 selling products by total sales value. 
Challange: Include Product name, total quantity sold, and total sales value.
```sql
select p.product_name, sum (oi.quantity) as total_quantity,
	sum (oi.total_sales) as total_sales 
from products p
join order_items oi on p.product_id=oi.product_id
group by p.product_name
order by total_sales desc;
```sql
