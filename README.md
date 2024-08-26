## Description
This project demonstrates the use of different types of SQL joins (LEFT JOIN, RIGHT JOIN, and FULL JOIN) using the dvdrental sample database. The goal is to retrieve specific data by combining information from multiple related tables (city, country, customer, payment, and rental).

## SQL Queries
# LEFT JOIN: City and Country Names

This query retrieves the city names from the city table and their corresponding country names from the country table. It includes all cities, even if they do not have a corresponding country entry.

```sql

SELECT city, country 
FROM city
LEFT JOIN country 
ON city.country_id = country.country_id;
```
# RIGHT JOIN: Payment ID with Customer Names

This query retrieves the payment_id from the payment table and the first and last names of customers from the customer table. It includes all customers, even if they have not made any payments.

``` sql

SELECT payment_id, first_name, last_name 
FROM payment 
RIGHT JOIN customer 
ON customer.customer_id = payment.customer_id;
```
# FULL JOIN: Rental ID with Customer Names

This query retrieves the rental_id from the rental table and the first and last names of customers from the customer table. It includes all customers and all rentals, even if there are no matches between them.

```sql

SELECT rental_id, customer.customer_id, first_name, last_name 
FROM customer
FULL JOIN rental 
ON rental.customer_id = customer.customer_id;
```
# Use Case
LEFT JOIN: Useful when you want to retrieve all records from the left table (city) and the matched records from the right table (country), including those that do not have a match.

RIGHT JOIN: Useful when you want to retrieve all records from the right table (customer) and the matched records from the left table (payment), including those that do not have a match.

FULL JOIN: Useful when you want to retrieve all records when there is a match in either the left (customer) or right (rental) table, including those that do not have a match.

# Conclusion
These examples illustrate the differences between LEFT JOIN, RIGHT JOIN, and FULL JOIN in SQL, helping to understand how to retrieve related data across multiple tables depending on the specific requirements of your query.
