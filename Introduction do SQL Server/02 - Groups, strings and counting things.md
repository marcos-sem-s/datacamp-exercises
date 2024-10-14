## Summing
Summing and counting are key ways of aggregating data, regardless of whether you are using a database, manipulating a spreadsheet, or using a programming language such as Python or R. Let's see how to do it in T-SQL using the `grid` table from Chapter 1.

You'll start by obtaining overall sums, focusing specifically on the `'MRO'` region.

![nerc_region map](img/image01.png)

**Instructions**

Obtain a grand total of the `demand_loss_mw` column by using the `SUM` function, and alias the `result` as `MRO_demand_loss`.
Only retrieve rows `WHERE` `demand_loss_mw` is _not_ `NULL` **and** `nerc_region` is [`'MRO'`](https://en.wikipedia.org/wiki/Midwest_Reliability_Organization).

``` sql
SELECT 
  SUM(demand_loss_mw) AS MRO_demand_loss 
FROM 
  grid 
WHERE
  demand_loss_mw IS NOT NULL
  AND
  nerc_region = 'MRO';
```

<br>

## Counting
Having explored the `'MRO'` region, let's now explore the [`'RFC'`](https://en.wikipedia.org/wiki/ReliabilityFirst) region in more detail while learning how to use the `COUNT` aggregate function.

![nerc_region map](img/image01.png)

**Instructions**

1. Return the `COUNT` of the `grid_id` column, aliasing the result as `grid_total`.

``` sql
SELECT 
  COUNT(grid_id) as grid_total 
FROM 
  grid;
```

2. Make the count more meaningful by restricting it to records where the `nerc_region` is `'RFC'`. Name the result `RFC_count`.

``` sql
SELECT 
  COUNT(grid_id) as RFC_count 
FROM 
  grid;
WHERE
  nerc_region = 'RFC'
```

<br>

## MIN, MAX and AVG
Along with summing and counting, you'll frequently need to find the minimum, maximum, and average of column values. Thankfully, T-SQL has functions you can use to make the task easier!

**Instructions**

1. Find the minimum value from the `affected_customers` column, but only for rows where `demand_loss_mw` has a value. Name the result `min_affected_customers`.

``` sql
SELECT 
  MIN(affected_customers) AS affected_customers 
FROM 
  grid
WHERE
  demand_loss_mw IS NOT NULL;
```

2. Amend the query to return the maximum value from the same column, this time aliasing as `max_affected_customers`.

``` sql
SELECT 
  MAX(affected_customers) AS max_affected_customers 
FROM 
  grid
WHERE
  demand_loss_mw IS NOT NULL;
```

3. Return the average value from the `affected_customers` column, this time aliasing as `avg_affected_customers`.

``` sql
SELECT 
  AVG(affected_customers) AS avg_affected_customers 
FROM 
  grid
WHERE
  demand_loss_mw IS NOT NULL;
```

<br>

## LEN'gth of a string
Knowing the length of a string is key to being able to manipulate it further using other functions, so what better way to start the lesson?

**Instructions**

Retrieve the length of the `description` column, returning the results as `description_length`.

``` sql
SELECT 
  LEN(description) AS description_length
FROM 
  grid;
```

<br>

## Left and right
We can retrieve portions of a string from either the start of the string, using `LEFT`, or working back from the end of the string, using `RIGHT`.

**Instructions**

1. Retrieve the first `25` characters from the `description` column in the grid table. Name the results `first_25_left`.

``` sql
SELECT 
  LEFT(description, 25) AS first_25_left 
FROM 
  grid;
```

2. Amend the query to retrieve the last `25` characters from the `description`. Name the results `last_25_right`.

``` sql
SELECT 
  RIGHT(description, 25) AS last_25_right 
FROM 
  grid;
```

<br>

## Stuck in the middle with you
You might be fortunate, and find that the interesting parts of your strings are at either end. However, chances are, you'll want to retrieve characters from somewhere around the middle. Let's see how to use `RIGHT`, `LEN`, `CHARINDEX` AND `SUBSTRING` to extract the interior portion of a text string. The `description` column can contain multiple reasons for power outages in each row. We want to extract any additional causes of outage whenever `Weather` appears in the description column.

**Instructions**

1. You can use `CHARINDEX` to find a specific character or pattern within a column. Edit the query to return the `CHARINDEX` of the string `'Weather'` whenever it appears within the `description` column.

2. 

3. 

<br>

## 