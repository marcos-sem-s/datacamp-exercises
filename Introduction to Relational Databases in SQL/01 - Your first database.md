## Attributes of relational databases
In the video, we talked about some basic facts about relational databases. Which of the following statements does **_not_** hold true for databases? Relational databases ... Select one answer.

- [ ] ... store different real-world entities in different tables.
- [ ] ... allow to establish relationships between entities.
- [x] ... are called "relational" because they store data only about people.
- [ ] ... use constraints, keys and referential integrity in order to assure data quality.

> Correct! Of course, databases can also store information about any other kind of entities, e.g. spare car parts.

<br>

## Query information_schema with SELECT
`information_schema` is a meta-database that holds information about your current database. information_schema has multiple tables you can query with the known `SELECT * FROM` syntax:

- tables: information about all tables in your current database
- columns: information about all columns in all of the tables in your current database
- ...

In this exercise, you'll only need information from the `'public'` schema, which is specified as the column `table_schema` of the `tables` and `columns` tables. The `'public'` schema holds information about user-defined tables and databases. The other types of `table_schema` hold system information – for this course, you're only interested in user-defined stuff.

**Instructions**

1. Get information on all table names in the current database, while limiting your query to the `'public'` `table_schema`.

``` sql
SELECT table_name 
FROM information_schema.tables
WHERE table_schema = 'public';
```

2. Now have a look at the columns in `university_professors` by selecting all entries in `information_schema.columns` that correspond to that table.

``` sql

```

3. 

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

