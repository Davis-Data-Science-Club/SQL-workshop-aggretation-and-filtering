# Quick SQL Syntax Introduction

Most queries will be of the form:

```SQL
SELECT *
FROM table
WHERE clause
ORDER BY column DESC
LIMIT 10;
```

## Select

What data do you want to recieve back?

| Selector | Description |
|----------|-------------|
| `*`      | Selects all rows and columns from query result|
| `column_name` | Selects all rows from specific columns |
| `aggregation` | Sum(), AVG(), COUNT() |
| `DISTINCT` | Returns one of each distinct value in the column |

## From

The table that you are trying to query from.

```SQL
SELECT *
FROM data_base.table_name
```

## Where

| Operation | Description |
|-----------|-------------|
| `=`      | Checks for equivalence |
| `>, <` | Checks for inequality |
| `ilike/like` | String similarity (not in all SQL flavors) |

```SQL
SELECT *
FROM data_base.table_name
WHERE column_name = column_value;
```

## GROUP BY

Only displays each value in the column once, then you're able to pair with a
COUNT() or other aggregation function on all the rows with that column value.

```SQL
SELECT column_name, avg(column_name)
FROM data_base.table_name
GROUP BY column_name;
```

## ORDER BY

Tells SQL what column and direction to the output data by.

| Option | Description |
|--------|-------------|
| `column_name` | Tells which column to order by |
| `ASC` | Orders data from smallest to largest |
| `DESC` | Orders data from largest to smallest |

```SQL
SELECT column_name
FROM data_base.table_name
ORDER BY column_name DESC;
```

## LIMIT

Tells SQL to only return a limited number of rows.

```SQL
SELECT *
FROM data_base.table_name
LIMIT 10;
```
