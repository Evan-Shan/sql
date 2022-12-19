## 1.1: SELECT statement
1. logic: first check which table then check which column;
```roomsql
SELECT col_1 FROM table_1;
```
```roomsql
SELECT col_1, col_2 FROM table_3;
```
```roomsql
SELECT * FROM table_3;
```
2. how to check what are your tables:
    * go to schemas -> check 'table';

## 1.2: SELECT DISTINCT statement
1. logic: select the distinct(unique) entries from the column(both ways are fine);
```roomsql
SELECT DISTINCT release_year FROM film;
```
```roomsql
SELECT DISTINCT(release_year) FROM film;
```

## 2.1: COUNT statement
1. logic: return the number of rows in a column;
2. All should return the same, because every column has the same number of rows;
3. Must have a parenthesis ();
```roomsql
SELECT COUNT(*) From table_1;
```
```roomsql
SELECT COUNT(col_1) From table_1;
```
```roomsql
SELECT COUNT(col_3) From table_1;
```

## 2.2: COUNT DISTINCT statement
1. logic: return the number of rows for distinct entries in a column/number of distinct elements in a column;
2. The syntax informs us we are calling count on the result of distinct;
```roomsql
SELECT COUNT (DISTINCT(col_1)) From table_1;
```

## 3.1: ORDER BY statement
1. logic: you can sort the rows on a column value; in ascending or descending order;
2. It will fist sort the rows based on company, then sort it on sales;
```roomsql
SELECT company, sales, name FROM table_1
ORDER BY company ASC, sales DESC;
```

## 3.2: LIMIT statement
1. logic: it allows us to limit the rows that get returned; usually in combo with ORDER BY
2. It is the last command to be executed;
```roomsql
SELECT * FROM table_1
ORDER BY payment_due DESC
LIMIT 5;
```
