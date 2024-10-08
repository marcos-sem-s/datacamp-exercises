## Simple selections
It's time to begin writing your own queries! In this first coding exercise, you will use `SELECT` statements to retrieve columns from a database table. You'll be working with the `eurovision` table, which contains data relating to individual country performance at the Eurovision Song Contest from 1998 to 2012.

After selecting columns, you'll also practice renaming columns, and limiting the number of rows returned.

**Instructions**

1. `SELECT` the `country` column `FROM` the `eurovision` table.

``` sql
SELECT 
  country
FROM 
  eurovision;
```

2. Use `TOP` to change the existing query so that only the first `50` rows are returned.

``` sql
SELECT 
  TOP(50) country 
FROM 
  eurovision;
```

3. Return a list of unique countries using `DISTINCT`. Give the results an alias of `unique_country`.

``` sql
SELECT 
  DISTINCT country AS unique_country 
FROM 
  eurovision;
```

<br>

## More selections
Now that you've practiced how to select one column at a time, it's time to practice selecting more than one column. You'll continue working with the eurovision table.

**Instructions**

1. SELECT the country and event_year columns from the eurovision table.

``` sql
SELECT  
  country, 
  event_year
FROM
  eurovision;
```

2. Use a shortcut to amend the current query, returning ALL columns in the table.

``` sql
SELECT  
  *
FROM
  eurovision;
```

3. This time, return only half the rows using 'TOP', using the same shortcut as before to return all columns.

``` sql
SELECT 
  TOP(50) PERCENT * 
FROM 
  eurovision;
```

<br>

## Order by
In this exercise, you'll practice the use of `ORDER BY` using the `grid` dataset. It's loaded and waiting for you! It contains a subset of wider publicly available information on US power outages.

Some of the main columns include:

`description`: The reason/ cause of the outage.
`nerc_region`: The North American Electricity Reliability Corporation was formed to ensure the reliability of the grid and comprises several regional entities.
`demand_loss_mw`: How much energy was not transmitted/consumed during the outage.

**Instructions**

1. Select `description` and `event_date` from `grid`. Your query should return the first 20 rows, ordered by `event_date`.

``` sql
SELECT 
  TOP(20) description, 
  event_date
FROM 
  grid
ORDER BY 
  event_date;
```

2. Select `description`, `nerc_region`, and `event_date` from `grid`, returning the first 20 rows ordered by `nerc_region`, `affected_customers`, and `event_date` (in that order); `event_date` should be in descending order.

``` sql
SELECT 
  TOP(20) description, 
  nerc_region, 
  event_date
FROM 
  grid
ORDER BY 
  nerc_region, 
  affected_customers, 
  event_date DESC;
```

<br>

## 