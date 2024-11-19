## Aggregate functions and data types
Aggregate functions are another valuable tool for the SQL programmer. They are used extensively across businesses to calculate important metrics, such as the average cost of making a film.

You know five different aggregate functions:

- `AVG()`
- `SUM()`
- `MIN()`
- `MAX()`
- `COUNT()`

Test your knowledge of what data types they are compatible with.

**Instructions**

Classify the function based on what data type it is compatible with.

| Numerical data only | Various data types |
| ------------------- | ------------------ |
| `AVG()` | `MAX()` |
| `SUM()` | `MIN()` |
|  | `COUNT()` |

> Congratulations! You've got aggregate functions under control.

<br>

## Practice with aggregate functions
Now let's try extracting summary information from a table using these new aggregate functions. Summarizing is helpful in real life when extracting top-line details from your dataset. Perhaps you'd like to know how old the oldest film in the films table is, what the most expensive film is, or how many films you have listed.

Now it's your turn to get more insights about the `films` table!

**Instructions**

1. Use the `SUM()` function to calculate the total duration of all films and alias with `total_duration`.

``` sql 
SELECT SUM(duration) AS total_duration
from films;
```

2. Calculate the average duration of all films and alias with `average_duration`.

``` sql 
SELECT AVG(duration) AS average_duration
from films;
```

3. Find the most recent `release_year` in the `films` table, aliasing as `latest_year`.

``` sql 
SELECT MAX(release_year) AS latest_year
from films;
```

4. Find the duration of the shortest film and use the alias `shortest_film`.

``` sql 
SELECT MIN(duration) AS shortest_film
from films;
```

> Well done! You'll find yourself using aggregate functions over and over again to get a quick grasp of the data in a SQL database.

<br>

## Combining aggregate functions with WHERE
When combining aggregate functions with `WHERE`, you get a powerful tool that allows you to get more granular with your insights, for example, to get the total budget of movies made from the year 2010 onwards.

This combination is useful when you only want to summarize a subset of your data. In your film-industry role, as an example, you may like to summarize each certification category to compare how they each perform or if one certification has a higher average budget than another.

Let's see what insights you can gain about the financials in the dataset.

**Instructions**

1. Use `SUM()` to calculate the total `gross` for all films made in the year 2000 or later, and use the alias `total_gross`.

``` sql
SELECT SUM(gross) AS total_gross
FROM films
WHERE release_year >= 2000;
```

2. Calculate the average amount grossed by all films whose titles start with the letter 'A' and alias with `avg_gross_A`.

``` sql
SELECT AVG(gross) AS avg_gross_A
FROM films
WHERE title LIKE 'A%';
```

3. Calculate the lowest gross film in 1994 and use the alias `lowest_gross`.

``` sql
SELECT MIN(gross) AS lowest_gross
FROM films
WHERE release_year = 1994;
```

4. Calculate the highest gross film between 2000 and 2012, inclusive, and use the alias `highest_gross`.

``` sql
SELECT MAX(gross) AS highest_gross
FROM films
WHERE release_year BETWEEN 2000 AND 2012;
```

> Nice. SQL provides us with several building blocks that we can combine in all kinds of ways, hence the name: Structured Query Language.

<br>

## Using ROUND()
Aggregate functions work great with numerical values; however, these results can sometimes get unwieldy when dealing with long decimal values. Luckily, SQL provides you with the `ROUND()` function to tame these long decimals.

If asked to give the average budget of your films, ten decimal places is not necessary. Instead, you can round to two decimal places to create results that make more sense for currency.

Now you try!

**Instructions**

Calculate the average `facebook_likes` to one decimal place and assign to the alias, `avg_facebook_likes`.

``` sql
SELECT ROUND(AVG(facebook_likes), 1) AS avg_facebook_likes
FROM reviews;
```

> Well done! The average, rounded `facebook_likes` is `7802.9`. This insight can be used as a benchmark to measure film reviews; any film with over `7802.9` likes can be considered popular.

<br>

## ROUND() with a negative parameter
A useful thing you can do with `ROUND()` is have a negative number as the decimal place parameter. This can come in handy if your manager only needs to know the average number of `facebook_likes` to the hundreds since granularity below one hundred likes won't impact decision making.

Social media plays a significant role in determining success. If a movie trailer is posted and barely gets any likes, the movie itself may not be successful. Remember how 2020's "Sonic the Hedgehog" movie got a revamp after the public saw the trailer?

Let's apply this to other parts of the dataset and see what the benchmark is for movie budgets so, in the future, it's clear whether the film is above or below budget.

**Instructions**

Calculate the average `budget` from the films table, aliased as avg_budget_thousands, and round to the nearest thousand.

``` sql
SELECT ROUND(AVG(budget), -3) AS avg_budget_thousands
FROM films;
```

> `ROUND()` of applause! The `ROUND()` function is very handy when making financial calculations to get a top-level view or specify to the penny or cent.

<br>

## Using arithmetic
SQL arithmetic comes in handy when your table is missing a metric you want to review. Suppose you have some data on movie ticket sales, but the table only has fields for ticket price and discount. In that case, you could combine these by subtracting the discount from the ticket price to get the amount the film-goer paid.

You have seen that SQL can act strangely when dividing integers. What is the result if you divide a `discount` of two dollars by the `paid_price` of ten dollars to get the discount percentage?

**Instructions**

Possible answers

- [ ] 2
- [ ] 0.222
- [x] 0
- [ ] 0.2

``` sql
SELECT (2 / 10):
```

> Correct! SQL thinks we want the answer to be an integer since we are dividing two integers. 0 is the closest integer to 0.2.

<br>

## Aliasing with functions
Aliasing can be a lifesaver, especially as we start to do more complex SQL queries with multiple criteria. Aliases help you keep your code clean and readable. For example, if you want to find the `MAX()` value of several fields without aliasing, you'll end up with the result with several columns called `max` and no idea which is which. You can fix this with aliasing.

Now, it's over to you to clean up the following queries.

**Instructions**

1. Select the title and duration in hours for all films and alias as duration_hours; since the current durations are in minutes, you'll need to divide duration by 60.0.

``` sql
SELECT title, (duration / 60.0) as duration_hours
FROM films;
```

2. Calculate the percentage of people who are no longer alive and alias the result as percentage_dead.

``` sql
SELECT COUNT(deathdate) * 100.0 / COUNT(*) AS percentage_dead
FROM people;
```

3. Find how many decades (period of ten years) the films table covers by using MIN() and MAX(); alias as number_of_decades.

``` sql 
SELECT (MAX(release_year) - MIN(release_year)) / 10.0 AS number_of_decades
FROM films;
```

> Amazing work mastering arithmetic, aggregate functions, and aliasing! Now you know that our `films` table covers films released over one hundred years!

<br>

## Rounding results
You found some valuable insights in the previous exercise, but many of the results were inconveniently long. We forgot to round! We won't make you redo them all; however, you'll update the worst offender in this exercise.

**Instructions**

Update the query by adding ROUND() around the calculation and round to two decimal places.

``` sql
SELECT title, ROUND((duration / 60.0), 2) AS duration_hours
FROM films;
```

> That's better! Now you can clearly see how long a movie is.
