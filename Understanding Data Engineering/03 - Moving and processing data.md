## Connect the dots
Data pipelines are used to process data. At the end of Chapter 1, you learned about ETL (Extract, Transform, Load), one of the frameworks used to build data pipelines. The data processing tasks you just studied actually match that framework, corresponding to either extraction, transformation or loading operations.

Note that although saving and loading are usually considered to be opposites, in the context of data engineering, they are the same thing, as you may have noticed. The reason for this is that when you're saving something, you're just storing it in the next step in the pipeline.

Can you correctly classify data processing tasks as extraction, transformation, or loading operations?

**Instructions**

Classify the operations as Extract, Transform or Load operations.

| Extract | Transform | Load |
| ------- | --------- | ---- |
| Collecting data from Google Analytics about our web-marketing promotion offering 3 months of access to the premium tier. | Summarizing the yearly listening activity to tell users how many hours they've listened to music on Spotflix this year. | Saving the new order of a playlist that was sorted based on the date songs were added, so that it remains that way the next time the user connects.|
| Pulling the top 20 songs users have been listening to on a loop. | Sorting a playlist's songs based on the date they were added. | Writing all the followers of a user in a table. |

> Great job connecting the dots! As you can see, most of the data processing steps are transformation steps including selecting, encoding, calculating new values, sorting and ordering, joining data from multiple sources, aggregating, pivoting tables, splitting one table into several ones, removing duplicate values. Depending on the context, validating data can be considered part of the extract step (you don't extract if it's not necessary), or the transform step (you check that your results make sense before saving them). OK, now that you know about processing tasks, let's see how to schedule them!

<br>

## Schedules
You just saw three ways of scheduling data: manually, at a specific time, or if a specific condition is met.

Can you correctly classify the following actions?

**Instructions**

Correctly classify the actions as being run manually, at a specific time, or if a specific condition is met.

| Manual | Time | Condition |
| ------ | ---- | --------- |
| Running the song encoding pipeline, because engineering changed the encoder and wants to make sure they still pass the validation check. | Collecting data from Google Analytics every morning to check how the promotion campaign is going. | Updating the number of followers in a playlist table after a user subscribed to it. |
|  | Processing music videos uploaded by artists every hour. |  |
|  | Generating the Spotflix Weekly Playlist from Chapter 1 every Monday at 00:00 AM. |  |

> Excellent! You definitely know how to schedule data processing tasks, what the different types of schedules are, and when they are appropriate. Let's go to the next exercise to see how well you understand batching and streaming!

<br>

## One or the other
You've seen that data can be processed in batches (records are grouped and processed at intervals) or streams (records are sent individually right away).

Can you correctly classify the following actions as being batched or streamed?

Some of these are tricky, you may have to think twice! Don't worry if you don't get it right the first time. All that matters is that you get the difference between batches and streams, so if you make a mistake, make sure to read the orange feedback messages at the bottom left to understand why!

**Instructions**

Correctly classify the actions as being batched or streamed.

| Batch | Stream |
| ----- | ------ |
| Loading new employees to Spotflix's employee table. | When a user listens to songs that are being recommended in real time, loading his upvotes and downvotes on each song. |
| Reducing access to premium features when someone unsubscribes. | Updating the count of followers in a playlist when a user subscribes to it. |

> OK! Once again, don't worry if you got some of it wrong. What matters is that hopefully, you now understand why these situations were categorized the way they were. In a nutshell, batch processing can be scheduled when resources aren't being used elsewhere, which makes it cheap. Stream processing, on the other hand is used if you need the latest data: the urgency of showing the latest data help you decide if you need it. Onwards to parallel computing!

<br>

## Whenever, whenever
While you're having lunch with the rest of the data science team, Sasha, the new data engineer intern, is telling you this: "Parallel computing is a jack of all trades and can be used whenever we want, for any task we want. It just optimizes running any data processing tasks. We should start implementing it across the whole pipeline. I'm ready to help do it!"

Is her statement actually true or false? Select one answer

- [ ] True
- [x] False

> Yup! This statement is wrong. It's OK: interns are here to learn, and we appreciate her passion and proactiveness!

<br>

## Parallel universe
You just told Sasha, the data engineer intern, that although incredibly efficient and powerful, parallel computing is not suited to every situation. It has its limitations, and sometimes it's just unnecessary.

You would like to help Sasha improve her understanding. You ask her to share her assumptions about parallel computing: you will tell her if she's right or wrong, and try to explain why. Are you up to the challenge?

**Instructions**

Classify the statements as either right or wrong.

| Right | Wrong |
| ----- | ----- |
| Parallel computing relies on processing units. | Parallel computing will always make things faster. |
| Parallel computing is used to provide extra processing power. | Parallel computing can't be used to optimize for memory usage. |
| It's a good idea to use parallel computing to encode songs uploaded by artists to the .ogg format that Spotflix prefers. | It's a good idea to use parallel computing to update the employees table every morning. |

> Great job helping Sasha improve. You're really getting the hang of this! OK, let's get to the last topic of this course: cloud computing!

<br>

## Obscured by clouds
Sasha, the new data engineer intern, is now trying to convince you that cloud computing and multicloud computing have absolutely no downsides. You disagree: you know for a fact that this is not true. It makes you question whether or not she is actually comfortable with the topic.

Once again, you take your manager role to heart and try to help her improve her understanding. You ask her to share her assumptions about cloud computing: you will tell her if she's right or wrong, and try to explain why. Are you up to the challenge?

**Instructions**

Classify the statements as either right or wrong.

| Right | Wrong |
| ----- | ----- |
| Leveraging the cloud instead of having our own on-premises data center allows us to use just the resources we need, when we need them. | Multicloud solutions reduce security and governance concerns. |
| Cloud computing encompasses storage, database and computing solutions. | EC2, S3 and RDS are solutions offered by Microsoft Azure. |
| A multicloud solution reduces reliance on a single vendor. | Cloud computing reduces all kinds of risk. |

> Well played! You've empowered your data engineer intern. Now, not only does she have a more nuanced point of view and knows she can come to you with questions, you also sense that your intern is better prepared for her job. One last exercise to check how well you know the different cloud providers and their respective solutions!

<br>

## Somewhere I belong
Spotflix's data engineers are worried about the company's reliance on a single vendor, and are considering a multicloud approach. They also think it might allow Spotflix to reduce costs, and to be more resilient in the face of a disaster.

As you've just seen, the main cloud providers are AWS, Microsoft Azure and Google Cloud. Together, they own about half of the cloud computing market share. They have different services, some you saw in the video, some you're about to discover. They also have competitors, some of which you're about to discover as well.

Can you help the data engineers classify the different services before they start evaluating alternatives?

**Instructions**

Correctly classify the cloud services solutions as either computing, or databases.

| Computing | Database |
| --------- | -------- |
| Azure Virtual Machines | AWS Redshift (data warehouse) |
| AWS EC2 | Snowflake Data Warehouse |
|  | Google Cloud Datastore (NoSQL) |

> Snowflake, founded in 2012, is disrupting the data warehouse industry and enjoyed a 174% revenue growth in 2019. That might be a name to remember! Alright, excellent job! In a couple hours, you went from wondering what data engineering is to being able to classify cloud solutions. Impressive! One last video and you're good to go!
