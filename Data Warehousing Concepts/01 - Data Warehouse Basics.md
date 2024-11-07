## Knowing the what and why
In the last video, we discussed **what** is a data warehouse, **what** it does, and **why** it is valuable to the organization.

Select the statement below that is **true**. Select one answer.

- [ ] A data warehouse cannot integrate data from different areas of an organization but must gather data from only one area
- [ ] Data warehouses enable organizational analysis and decision-making
- [ ] A data warehouse is not used for analysis but primarily to store and back up data from other critical systems
- [ ] Data warehouses are designed only to store the AI models of a data scientist or analyst

> Perfect! By bringing data together from different areas of the organization and storing it, data warehouses enable the analysis of that data to support organizational decision-making.

<br>

## Possible use cases for a data warehouse for Zynga
Companies are willing to invest a large amount of money into developing a data warehouse for the potential insights they can bring. For example, Zynga, the social video game company, said the following when submitting to become a publicly traded company.

> _While Zynga has generated positive operating cash flow since the fall of 2007, we raised hundreds of millions of dollars to maximize our ability to **make large investments** in teams, games, and **infrastructure**. For example, our Chief Technology Officer joined us in the fall of 2008 with a mission of building the **greatest data warehouse in the game industry**, which now processes 15 terabytes of game data every day. We will continue to make these big investments and big bets in pursuit of our mission._

Let's imagine how Zynga might use its data warehouse. Select the answer that is **not** a use case for how Zynga may have used its data warehouse. Select one answer.

- [x] For new game development, by allowing employees to store, track, and collaborate on the code for their latest game
- [ ] For Marketing and measuring its sales campaign effectiveness by connecting data from internal and external systems such as web analytics platforms and advertising channels.
- [ ] For team performance evaluations using metrics derived from the data warehouse to create customized dashboards or reports showing team performance.

> Great job! Data warehousing is a valuable field because companies are willing to invest money into it. In this exercise, we only guessed how Zynga used its data warehouse. However, companies use data warehouses to integrate internal and external data sources and track performance metrics, but they are not designed for code version control.

<br>

## Data warehouses vs. data lakes
The last video discussed how data warehouses and data lakes compare. It's time to review what you have learned!

**Instructions**

Drag the characteristics, attributes, or items into the Data Lake or Data Warehouse bucket, depending on which it best describes.

| Data Lake | Data Warehouse |
| --------- | -------------- |
| Can include unstructured data | Contains only structured data |
| Hold data the purporse of which is not yet determined | Holds data only where the purpose is known |
| Is less organized | Is relatively more complicated to change because of upstream and downstream impacts| 

> Awesome! The key takeaway is that organizations that want to store unstructured data might use a data lake, whereas those with only structured data might use a data warehouse.

<br>

## Data warehouses vs. data marts
In the last video you learned about some of the similarities and differences between a data warehouse and a data mart.

Select the statement that is true. Select one answer.

- [ ] A data mart is an organization-wide repository of disparate data sources, while a data warehouse is a subset of data focused on one area.
- [ ] A data mart typically stores data from multiple sources, compared to a data warehouse that typically stores data from just a few sources.
- [x] A data mart size is typically less than 100 GB compared to a data warehouse that is often 100 GB or more.

> Outstanding! Yes, a data mart tends to be smaller in size, has few data sources, and can contain a subset of data compared to a data warehouse.

<br>

## Deciding between a data lake, warehouse, and mart
You are performing some initial assessment for the hypothetical home office furniture company Bravo. The company is looking to invest in its data infrastructure.

From your initial interviews, you have learned that the company has multiple databases but no single data repository for analysis. Additionally, Bravo has confirmed that they are interested in storing unstructured data in this system, such as audio and video files. They expect many users of this data will have experience using sophisticated data tools to interface with the system. Finally, they estimate their current and future data needs will be about two terabytes (i.e.,>100 GB).

Based on this information, choose if Bravo should invest in a data warehouse, data mart, or data lake. Select one answer.

- [x] Select a data lake since they need to integrate over a terabyte of structured and unstructured data covering many different departments.
- [ ] Select a data mart since they need to integrate over a terabyte of structured and unstructured data covering many different departments.
- [ ] Select a data warehouse since they need to integrate over a terabyte of structured and unstructured data covering many different departments.

> Nice job! The data lake would fit the needs identified by Bravo, in particular, because they are also looking to store unstructured data. Sometimes a data warehouse is not the best tool.

<br>

## Data warehouse life cycle
There are many steps, from ideation to deploying a data warehouse, and it is valuable to understand the order of the different steps of the data warehouse life cycle. Each of the earlier steps helps support the later steps.

**Instructions**

Place the different life cycle steps in order, with the first step at the top of the list.

1. Bussiness Requirements
2. Data Modeling 
3. ETL Design & Development
4. BI Application Development
5. Test & Deploy

> Congratulations, you now see how the different substeps come together to create a data warehouse.

<br>

## Support where needed
Different personas are needed to support the creation and deployment of a data warehouse. Select the true statement about a persona and their involvement in the data warehouse life cycle. Select one answer

- [ ] Data Scientists support the ETL Design and Development step using machine learning modeling skills.
- [x] Data Analysts are needed in the Business Requirements step to help gather the organizational requirements of the data warehouse
- [ ] Database Administrators are needed during the BI Application Development step to coordinate access to the transactional databases.

> Great work! Data Analysts are close to the data and often perform different business analyses. Therefore, they are needed to assist with gathering the business requirements.

<br>

## Who does what?
You learned about different personas and their scope of involvement during different phases of the life cycle of a data warehouse. Use that knowledge to categorize the different scopes for each persona correctly.

**Instructions**

Place the statements in the correct category. Note that there may be a statement that fits both categories.

| Analysts | Data Engineer | Both |
| -------- | ------------- | ---- |
| Assist with collecting business requirements as they understand the organization's needs | Assist with creating the data pipelines during the ETL Design and Development step | Are needed during the Data Modeling step |
| Consult and help with the setup of BI reports during the BI Application Development step | Make changes to pipelines if needed during the Maintenance step |  |

> Congratulations! As we work through the different phases of a data warehouse's life cycle, having key personnel's support is vital to a successful warehouse implementation.
