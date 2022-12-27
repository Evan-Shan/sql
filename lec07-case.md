## CASE clause
1. logic: The CASE statement goes through conditions and return a value when the first condition is met (like an IF-THEN-ELSE statement)
```roomsql
SELECT OrderID, Quantity,
CASE
    WHEN Quantity > 30 THEN "The quantity is greater than 30"
    WHEN Quantity = 30 THEN "The quantity is 30"
    ELSE "The quantity is under 30"
END
FROM OrderDetails;
```
```roomsql
/*Case expression */
SELECT OrderID, Quantity,
CASE Quantity
    WHEN > 30 THEN "The quantity is greater than 30"
    WHEN = 30 THEN "The quantity is 30"
    ELSE "The quantity is under 30"
END
FROM OrderDetails;
```

## COALESCE clause
1. logic: The COALESCE() function returns the first non-null value in a list.
```roomsql
SELECT ITEMS, (price - COALESCE(discount, 0))
FROM tabel_1;
```

## CAST clause
1. logic: The CAST() function converts a value (of any type) into the specified datatype.
```roomsql
SELECT CAST("14:06:10" AS TIME);
```

## NULLIF clause
1. logic: The NULLIF() function compares two expressions and returns NULL if they are equal. Otherwise, the first expression is returned.
```roomsql
SELECT NULLIF(25, "Hello");
```