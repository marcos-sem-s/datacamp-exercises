## Sorting text
SQL provides you with the ORDER BY keyword to sort one or more fields from your data. It can do this multi-directionally and helps make results easy to interpret.

How does ORDER BY sort a column of text values by default? Select one answer.

- [x] Alphabetically (A-Z)
- [ ] Reverse alphabetically (Z-A)
- [ ] There's no natural ordering to text data
- [ ] By number of characters (fewest to most)

> Correct! Because ascending is the default, indicating ASC is helpful for clarity but not required!.

<br>

## Sorting single fields
Now that you understand how `ORDER BY` works, you'll put it into practice. In this exercise, you'll work on sorting single fields only. This can be helpful to extract quick insights such as the top-grossing or top-scoring film.

The following exercises will help you gain further insights into the film database.

**Instructions**

1. Select the `name` of each person in the `people` table, sorted alphabetically.

``` sql
SELECT name 
FROM people
ORDER BY name;
```

2. Select the `title` and `duration` for every film, from longest duration to shortest.

``` sql
SELECT title, duration
FROM films
ORDER BY duration DESC;
```

> Superb sorting! `ORDER BY` is another simple yet effective way to gain intelligence about your business and data. You now know how to extract your best and worst-performing assets with only a few lines of code.

<br>

## Sorting multiple fields
ORDER BY can also be used to sort on multiple fields. It will sort by the first field specified, then sort by the next, and so on. As an example, you may want to sort the people data by age and keep the names in alphabetical order.

Try using ORDER BY to sort multiple columns.

**Instructions**

1. Select the release_year, duration, and title of films ordered by their release year and duration, in that order.

``` sql
SELECT release_year, duration, title
FROM films
ORDER BY release_year, duration;
``` 

2. Select the certification, release_year, and title from films ordered first by certification (alphabetically) and second by release year, starting with the most recent year.

``` sql
SELECT certification, release_year, title
FROM films
ORDER BY certification, release_year DESC;
```

> Nicely done! The second column you order on only steps in when the first column has been ordered.

<br>

## GROUP BY single fields
`GROUP BY` is a SQL keyword that allows you to group and summarize results with the additional use of aggregate functions. For example, films can be grouped by the certification and language before counting the film titles in each group. This allows you to see how many films had a particular certification and language grouping.

In the following steps, you'll summarize other groups of films to learn more about the films in your database.

**Instructions**

1. Select the `release_year` and count of films released in each year aliased as `film_count`.

``` sql
SELECT release_year, COUNT(*) as film_count
FROM films
GROUP BY release_year;
```

2. Select the `release_year` and average duration aliased as `avg_duration` of all films, grouped by `release_year`.

``` sql
SELECT release_year, AVG(duration) as avg_duration
FROM films
GROUP BY release_year;
```

> Great job grouping! Using `GROUP BY` with a time or date field such as `release_year` can help us identify trends such as a period of time where movies were really short!

<br>

## GROUP BY multiple fields
`GROUP BY` becomes more powerful when used across multiple fields or combined with `ORDER BY` and `LIMIT`.

Perhaps you're interested in learning about budget changes throughout the years in individual countries. You'll use grouping in this exercise to look at the maximum budget for each country in each year there is data available.

**Instructions**

Select the `release_year`, `country`, and the maximum `budget` aliased as `max_budget` for each year and each country; sort your results by `release_year` and `country`.

``` sql
SELECT release_year, country, MAX(budget) as max_budget
FROM films
GROUP BY release_year, country
ORDER BY release_year, country;
```

> Well done! You can see how building on your SQL queries helps you gain more insights and detect trends in the data, such as how film budgets may change throughout the years.

<br>

## Answering business questions
In the real world, every SQL query starts with a business question. Then it is up to you to decide how to write the query that answers the question. Let's try this out.

Which `release_year` had the most language diversity?

Take your time to translate this question into code. We'll get you started then it's up to you to test your queries in the console.

"Most language diversity" can be interpreted as `COUNT(DISTINCT ___)`. Now over to you.

**Instructions**

Possible answers

- [ ] 2005
- [ ] 1916
- [x] 2006
- [ ] 1990

``` sql
SELECT release_year, COUNT(DISTINCT language) as number_of_unique_languages
FROM films
GROUP BY release_year
ORDER BY number_of_unique_languages DESC;
```

> Well done! The year 2006 had 16 distinct languages, that's more than any other year.

<br>

## Filter with HAVING
Your final keyword is `HAVING`. It works similarly to `WHERE` in that it is a filtering clause, with the difference that `HAVING` filters grouped data.

Filtering grouped data can be especially handy when working with a large dataset. When working with thousands or even millions of rows, `HAVING` will allow you to filter for just the group of data you want, such as films over two hours in length!

Practice using `HAVING` to find out which countries (or country) have the most varied film certifications.

**Instructions**

- Select `country` from the `films` table, and get the distinct count of `certification` aliased as `certification_count`.
- Group the results by `country`.
- Filter the unique count of certifications to only results greater than 10.

``` sql 
SELECT country, COUNT(DISTINCT certification) as certification_count
FROM films
GROUP BY country
HAVING COUNT(DISTINCT certification) > 10;
```

> Great job! The answer is USA with 12 different certifications.

<br>

## HAVING and sorting
Filtering and sorting go hand in hand and gives you greater interpretability by ordering our results.

Let's see this magic at work by writing a query showing what countries have the highest average film budgets.

**Instructions**

- Select the `country` and the average budget as `average_budget`, rounded to two decimal, from `films`.
- Group the results by `country`.
- Filter the results to countries with an average budget of more than one billion (`1000000000`).
- Sort by descending order of the `average_budget`.

``` sql
SELECT country, AVG(budget) as average_budget
FROM films
GROUP BY country
HAVING AVG(budget) > 1000000000
ORDER BY average_budget DESC;
```

> You did it! South Korea and Hungary seem to have pricey films... or do they? Actually, these budgets are pretty standard for their local currency.

<br>

## All together now
It's time to use much of what you've learned in one query! This is good preparation for using SQL in the real world where you'll often be asked to write more complex queries since some of the basic queries can be answered by playing around in spreadsheet applications.

In this exercise, you'll write a query that returns the average budget and gross earnings for films each year after 1990 if the average budget is greater than 60 million.

This will be a big query, but you can handle it!

**Instructions**

1. Select the `release_year` for each film in the `films` table, filter for records released after 1990, and group by `release_year`.

``` sql
SELECT release_year
FROM films
WHERE release_year > 1990
GROUP BY release_year;
```

2. Modify the query to include the average `budget` aliased as `avg_budget` and `average` gross aliased as `avg_gross` for the results we have so far.

``` sql
SELECT release_year, AVG(budget) as avg_budget, AVG(gross) as avg_gross
FROM films
WHERE release_year > 1990
GROUP BY release_year;
```

3. Modify the query once more so that only years with an average budget of greater than 60 million are included.

``` sql
SELECT release_year, AVG(budget) AS avg_budget, AVG(gross) AS avg_gross
FROM films
WHERE release_year > 1990
GROUP BY release_year
HAVING AVG(budget) > 60000000;
```

4. Finally, order the results from the highest average gross and limit to one.  

``` sql
SELECT release_year, AVG(budget) AS avg_budget, AVG(gross) AS avg_gross
FROM films
WHERE release_year > 1990
GROUP BY release_year
HAVING AVG(budget) > 60000000
ORDER BY avg_gross DESC
LIMIT 1
```

> Superb work! SQL queries can get rather long, but breaking them down into individual clauses makes them easier to write.
