## Go with the flow
To understand what data engineers do, why they are necessary and the impact they have, you need to know how data flows through an organization.

Can you order the four steps of the data science workflow chronologically?

**Instructions**

Order the steps on chronologically (the step happening first should be at the top and the step happening last at the bottom).

1. Data collection and storage
2. Data preparation
3. Exploration and visualization
4. Experimentation and prediction

<br>

## Not responsible
You recently joined the data science team as a manager for a music streaming company named Spotflix. It's a music platform that lets users stream songs, create playlists, follow artists, watch music videos and even look up lyrics!

One of your colleagues just walked to your desk. They just got hired, but they already know you're on the data team - after training with DataCamp, you've made a name for yourself pretty quick! They have a bunch of data tasks they need completed, and they want to make sure they ask the right person. You tell them you can help them identify what they should request from data engineers, and what they should not.

Can you deliver on this promise?

**Instructions**

Here are several tasks related to working with data. Classify them in two buckets: one for data engineering tasks, one for tasks that are not the responsibility of data engineers.

| Data engineering taks | Not data engineering tasks |
| --------------------- | -------------------------- |
| Gathering music consumption data from desktop and mobile sources. | Based on their listening behavior, predict which songs customers are likely to enjoy.|
| Optimizing the customers databases for analysis. | Building a visualization to understand listening patterns by city. |
| Ensuring corrupted, unreadable music tracks are removed and don't end up facing customers. | Running an experiment to identify the optimal search bar positioning in the app. |

<br>

## Big time
You saw how the advent of big data increased the demand for data engineers. As more data gets generated, at a higher rate, with a growing variety of formats, the need for people able to manage this data is soaring.

Which of the following statements are true, and which are false?

**Instructions**

Classify the statements as either true of false.

| True | False |
| ---- | ----- |
| Value refers to how actionable the data is. | Velocity refers to how big the data is. |
| Data types refer to the variety of the data. | Volume has to do with how trustworthy the data is. |
|  | Veracity refers to how frequently the data is generated. |

<br>

## Tell me the truth
In 2012, IBM declared that 90% of the data in the world had been created in the past 2 years. That same year, the amount of digital data in the world first exceeded 1 zetabyte (1 billion terabytes). In 2020, we're expected to reach 44 zetabytes. This big data era led to the advent of two new roles: data engineers and data scientists. You just studied the differences between these two roles.

Let's have a quick sanity check: which of the following options is true? Select one answer

- [ ] Data engineers intervene at the very end of the data workflow.
- [ ] Data scientists build pipelines.
- [ ] Data engineers need strong statistical expertise.
- [x] Data engineers enable data scientists.

<br>

## Who is it
In the first lesson, you classified some data related tasks between data engineer tasks and not data engineer tasks. Let's raise the bar and see if you can assign more specific tasks to data engineers or data scientists.

**Instructions**

Assign the tasks to the data engineer or the data scientist.

| Data engineer | Data scientist |
| ------------- | -------------- |
| Provide listening sessions data so it can be analyzed with minimal preparation work. | Identify which customers are likely to end their Spotflix subscriptions, so marketing can target them and encourage them to renew. |
| Ensure that people who use the databases can't erase music videos by mistake. | Use Python to run an analysis on whether users prefer having the search bar on the top left or the top right of the Spotflix desktop app. |
| Use Java to build a pipeline collecting album covers and storing them. | Find out in which countries certain artists are popular to give them insights on where to tour. |

<br>

## It's not true
The main objective, when setting up data pipelines, is to improve the efficiency with which data flows, from its ingestion to the final users.

Most of the options below are true, but one is false. Which one is it? Select one answer

- [ ] Data pipelines ensure an efficient flow of the data through the organization.
- [ ] Data pipelines automate data extraction.
- [x] Data pipelines necessarily include a transformation step.
- [ ] ETL stands for Extract, Transform, Load.

<br>

## Pipeline
Once you've successfully completed this exercise, make sure to read the success message! 🎶😉

You've just seen some examples of pipelines used at Spotflix. Let's have you build one!

Our data engineer, Vivian, is working on building new pipelines to generate a new product: the Weekly Playlist. It's a playlist that is created by our system every day to recommend new songs that users might like based on their tastes.

In this exercise, you will find some steps. Can you order the steps correctly to help her build the pipeline generating a Weekly Playlist for each user? Let's start with one user, and build a pipeline to generate a Weekly Playlist for Julian, our data scientist.

**Instructions**

Order the steps chronologically (the step happening first should be at the top and the step happening last at the bottom).

1. Extract the songs Julian listened to the most over the past month
2. Find other users who listened to these same songs a lot as well
3. Load only the 10 top songs these users listened to the most over the past week  into a table called "Similar profiles"
4. Extract only songs these other users listen to that are of the same genre as the ones in Julian's listening sessions. These are our recommendations.
5. Load the recommended songs into a new table. That's Julian's Weekly Playlist!
