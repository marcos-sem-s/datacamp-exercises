## Traditional vs. cloud data warehouse
You learned about traditional and cloud data warehouses, which are two different approaches to storing and managing data. Understanding their differences is crucial as it enables businesses to make informed decisions about their data infrastructure.

**Instructions**

Reflecting on the content discussed, categorize each characteristic or feature by determining which category it belongs to: traditional data warehouses or cloud data warehouses

| Traditional data warehouse | Cloud data warehouse |
| -------------------------- | -------------------- |
| High upfront hardware and software costs| Utilizes cloud infrastructure |
| Limited scalability | Highly scalable and flexible |
| Limited accessibility | Accessible from anywhere |

> Well done! You've got it! Cloud data warehouses are highly scalable and flexible since they leverage cloud infrastructure. This aspect has driven their immense popularity in recent years.

<br>

## Row versus column oriented database
In the world of databases, two primary storage models are widely used: row-oriented and column-oriented databases. Each of these database types has its strengths and use cases.

**Instructions**

Match the scenarios with the appropriate database classification.

| Row-oriented database | Column-oriented database |
|-----------------------------------------------------------------|----------------------------------------------------------------------|
| Updating and managing inventory levels for individual products. | Running complex queries to track inventory levels and sales performance in a retail system. |
| Recording and processing individual sales transactions in an online retail system. | Analyzing and summarizing large volumes of historical sales data for trend analysis and forecasting in a retail chain. |
| | Creating real-time reports for website traffic and user interactions on an e-commerce platform. |

> Great job! You've accurately matched the scenarios to the appropriate database classifications. It's important to recognize that both databases have their specific use cases where they can be valuable and effective. Keep up the great effort.

<br>

## Snowflake use cases
Snowflake is a cloud data warehouse solution that utilizes a columnar data storage model. This enables Snowflake to excel in various use cases, making it a powerful choice for organizations dealing with data-intensive tasks.

What are the use cases where organizations leverage the power of Snowflake? Select all correct answers.

- [x] Data analytics
- [ ] Content creation for online platforms.
- [x] To gain insights through advanced analytics
- [ ] To increase social media followers

> Congratulations! You nailed it! Snowflake's columnar data storage model and its unique architecture indeed enables advanced analytics, and efficient handling of data-intensive tasks.

<br>

## Introduction to Snowflake SQL
Are you ready to refresh your SQL skills? Wondering why in Snowflake? Rest assured, Snowflake SQL is quite similar to PostgreSQL. Even though Snowflake automatically capitalizes column names by default, fundamental commands like `SELECT` will operate in much the same way as they do in PostgreSQL. So, you're in familiar territory!

You are working as a data engineer at Pissa, an expanding pizza delivery company. As part of the transition from PostgreSQL to Snowflake, you're now examining the different columns in the `pizzas` table.

**Instructions**

Select `pizza_type_id`, `pizza_size` and `price` from the `pizzas` table

``` sql
SELECT pizza_type_id, pizza_size, price
FROM pizzas;
```

> Congratulations! You're already familiar with how the SELECT command works in Snowflake, as it's similar to Postgres. That means you're already coding in Snowflake! Well done!

<br>

## Decoupling Compute & Storage
In Snowflake's cutting-edge architecture, one of its defining features is the concept of decoupling compute and storage.

This innovative approach allows organizations to gain significant advantages in scalability, performance, and cost optimization.

What does decoupling compute and storage mean in Snowflake architecture? Select one answer.

- [ ] Combining compute and storage resources to optimize performance.
- [ ] Storing data and compute resources on separate servers but linked closely.
- [x] Separating the compute resources from the data storage allows to scale them independently.

> Well done! By separating the compute resources from data storage, Snowflake allows them to scale independently, leading to better resource allocation and enhanced data processing efficiency.

<br>

## Snowflake Architecture Layers
In Snowflake's architecture, we have three layers - Storage, Compute, and Cloud Services.

Each layer consists of specific components responsible for different functionalities, creating a unique and powerful architecture that enables organizations to scale compute and storage independently.

**Instructions**

Recall the roles of these components and drag and drop them into their appropriate layers.

| Storage Layer | Compute Layer | Cloud Services Layer |
| ------------- | ------------- | -------------------- |
| Columnar Storage | Query Processing | Optimizer |
| Data compression | Virtual Warehouse | Authentication |

> Bravo! You've skillfully paired each component with its corresponding layer in Snowflake's architecture! These essential components play a vital role in defining the functionalities and strength of each layer, making Snowflake's architecture a powerful and cohesive system.

<br>

## Virtual Warehouse
In Snowflake's architecture, a critical component in the 'Compute Layer' is the "Virtual Warehouse."

Understanding its role and functionalities is essential for harnessing the full potential of Snowflake's cloud data warehousing solution.

What is the role of the "Virtual Warehouse" in Snowflake's architecture? Select all correct answers.

- [x] Handling query processing.
- [ ] Storing and organizing data in Snowflake.
- [x] Managing compute resources.
- [ ] Managing metadata and access control.

> Awesome work! The "Virtual Warehouse" is a vital component in Snowflake's architecture, responsible for query processing and compute resource management.

<br>

## Data warehousing platforms
We compared data warehousing platforms operating in the same domain as Snowflake. Each of these data warehouses offers its distinct features.

Which of the following are the competitors in the cloud data warehousing space? Select all correct answers.

- [x] Amazon Redshift
- [x] Google BigQuery
- [ ] Postgres
- [ ] Azure Data Lake Storage

> Congratulations! You've correctly recognized the primary cloud data warehousing platforms. Understanding these various solutions is crucial for making informed decisions about data warehousing.

<br>

## Features: Snowflake & its competitors
We explored the competitor landscape surrounding Snowflake and familiarized ourselves with the distinctive features of both Snowflake and other data platforms.

Throughout the session, you discovered the distinctive features that make Snowflake stand out while also noting that some competitors offer similar capabilities.

You now have a chance to reinforce your understanding by applying what you've learned.

**Instructions**

Drag and drop the statements based on the learning and classify them as True or False.

| True | False |
| ---- | ----- |
| Databricks provides autoscaling | Snowflake doesn't support JSON | 
| SnowflakeSQL has many similarities with PostgreSQL | Snowflake uses a single pricing model that charges for both compute and storage. |
| Postgres can be hosted on Cloud Platforms | Snowflake offers coupled Storage and Compute |

> Amazing work! You have completed an insightful journey exploring the competitive landscape of Snowflake and gaining valuable knowledge about the distinctive features of various data platforms.

<br>

## Snowflake SQL: Using SELECT and WHERE in Snowflake
You are still consulting as a data engineer at Pissa, a growing pizza delivery company transitioning its legacy on-premise Postgres data warehouse to Snowflake to be more efficiently able to handle the volatile demand of its business.

The goal is to ensure the integrity and correctness of the data after migration. You're specifically working with the `pizza_type` table, which is critical as it contains all the different types of pizzas.

Let's leverage your `SQL` skills to see if it works in Snowflake as well.

**Instructions**

1. Count the total number of pizza entries in the `pizza_type`.
2. Filter the query to count only the pizzas that are categorized as `Classic`.
3. Further refine the count to include only those pizzas where the `name` contains the word `Cheese`.

``` sql
SELECT COUNT(*) AS count_all_pizzas
FROM pizza_type
WHERE category = 'Classic'
AND name LIKE '%Cheese%';
```

> Congratulations! You did it! Your skills have proven invaluable in handling the data migration for Pissa. Now, you know that PostgreSQL indeed works well for Snowflake.
