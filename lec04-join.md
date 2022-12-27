## AS clause: Alias
1. logic: it allows us to create an alias for a column or result;
2. Remember not to use it within a 'where' and 'having' statement, because 'as' executed at last;
```roomsql
SELECT amount AS rental_price
FROM customer
```
```roomsql
SELECT SUM(amount) AS rental_price
FROM customer
```
```roomsql
SELECT customer_id, SUM(amount) AS rental_price
FROM customer
GROUP BY customer_id
HAVING SUM(amount) > 100
/* can not use HAVING rental_price > 100 here*/
```

## INNER JOIN statement: 
1. logic: (items present in both tables!)selects records that have matching values in both tables.
```roomsql
/* This will have duplicate columns */ 
SELECT *
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
/* This tells the join to find the intersection based on column's name */
```
```roomsql
/* This will only include selected columns */ 
SELECT column_1, table1.name, column_2
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

## FULL OUTER JOIN
1. logic: (similar to union)returns all records when there is a match in (only one table) left (table1) or right (table2) table records.
```roomsql
SELECT * 
FROM table_a
FULL OUTER JOIN table_b
ON table_a.col_1 = table_b.col_1
WHERE table_a.id is NULL OR
table_b.id is NULL;
/* Items unique to table a and table b */
```

## LEFT OUTER JOIN
1. logic: exclusive to table_a or in the intersection of a and b, not including anything exclusive to table b;
```roomsql
SELECT * 
FROM table_a
LEFT OUTER JOIN table_b
ON table_a.col_1 = table_b.col_1
WHERE table_b.id is NULL
/* Items unique to table a not including the intersection */
```

## UNION statement
1. logic: it is used to combine to result set of two or more 'SELECT' statement;
```roomsql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```