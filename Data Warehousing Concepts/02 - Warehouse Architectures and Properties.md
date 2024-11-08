## Ordering data warehouse layers
In the recent video, you learned of the different architectural layers common in data warehouses. Data flows from input sources to users for analysis through these different layers.

**Instructions**

Place the different stages in order.

1. Source layer
2. Staging layer
3. Storage layer
4. Presentation layer

> You did a great job of placing the layers in order. Each layer is dependent on all the layers before it. Therefore, challenges with the source layer, such as bad data, will affect all other layers.

<br>

## Understanding ETL
The ETL process is important for moving data in the data warehouse.

Select the **true** statement about the ETL process. Select one answer.

- [ ] The transformation process in ETL can only handle sorting data and **no** mathematical operations.
- [x] Deduplication, or removing duplicate values, can be done in the ETL process.
- [ ] The data warehouse ETL process can only work with structured data sources.

> Perfect! Deduplication is a process that many ETL can tools can do.

<br>

## Pick the correct layer
Each layer of the data warehouse plays a particular role in the data warehouse. Therefore, understanding each function should help you better understand the designing process and troubleshoot problems once the warehouse is implemented.

**Instructions**

Select the layer that makes the statement true.

| Source layer | Staging layer | Storage layer |
| ------------ | ------------- | ------------- |
| Might include JSON files | Contains a database to store data temporarily during the ETL process | Contains data marts |
| Comprises all of the input data sources used in the data warehouse | Includes an ETL process that transforms the input data into a structured form | Includes the data warehouse |

> Congratulations! You have shown an understanding of the different data warehousing layers and how data flows through the layers from the source to the end user.

<br>

## Stepping into a consultant's shoes
In this exercise, imagine that you work for an online digital advertising firm on the data warehouse team. The performance of the ads the company creates for its customers is tracked within the company's data warehouse. It is important for many of the sales staff, who have little experience in coding, to track the historical performance of their advertising campaigns each month.

What type of tool could you suggest for this situation? **Select the best answer**. Select one answer.

- [x] You suggest an automated reporting or dashboarding tool because the graphical interface is easier for those without a strong coding background. The automation capabilities can save significant time since it will be needed monthly.
- [ ] You suggest a data mining tool because of their ability to explore the data and no coding experience.
- [ ] You suggest the sales team learn SQL and run queries against the data warehouse.- The sales team lacks coding experience and needs a tool that makes it easy to use on a monthly basis.

> Awesome! The lack of coding experience was the key to this question.

<br>

## Supporting analysts and data scientist users
Data warehouses support the work of analysts and data scientists. The statements below are examples of this support.

In this exercise, select the **false** statement. Select one answer.

- [ ] Support sophisticated tools such as R and Python to query the data warehouse directly.
- [x] Support automated reporting by exporting business reports during the ETL process.
- [ ] Support data exploration and pattern discovery by making the data within the warehouse available to BI or business intelligence tools.

> Great job! Data warehouses support analytical work by making the data available to users who interact with it using different tools through the presentation layer. In this particular case, you selected the correct answer. Unfortunately, the ETL process does not export business reports.

<br>

## Top-down vs bottom-up
In the last video, you learned about top-down and bottom-up approaches. The statements below compare the different architectural designs.

For this exercise, select the **true** statement. Select one answer.

- [x] The top-down approach has longer upfront development time before users can deliver reports compared to the bottom-up approach due to aligning the organization on all data definitions and cleaning rules.
- [ ] The top-down approach moves data into the data marts first compared to the bottom-up approach because this approach is focused on delivering organizational value as quickly as possible.
- [ ] The top-down approach has a higher chance of duplicate data compared to the bottom-up approach because the data is modeled for each departmental data mart.

> Great job! The top-down approach tends to have a longer upfront development time due to the focus on aligning the organization with the data definitions. However, organizations from well-established industries such as banking could use templates to speed up the development process or if the organization already has a set of integrated data where the definitions are already defined.

<br>

## Characteristics of top-down and bottom-up
The different architectural approaches reviewed in the last video have pros and cons. When designing a warehouse for an organization, it is valuable to understand these pros and cons to choose an approach that best fits that organization. This exercise will test your understanding of these pros and cons.

**Instructions**

Place the comment into either to the top-down or bottom-up bucket.

| Top-down | Bottom-up |
| -------- |---------- |
| It was popularized by Bill Inmon and is often also called the Inmon approach | It was popularized by Ralph Kimball and is often also called the Kimball approach |
| Uses normalization to store data | It has the disadvantage of increased ETL processing time because it uses denormalization |
| Has data flowing into the data warehouse and then to the data marts | Has the data flowing into the data marts and then to the data warehouse |

> Congratulations! This exercise was challenging. Understanding the advantages and disadvantages of the different architectural approaches is important.

<br>

## Choosing a top-down approach
In this exercise, imagine you work as a data warehousing consultant engaged with Northwestern insurance company. The company has seen much growth over time and wants to consolidate systems into a data warehouse. The company must connect the data from one department to all other departments and avoid data duplication, creating a single source of truth. Also, they would like to minimize the data storage size if possible. Finally, Northwestern's management wants a smooth implementation and would prefer the project team take the time needed to get it right the first time.

Select the answer that best explains why you might select a top-down approach. Select one answer.

- [x] The top-down approach requires the organization to create the data definitions first, allowing them to connect the data with different parts of the organization and avoid duplicate data.
- [ ] Since they are building the data marts first, they can deliver reporting and business value quickly.
- [ ] Due to the data being stored in a denormalized form, it will minimize the data storage size.

> Perfect! The upfront planning in a top-down approach of all the organization's data will help ensure that the data warehouse becomes an organization's single source of truth. Also, management has expressed that they will give the time needed for the project to start. All of these work well with a top-down approach.

<br>

## The OLAP data cube
The OLAP data cube is essential for OLAP systems. OLAP systems help support organizational decision-making by supporting large-scale data analysis.

Select the **true** statement about the OLAP system data cube. Select one answer. 

- [ ] The OLAP data cube only stores data in two dimensions, in rows and columns, for fast processing.
- [x] OLAP data cube with user data within the New York Times newspaper could process a metric like the number of users by country, subscription type, and year.
- [ ] The OLAP data cube only allows users to drill down on different data dimensions and not aggregate the values.
- [ ] The OLAP data cube is limited to only three dimensions.

> Great work! The OLAP cube can process data in multiple dimensions, which supports analysts and decision-makers interested in analyzing the organization's data.

<br>

## OLAP vs. OLTP scenarios
In the last video, you learned that OLAP and OLTP systems are optimized for different workloads. This exercise reviews the different hypothetical scenarios and chooses if the OLAP or OLTP system is best optimized for that scenario.

**Instructions**

Drag the different scenarios into the correct bucket.

| OLAP | OLTP |
| ---- | ---- |
| Finding which salesperson had the highest total sales last month | Updating a row of data in the database when a passenger wants to be picked up for a ride-sharing service |
| Summarizing each day last month, what was the last order number shipped that day| Recording when an order has been picked up for a food delivery service |
| Determining the total sales of the North-western sales department in the previous year | Tracking in the database when a customer places a new order |

> Congratulations! Analytical queries summarize data over multiple transactions, and OLAP systems are optimized for analytical queries. Data warehouses are used to analyze and summarize an organization's historical data, and they use OLAP systems to help with this process.

<br>

## Understanding OLTP
Select the true statement about OLTP systems. Select one answer.

- [ ] OLTP systems process data in multidimensional cubes to update the database quickly
- [ ] Analysts often use OLTP systems to analyze vast amounts of data
- [x] OLTP systems are designed to process large volumes of simple queries quickly

> Awesome! OLTP systems are designed to process queries quickly to keep the database up to date for fast-moving processes like credit card transactions.
