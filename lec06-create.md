## Primary Key& Foreign Key
1. Primary: is a column or group of columns used to identify a row uniquely in a table
2. Foreign: is a field or a group of field that used to identify a row in another table

## Constraints
1. logic: rules that are enforced on data columns on table to prevent invalid data from entering the column
* Two Types:
    * column constraints: apply to only in a column
    * table constraints: apply to a entire table
* Common constraints:
    * NOT NULL: 
    * UNIQUE: 
    * Primary Key 
    * Foreign Key

## Create statement
1. 
```roomsql
CREATE TABLE account(
NAME TYPE CONSTRAINT,
user_id SERIAL PRIMARY KEY,
username VARCHAR(50) UNIQUE NOT NULL,
password VARCHAR(50) NOT NULL
)
```
```roomsql
CREATE TABLE account_job(
user_id INTEGER REFERENCES account(user_id)
/*SERIAL should only be used in primary key*/
)
```
2. Adding Check constraint: allows us to create more customized constraints
```roomsql
CREATE TABLE account(
user_id SERIAL PRIMARY KEY,
username VARCHAR(50) UNIQUE NOT NULL,
password VARCHAR(50) NOT NULL,
birthday DATE CHECK (birthday > '1990-01-01'),
hire_date DATE CHECK (hire_date > birthday),
salary INTEGER CHECK (salary > 0)
)
```


## Insert statement
1. logic: it allows you to add row to a table
2. 
```roomsql
INSERT INTO account(user_id, username, password)
VALUES
('123', 'jose', '56789')
```

## UPDATE statement
1. logic: It allows you for the changing values of a column to a table
```roomsql
UPDATE table_1
SET col_1 = value_1,
    col_2 = value_2,
WHERE conditions;
/* Without where, it will change everthing in a column */
```
2. Update Join: using another table's value
```roomsql
UPDATE table_1
SET col_1 = table_b.col_2,
FROM table_b
WHERE conditions;
```
3. Update + return
```roomsql
UPDATE table_1
SET col_1 = value_1,
    col_2 = value_2
RETURNING account_id, last_login;
```

## DELETE statement
1. logic: we can use delete clause to remove rows from a table
```roomsql
DELETE FROM table_1
WHERE condition
```
```roomsql
DELETE FROM table_1
USING table_2
WHERE table_1.id = table_2.id
RETURNING ..., ...
```

## ALTER statement
* logic: it allows for changes to an existing table structure
  * rename table
  * add, drop, rename column
  * change column's data type
  * set default value for a column
  * add CHECK constraints
```roomsql

```
```roomsql
ALTER TABLE new_info
ALTER COLUMN person DROP NOT NULL
```

## DROP clause
1. logic: allows for the complete removal of a column in a table
```roomsql
ALTER TABLE new_info
DROP COLUMN col_1,
DROP COLUMN col_2 
```

