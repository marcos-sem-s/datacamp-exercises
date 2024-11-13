## Understanding facts and dimensional tables
Fact and dimensional tables are key to the star schema data model. Therefore, it is important to understand them.

Select the **_true_** statement about fact and dimensional tables. Select one answer.

- [ ] A fact table holds additional attributes/characteristics about an organizational process.
- [ ] A dimensional table contains measurements and metrics for the organization.
- [x] A fact table used within the Apple music service to track artist albums might include columns like ArtistID, GenreID, SongLength, and UnitPrice.
- [ ] An example of a fact table used by a food manufacturer to track production is a table that only contains the manufacturing plant's ID, location, name, and size.

> Excellent job! You got it right. Fact tables contain measurements and metrics, which this table has in song length, and unit price. In addition, the artist and genre ids can be used to join dimensional tables to provide more details about the song length or unit prices.

<br>

## One starry and snowy night
You learned about star and snowflake schemas in the last video.

Select the **_false_** statement about star and snowflake schemas. Select one answer.

The relatively few joins for a star schema make queries easy to use by organizational users.
When you must join the dimensional department table via the employee dimensional table to analyze an organization's total sales through the sales fact table, this is an example of a star schema.
In a snowflake schema, at least one-dimensional table cannot be joined directly to the fact table.

> Great job! This statement is false and is an example of a snowflake schema. Recall that the snowflake schema is similar to a star schema, except at least one-dimensional table can only be joined to the fact table through another dimensional table.

<br>

## Fact or dimension?
Below are the column names for two tables taken from the snowflake schema proposed by Tsvetanka Georgieva-Trifonova et al. to analyze academic bibliographic data. Your goal is to select the statement below that correctly identifies tables A and B as fact or dimension tables and the reason why. Select one answer.

| Table A | Table B |
| ------- | ------- |
| InstitutionID | PaperID |
| InstitutionName | JournalID |
| City | ProceedingsID |
| Country | InstitiutionID |
| | PublisherID |
| | CountOfAuthorID | 
| | CountOfPapers | 
| | CountOfCitations | 

- [ ] Table B is a dimension table because the count of citations is an example of an attribute about the paper, and table A is a fact table because the institution name and location are facts about that institution.
- [ ] Table A is a fact table because it has metrics and references to other dimension tables, and table B is a dimension table because it has additional characteristics and attributes about the data in Table A.
- [x] Table A is a dimension table because it provides data characteristics, and table B is a fact table because it has metrics and references to other dimension tables.

> Nice job! You correctly identified the fact and dimension tables. Just remember that fact tables contain facts/metrics that are designed to be joined to dimension tables which hold additional detail about each fact/metric.

<br>

## Ordering Kimball's steps
To create a data warehouse using the bottom-up approach and a star schema, you need to define the data model. Kimball's four-step process offers a method for doing this. Thus, review the different steps to ensure you know their order.

**Instructions**

Place the steps of the Kimball process in order.

1. Select the organizational process
2. Declare the grain
3. Identify the dimensions 
4. Identify the facts

> Congratulations! Great work on correctly ordering the steps in the Kimball process. You can use these steps when designing your next star schema data model.

<br>

## Deciding on the grain
Choosing the proper grain level for the fact table is an important step in the four-step process.

Review the statements and select the one that is true. Select one answer.

- [ ] The term grain in this step refers to the small, hard-to-see data in the warehouse.
- [ ] Selecting the grain at the highest, or most aggregate, level of detail is important because it will allow organizational users to drill into the facts.
- [x] It is crucial to select the proper grain level because selecting the wrong grain may make it impossible for organizational users to use the data to answer questions.

> Excellent job! This is a true statement. Therefore, it is vital to work with organizational users that will help you choose the grain that has the most value to the business.

<br>

## Selecting reasonable facts
Identifying the facts in the fact table is another vital step in the four-step process. In this exercise, select the option where the facts/metrics of the fact table **does not** match well with the grain of the table. Select one answer.

- [ ] For a fact table focused on bank transactions at the individual transaction grain, storing the facts of how much the transaction was and the length of the transaction is reasonable.
- [x] For a fact table focused on doctor visits with patients at the individual patient/doctor grain, storing the facts of the total number of patients a doctor has ever seen and the total doctor visits by the patient is reasonable.
- [ ] For a fact table focused on an online digital advertising campaign at the advertiser/campaign grain, storing the facts of the number of clicks and impressions of the campaign is reasonable.

> Perfect! The facts in this table do not match the grain of the table. Knowing the patient's level of sickness on a scale from one to ten for each patient-doctor interaction would be a better fact to store.

<br>

## Pop-quiz on slow changes
In the last video, you learned about slowly changing dimensions (SCD) and their impact.

The statements below discuss SCD. In this exercise, test your knowledge of SCD by selecting the false statement. Select one answer.

- [ ] Understanding how an approach will affect historical reporting should be an important consideration in choosing an approach to slowly changing dimensions.
- [ ] A slowly changing dimension is a dimension that contains relatively static data which can change slowly but unpredictably.
- [x] An example of a slowly changing dimension scenario is when you need to update a value in the fact table.

> Awesome! You selected the correct answer. All of the other statements are true, and this option is false. Slowly changing dimension situations focus on the dimension and not the fact table.

<br>

## Difference between type I, II, and III
With slowly changing dimensions, it is important to understand the differences between the Type I, II, and III approaches. In this exercise, select the true statement about Type I, II, and III approaches. Select one answer.

- [x] A Type II approach maintains historical reporting because all references to historical facts point to the old row within the dimension table.
- [ ] A Type III approach only updates the value in the dimension table row, making it quick and easy to use.
- [ ] Using a Type I approach has no impact on historical reporting.

> Great job! All of the other statements are false. It is important to remember that when deciding on the approach to take for dealing with slowly changing dimensions, understanding how this will impact historical reports is important.

<br>

## Categorizing row and column store scenarios
Row and column stores have different properties that make them optimal for different situations. Use what you have learned in the last video to categorize the different scenarios.

**Instructions**

Drag each statement into the Row store or Column store bucket based on which type of store it best describes.

Here's the table in Markdown format based on the information in the image:

| Row store | Column store |
| --------- | ------------ |
| Organizes the blocks of storage by storing rows of data | Organizes the blocks of storage by storing table columns of data |
| Is optimized for transactional queries | Optimized for analytical queries |
| Is best for operational systems that need to update and insert rows of data  | Is best for a query such as "What was the sum of sales for the South American region for the last two years?" |

> Great work! Overall, remember that the column store is optimized for analytical queries, and the row store is optimized for transactional queries. This knowledge will allow you to pick the one optimized for your situation.

<br>

## Why is column store faster?
In the last video, you learned that column store tends to be faster for analytical queries than row store.

Select the **true** statement that explains this. Select one answer.

- [ ] Column store is optimized for transactional and analytical queries compared to the row store.
- [x] Column store allows the system to read in blocks that contain only the data needed for the query, versus row store, where the blocks may include data from columns not required for the query. This results in more blocks needing to be read and a longer query time.
- [ ] Row store allows the system to better compress the data compared to column store, and it takes time to decompress the data resulting in slower query speeds.
- [ ] Column store can read the data from all the columns of a row at the same time, allowing it to return the answer faster.

> Triumph! Part of the value of data warehouses is for analyzing an organization's data, leading to analytical queries. Column store is optimized for analytical queries and therefore is a natural fit for a data warehouse.

<br>

## Which queries are faster?
In their research, Stonebrake et al. (C-Store: A Column-Oriented DBM) directly compared the speed of running queries on a column and row data store table containing shipping data. Both tables held the same data.

They tested the speed of seven different **_analytical queries_** (Q1-Q7), as shown below in the table. The speed is measured in seconds.

| Query | Table 1 speed seconds | Table 2 speed seconds |
| ----- | --------------------- | --------------------- |
| Q1 | 6.80 | 2.24 |
| Q2 | 1.09 | 0.83 |
| Q3 | 93.26 | 29.54 |
| Q4 | 722.9 | 22.23 |
| Q5 | 116.56 | 0.93 |
| Q6 | 652.9 | 32.83 |
| Q7 | 265.8 | 33.24 |

**Using this information above, select the false statement.** Select one answer.

- [ ] Table 2 is likely set up in a column store format because the query times are faster for analytical queries.
- [ ] Table 1 is likely set up in a row store format because the query times are slower for analytical queries.
- [x] Table 1 is likely set up in a column store format because the query times are slower for analytical queries.

> Perfect! This statement is false because the column store format tends to have faster query times for analytical queries since the system does not have to read blocks of data that contain info from unnecessary columns.
