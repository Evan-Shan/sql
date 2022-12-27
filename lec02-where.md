## 1.1: WHERE statement
1. logic: It allows us to specify the conditions for rows to be returned;
2. Operators:
    * Comparison: >, < >=, <=, =, !=;
    * Logical: AND, OR, NOT;
```roomsql
SELECT name, choice FROM table_1
WHERE name = 'david' AND choice = 'red';
```
## 1.2: BETWEEN statement
1. logic: is the same as saying: value >= low AND value <= high;
```roomsql
SELECT * FROM table_1
WHERE value BETWEEN 8 AND 9;
```
```roomsql
SELECT * FROM table_1
WHERE value NOT BETWEEN 8 AND 9;
```

## 1.3: IN statement
1. logic: can check if a value is in a list of multiple options;
```roomsql
SELECT * FROM table_1
WHERE value IN (0.99, 0.98, 1.99);
```
```roomsql
SELECT * FROM table_1
WHERE value NOT IN (0.99, 0.98, 1.99);
```

## 1.4: LIKE/ILIKE statement
1. logic: it allows us to perform pattern matching; LIKE - case sensitive; ILIKE - case insensitive;
   * Percent: %
      * match any sequence of characters;
   * Underscore: -
      * match any single character;
```roomsql
SELECT * FROM table_1
WHERE value LIKE 'VERSION__' AND last_name LIKE '_her%'AND title LIKE '%eyr%';
```