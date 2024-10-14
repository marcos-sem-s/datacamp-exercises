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

## Where
You won't usually want to retrieve every row in your database. You'll have specific information you need in order to answer questions from your boss or colleagues.

The `WHERE` clause is essential for selecting, updating (and deleting!) data from your tables. You'll continue working with the `grid` dataset for this exercise.

**Instructions**

- Select the `description` and `event_year` columns.
- Return rows `WHERE` the `description` is `'Vandalism'`.

``` sql
SELECT 
  description, 
  event_year
FROM 
  grid 
WHERE
  description = 'Vandalism';
```

<br>

## Where again
When filtering strings, you need to wrap your value in 'single quotes', as you did in the previous exercise. You don't need to do this for numeric values, but you DO need to use single quotes for date columns.

In this course, dates are always represented in the `YYYY-MM-DD` format (Year-Month-Day), which is the default in Microsoft SQL Server.

**Instructions**

1. Select the `nerc_region` and `demand_loss_mw` columns, limiting the results to those where `affected_customers` is greater than or equal to 500000 (500,000).

``` sql
SELECT 
  nerc_region, 
  demand_loss_mw
FROM 
  grid 
WHERE 
  affected_customers >= 500000;
```

2. Select the `description` and `affected_customers` columns, returning records where the `event_date` was the 22nd December, 2013.

``` sql
SELECT 
  description, 
  affected_customers
FROM 
  grid   
WHERE 
  event_date = '2013-12-22';
```

3. Limit the results to those where the `affected_customers` is BETWEEN 50000 and 150000, and order in descending order of `event_date`.

``` sql
SELECT 
  description, 
  affected_customers,
  event_date
FROM 
  grid
WHERE 
  affected_customers BETWEEN 50000
  AND 150000
ORDER BY   
  event_date DESC;
```

<br>

## Working with NULL values
A NULL value could mean 'zero' - if something doesn't happen, it can't be logged in a table. However, NULL can also mean 'unknown' or 'missing'. So consider if it is appropriate to replace them in your results. NULL values provide feedback on data quality. If you have NULL values, and you didn't expect to have any, then you have an issue with either how data is captured or how it's entered in the database.

In this exercise, you'll practice filtering for NULL values, excluding them from results, and replacing them with alternative values.

**Instructions**

1. Use a shortcut to select all columns from `grid`. Then filter the results to only include rows where `demand_loss_mw` is unknown or missing.

``` sql
SELECT 
  * 
FROM 
  grid 
WHERE 
  demand_loss_mw IS NULL;
```

2. Now filter the results to only include rows where `demand_loss_mw` is **not** unknown or missing.

``` sql
SELECT 
  * 
FROM 
  grid 
WHERE 
  demand_loss_mw IS NOT NULL;
```

<br>

## Exploring classic rock songs
It's time to rock and roll! In this set of exercises, you'll use the `songlist` table, which contains songs featured on the playlists of 25 classic rock radio stations.

First, let's get familiar with the data.

**Instructions**
- Retrieve the song, `artist`, and `release_year` columns from the `songlist` table.
- Return only rows where `release_year` is not missing or unknown.
- Order the results by `artist` and `release_year`.

``` sql
SELECT 
  song, 
  artist, 
  release_year 
FROM 
  songlist
WHERE 
  release_year IS NOT NULL
ORDER BY
  artist,
  release_year;
```

<br>

## Exploring classic rock songs - AND/OR
Having familiarized yourself with the `songlist` table, you'll now extend your `WHERE` clause from the previous exercise.

**Instructions**

1. Extend the `WHERE` clause so that the results are those with a `release_year` greater than or equal to `1980` and less than or equal to `1990`.

``` sql
SELECT 
  song, 
  artist, 
  release_year
FROM 
  songlist 
WHERE 
  -- Retrieve records greater than and including 1980
  release_year >= 1980 
  -- Replace AND with OR
  AND release_year <= 1990 
ORDER BY 
  artist, 
  release_year;
```

2. Update your query to use an `OR` instead of an `AND`.

``` sql
SELECT 
  song, 
  artist, 
  release_year
FROM 
  songlist 
WHERE 
  -- Retrieve records greater than and including 1980
  release_year >= 1980 
  -- Replace AND with OR
  OR release_year <= 1990 
ORDER BY 
  artist, 
  release_year;
```

<br>

## Using parentheses in your queries
You can use parentheses to make the intention of your code clearer. This becomes very important when using AND and OR clauses, to ensure your queries return the exact subsets you need.

**Instructions**

Select all artists beginning with `B` who released tracks in `1986`, but also retrieve any records where the `release_year` is greater than `1990`.

``` sql
SELECT 
  artist, 
  release_year, 
  song 
FROM 
  songlist 
WHERE 
  (
    artist LIKE 'B%' 
    AND release_year = 1986
  )
  OR release_year > 1990
ORDER BY 
  release_year, 
  artist, 
  song;
```
