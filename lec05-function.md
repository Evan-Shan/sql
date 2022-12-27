## TIME
```roomsql
TIME - contains only time
DATE - contains only date
TIMESTAMP - contains only date and time
TIMESTAMPTZ - contains only date, time and timezone
```
```roomsql
SHOW ALL
```
```roomsql
SHOW TIMEZONE
```
```roomsql
SELECT NOW()
SELECT TIMEOFDAY()
SELECT CURRENTDATE
```

## EXTRACT 
1. logic: allows you to extract a sub-component of a date form
```roomsql
SELECT EXTRACT(YEAR FROM payment_date)
FROM payment;
/* YEAR MONTH DAY WEEK QUARTER */
```
```roomsql
SELECT AGE(payment_date)
FROM payment;
```

## Mathematical Functions
1. logic: 
```roomsql
SELECT ROUND(rental_rate/replacement_cost)*100
AS percent_cost
FROM film
```

## String functions
1. logic:
```roomsql
SELECT LOWER(LEFT(first_name, 2)) || LOWER(last_name)
AS name
FROM customer;
```

## Subquery
