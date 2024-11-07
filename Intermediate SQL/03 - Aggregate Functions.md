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

## 