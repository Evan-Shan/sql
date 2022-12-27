## 1.1: Aggregation functions
1. logic: function that takes in multiple inputs and return a single output;
```roomsql
SELECT AVG(col_1), MAX(col_2), SUM(col_3) FROM table_1;
```

## 1.2: GROUP BY statement
1. logic: groups rows that have the same values into summary rows; 
2. It is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.
    * it will first split columns based on the group by column;
    * select must have aggregation functions or be in the group by statement; 
```roomsql
/*customer_id and staff_id must appear in group by statement
it means to show the customer_id and its corresponding staff_id*/
SELECT customer_id, staff_id FROM payment
GROUP BY customer_id, staff_id
Order by customer_id
```
```roomsql
SELECT customer_id, staff_id, SUM(amount) FROM payment
GROUP BY customer_id, staff_id
Order by SUM(amount)
```

## 1.3: HAVING statement - GROUP BY version 'WHERE'
1. logic: we can not use 'where' to filter aggregation function because 'select' execute after 'where';
2. Having is similar to the 'group by' version 'where'; In which 'where' filter based on every row, whereas 'having' based on group
```roomsql
SELECT customer_id, SUM(amount) 
/* 1. Preliminary filtering/putting restrictions on certain rows */
FROM payment
WHERE customer_id NOT IN (1, 10, 100)
/* 2. Deep filtering */
GROUP BY customer_id
HAVING SUM(amount) > 150
```