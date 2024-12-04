## Your first join
Throughout this course, you'll be working with the `countries` database, which contains information about the most populous cities in the world, along with country-level economic, population, and geographic data. The database also contains information on languages spoken in each country.

You can see the different tables in this database to get a sense of what they contain by clicking on the corresponding tabs. Familiarize yourself with the fields that seem to be shared across tables before you continue with the course.

In this exercise, you'll use the `cities` and `countries` tables to build your first inner join. You'll start off by selecting all columns in step 1, performing your join in step 2, and then refining your join to choose specific columns in step 3.

**Instructions**

1. Begin by selecting all columns from the `cities` table, using the SQL shortcut that selects all.
2. Perform an inner join with the `cities` table on the left and the `countries` table on the right; you **do not** need to alias tables here. Join `ON` the `country_code` and `code` columns, making sure you identify them with the correct table.
3. Complete the `SELECT` statement to keep three columns: the `name` of the city, the `name` of the country, **and** the `region` the country is located in (in this order). Alias the name of the city `AS city` and the name of the country `AS country`.

``` sql
SELECT 
    cities.name AS city, 
    countries.name AS country,
    countries.region
FROM 
    cities
INNER JOIN 
    countries
    ON cities.country_code = countries.code;
```

> Great work! Writing out full table names when joining tables creates a lot of extra code. In the next exercise, you'll explore how you can do more aliasing to limit the amount of writing.

<br>

## Joining with aliased tables
Table aliases are helpful in allowing you to reference them in other parts of your query, like the `SELECT` statement.

When you `SELECT` fields, a field can be ambiguous. For example, imagine two tables, `apples` and `oranges`, both containing a column called `color`. You need to use the syntax `apples.color` or `oranges.color` in your `SELECT` statement to point SQL to the correct table. Without this, you would get the following error:

```
column reference "color" is ambiguous
```

You'll practice joining with aliased tables using data from both the `countries` and `economies` tables to examine the inflation rate in 2010 and 2015.

When writing joins, many SQL users prefer to write the `SELECT` statement _after_ writing the join code, in case the `SELECT` statement requires using table aliases.

**Instructions**

- Start with your inner join in line 5; join the tables `countries AS c (left)` with `economies` (right), aliasing `economies AS e`.
- Next, use `code` as your joining field in line 7; do **not** use the `USING` command here.
- Lastly, select the following columns **in order** in line 2: code from the `countries` table (aliased as `country_code`), `name`, `year`, and `inflation_rate`.

``` sql
SELECT
    c.code as country_code,
    name,
    year,
    inflation_rate
FROM countries AS c
INNER JOIN
    economies AS e
    ON c.code = e.code;
```

> Nicely done! Notice that only the `code` field is ambiguous, so it requires a table name or alias before it. All the other fields (`name`, `year`, and `inflation_rate`) do not occur in more than one table name, so do not require table names or aliasing in the `SELECT` statement. Using table aliases takes some getting used to, but it will save you a lot of typing, especially when your query involves joining tables!

<br>

## USING in action
In the previous exercises, you performed your joins using the `ON` keyword. Recall that when **both** the field names being joined on are the same, you can take advantage of the `USING` clause.

You'll now explore the `languages` table from our database. Which languages are official languages, and which ones are unofficial?

You'll employ `USING` to simplify your query as you explore this question.

**Instructions**

Use the country `code` field to complete the `INNER JOIN` with `USING`; do **not** change any alias names.

``` sql
SELECT c.name AS country, l.name AS language, official
FROM countries AS c
INNER JOIN languages AS l
USING(code);
```

> Great work! It looks like Afghanistan has multiple official _and_ unofficial languages! A parting word of caution when using `USING`: columns can sometimes have the same name but actually contain vastly different data. Always remember to check what you are joining on by displaying and viewing your data first!

<br>

## Relationships in our database
Now that you know more about the different types of relationships that can exist between tables, it's time to examine a few relationships in the `countries` database!

To answer questions about table relationships, you can explore the tables displayed as tabs in your console.

**Instructions**

1. What best describes the relationship between `code` in the countries table and `country_code` in the `cities` table?

- [ ] This is a many-to-many relationship.
- [ ] This is a one-to-one relationship.
- [x] This is a one-to-many relationship.

1. Which of these options best describes the relationship between the `countries` table and the `languages` table?

- [ ] This is a one-to-many relationship.
- [x] This is a many-to-many relationship.
- [ ] This is a one-to-one relationship.

> That's right! Recall Belgium has three official languages, French, German, and Dutch. Conversely, languages can be official in many countries: Dutch is an official language of both the Netherlands and Belgium, but not Germany. Because of the many types of relationships tables can have, there are many ways to join data.

<br>

## Inspecting a relationship
You've just identified that the `countries` table has a many-to-many relationship with the `languages` table. That is, many languages can be spoken in a country, and a language can be spoken in many countries.

But, what is the best way to query all the different languages spoken in a country? Or, all the countries that speak a certain language?
    
**Instructions**

1. Select the country `name`, aliased as `country`, from the `countries` table.

``` sql
SELECT 
    name AS country
FROM 
    countries;
```

2. Now add an alias `c` for the `countries` table and perform an inner join with the `languages` table, `l`, on the right; join on `code` in line 8 with the `USING` keyword; include the language name, aliased as `language`.

3. Add a `WHERE` clause to find how many countries speak the language `'Bhojpuri'`.

``` sql
SELECT c.name AS country, l.name AS language
FROM countries AS c
INNER JOIN 
    languages as l
    USING(code);
WHERE l.name = 'Bhojpuri';
```

4. In how many countries is the `'Bhojpuri'` language spoken? Select the **correct** answer from the following options.
The query you generated is provided below. Run this query to find the answer to the question.

``` sql
SELECT c.name AS country, l.name AS language
FROM countries AS c
INNER JOIN languages AS l
USING(code)
WHERE l.name = 'Bhojpuri';
```

- [ ] 1
- [x] 2
- [ ] 3

> Correct! Bhojpuri is spoken in two countries: Mauritius and Nepal.

<br>

## 

> 

<br>

## 

> 

<br>

## 

> 

<br>

## 

> 

<br>

## 

> 

