## Snowflake connections and DDL commands
You learned about the different ways to connect with Snowflake, whether through the Web Interface, command line, or drivers.

Similarly, you noticed how many DDL commands in Snowflake bear a resemblance to those in PostgreSQL.

But true understanding often comes from practice. Let's reinforce these learnings with this exercise!

**Instructions**

Drag and drop the statements based on what you've learned. Classify them as True or False.

| True | False |
| ---- | ----- |
| `DROP TABLE` command deleted the data and table structure. | We can't connect to Snowflake through JDBC/ODBC drivers. |
| SnowSQL is a command-line client that provides a direct way to interact with Snowflake. | In Snowflake, you can use `VALIDATE TABLE` to ensure an operation proceeds if a specific table exists. |
| Snowflake offers worksheets to write and execute queries in Snowflake Web Interface. | There is no difference in adding comments in Snowflake versus Postgres. |

> Congratulations! You've successfully reinforced your understanding of Snowflake's connection methods and DDL commands. While Snowflake's DDL commands mirror those in PostgreSQL, its ability to support diverse connection methods, from web to command line, showcases its versatility in today's cloud-centric world!

<br>

## Snowflake Staging
Understanding Snowflake Staging is important for several reasons, such as performance optimization. Which of the following best describes Snowflake Staging? Select one answer.

- [ ] Snowflake Staging is an area where data transformations occur before they're loaded into Snowflake tables.
- [x] Snowflake Staging is an intermediary storage area used for storing data files before they are loaded into Snowflake tables.
- [ ] Snowflake Staging is the Snowflake's backup mechanism for saving database states in case of system failures.

> Correct! Snowflake staging acts as an intermediary storage area. It can be set up either local within Snowflake or on external cloud platforms.

<br>

## Loading data
You learned about how Snowflake loads data from a file in a staging area into a table. You are now working to load a file from your local staging area to a table.

Can you recall which of the following command will load data from your staging area `my_local_stage` to table `pizza_type`. Select one answer.

- [ ] `LOAD DATA INTO pizza_type FROM <//your/local/file/path>`
- [ ] `INSERT INTO pizza_type from @my_local_stage`
- [ ] `UPLOAD DATA INTO pizza_type from @my_local_stage`
- [x] `COPY INTO pizza_type FROM @my_local_stage`

> Correct! In Snowflake, the `COPY INTO` command is used to efficiently load data from a staging area into a table. Up next, you'll dive into the interactive `DESCRIBE` and `SHOW` commands. Get ready to explore them hands-on!

<br>

## DESCRIBE & SHOW
Pissa, the expanding pizza delivery enterprise, again requests your excellent data engineering skills. Currently, you're exploring their database structures.

Your understanding of the `SHOW` and `DESCRIBE` commands will be critical for this task.

You are working within a database named `pizza`, which contains a table named orders and a view named `orders_view`.

**Instructions**

Examine each of the following syntax examples and classify them as either "Correct Syntax" or "Incorrect Syntax".

| Correct Syntax | Incorrect Syntax |
| -------------- | ---------------- |
| `DESCRIBE DATABASE pizza` | `SHOW COLUMNS OF TABLE orders`|
| `DESCRIBE TABLE orders` | `SHOW TABLES FOR DATABASE pizza` |
| `SHOW TABLES LIKE '%ORDERS%' IN DATABASE pizza` | `DESCRIBE IN VIEW ORDERS_VIEW` |

> Congratulations! You've successfully identified the correct and incorrect syntaxes for `DESCRIBE` and `SHOW` commands in Snowflake. This will help you effectively navigate and manage your Snowflake database environment.

<br>

## Data types
You've learned various Snowflake data types like VARCHAR, NUMERIC, DATE, TIME, and TIMESTAMP.

Let's test your knowledge!

**Instructions**

Drag each statement to the correct classification: 'True' or 'False'.

| True | False |
| ---- | ----- |
| `TIMESTAMP` é uma combinação de `DATE` e `TIME`. | `TIMESTAMP` no Snowflake não armazena minutos no `Time`.  |
| O formato padrão de `DATE` no Snowflake é `YYYY-MM-DD`. | `VARCHAR` no Postgres pode armazenar mais caracteres que no Snowflake. |
| O formato padrão para `TIME` é `HH:MI:SS`. | |

> Awesome work! You've demonstrated a solid understanding of Snowflake's data types. Next, we'll dive into creating tables using these data types.

<br>

## Datatype conversion
When working with databases, there are times when we need to change the data type of a column to better suit our operations or analyses.

As a consulting data engineer for CityRide, you have been given access to a dataset from their partner, Uber.

The datasets captures ride details and include fields such as `driver_id`, `pickup_point`, `status`, and `request_timestamp`.

These fields might not be in the desired data types, and it's your task to rectify this and apply necessary data type conversions to ensure data consistency and facilitate smoother analysis.

**Instructions**

1. Select and convert the `request_id` column from `uber_request_data` table to `VARCHAR` using the `CAST` method aliasing it to `request_id_string`.
2. Convert `request_timestamp` to `DATE` using the `TO_DATE` function aliasing it as `request_date`.
3. Convert the `drop_timestamp` column to `TIME` using the `::` operator, and alias it to `drop_time`. Filter the records where `request_date` is greater than '2016-06-01' and `drop_time` is less than '6 AM'.

``` sql
SELECT 
    CAST(request_id AS VARCHAR) AS request_id_string, 
    TO_DATE(request_timestamp) AS request_date,
    drop_timestamp::TIME AS drop_time
FROM uber_request_data
WHERE request_date > '2016-06-01' AND drop_time < '06:00:00';
```

> Great work! You've got a solid grasp on Snowflake data type conversion. With this skill, you can easily handle many other conversions. Keep going!

<br>

## String functions
Having recently mastered string functions such as `UPPER`, `LOWER`, and `CONCAT`, you're ready to put them into practice.

As a freelance data engineer, CityRide, a leading urban mobility platform, has approached you with their raw Uber ride data. Your task is to make this data consistent using the string functions you've learned.

**Instructions**

1. Standardize the status entries in the `uber_request_data` table. Convert all entries in the status column to lowercase.

``` sql
SELECT LOWER(status) FROM uber_request_data;
```

2. Convert all entries in the `pickup_point` column to uppercase.

``` sql
SELECT UPPER(pickup_point) FROM uber_request_data;
```

3. Complete the `CONCAT` function to combine the `pickup_point` and status with the given comments.

``` sql
SELECT CONCAT('Trip from ', pickup_point, ' was completed with status: ', status) AS trip_comment
FROM uber_request_data;
```

> Incredible! You've transformed the data, making it consistent and easy to understand. Great use of your string function knowledge! Keep up the exceptional work!

<br>

## Functions & Grouping
As a freelancer at Pissa, you're examining pizza order details. As the team dives deeper into the sales data, there's a need to focus on orders with larger quantities to ensure efficient service and delivery.

Using your knowledge of aggregate functions, sorting, and grouping, complete the query to analyze and prioritize these bulk orders.

**Instructions**

- Retrieve the `order_id` and `pizza_id` from `order_details` for orders where the total pizza quantity is more than 3 using the `HAVING` clause.
- Group the orders using `GROUP BY ALL`
- Arrange your results by `order_id` and then by `total_quantity` in a descending sequence.

``` sql
SELECT order_id, pizza_id, SUM(quantity) AS total_quantity
FROM order_details
GROUP BY ALL
HAVING total_quantity > 3
ORDER BY order_id, total_quantity DESC
```

> Outstanding! Your ability to analyze data is as impressive as a perfectly baked Margherita slice! Leveraging aggregate functions lets us dive deep into the data, and did you notice how 'GROUP BY ALL' streamlined your query? It elegantly groups by all columns without us having to specify them.

<br>

## DATE & TIME
As a freelance data engineer assisting CityRide, you are now focusing on timestamp-related columns in their raw Uber ride data.

Use your knowledge of date and time functions to accomplish the tasks.

**Instructions**

1. Select the current date and current time using a valid date and time functions.

``` sql
SELECT CURRENT_DATE, CURRENT_TIME;
```

2. Complete the concatenation for the `CURRENT_DATE` and `CURRENT_TIME`, converting the result to `TIMESTAMP`.

``` sql
SELECT CONCAT(CURRENT_DATE, ' ', CURRENT_TIME)::TIMESTAMP;
```

3. 

> 

<br>

