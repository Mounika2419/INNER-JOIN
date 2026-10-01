Suppose you want to know:

Which customer made which order and what is the order amount?

The customer name is in the customer table, while the order amount is in the orders table.

So we need to JOIN the two tables.
Types of SQL JOINs

The main JOIN types are:

INNER JOIN
LEFT JOIN
RIGHT JOIN
FULL OUTER JOIN
CROSS JOIN
SELF JOIN

The most commonly used ones for beginners are INNER JOIN, LEFT JOIN, and RIGHT JOIN.

1. INNER JOIN

INNER JOIN returns only the rows that have matching values in both tables.

Syntax:

SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;

Your query:

SELECT customer.cid, customer.cname, orders.amount
FROM customer
INNER JOIN orders
ON customer.cid = orders.customers;
How it works

It compares:

customer.cid = orders.customers

Let's check each order:

Customer ID	Customer Name	Order Customer ID	Match?
1	anil	—	❌
2	raju	2	✅
3	ravi	3	✅
4	ramu	4	✅
5	harsha	—	❌

Your orders table contains customer IDs 20, 3, 7, 4, 2.

Only 2, 3, and 4 exist in the customer table.

Therefore, the INNER JOIN result is:

cid	cname	amount
3	ravi	220000.00
4	ramu	660000.00
2	raju	750000.00

Notice:

anil is not shown because there is no order with customer ID 1.
harsha is not shown because there is no order with customer ID 5.
Orders with customer IDs 20 and 7 don't have matching customers, so they are also not shown.
