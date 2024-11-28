## Motivating visualization
To get an insight from a dataset, you can calculate summary statistics or run statistical models, but often it's easier to draw a plot.

In this exercise, you can see the price of the Bitcoin cryptocurrency from the start of 2016 to the start of 2020. Columns in the table are filterable and sortable.

Look at the Bitcoin prices on January the first each year. Which year began with the highest Bitcoin price?

Data Source: [Coindesk](https://www.coindesk.com/price/bitcoin)

**Instructions**

- [ ] 2016
- [ ] 2017
- [x] 2018
- [ ] 2019
- [ ] 2020

![alt text](imgs/image01.png)

> Perfect price plot probing! Often, looking at a plot is a quicker way to answer questions than poring through data.

<br>

## Continuous vs. categorical variables
In order to choose an appropriate type of plot to draw, you need to be able to distinguish between continuous variables (roughly: "things you can do arithmetic on") and categorical variables (roughly: "things that can be classified").

**Instructions**

State which of these variables are continuous and which are categorical.

| Continuous | Categorical |
| ---------- | ----------- |
| Salary of employees | Was the exam passed or failed? |
| Population of towns in Canada | Job title of employees |
| Mass of squirrels | Provinces of towns in Canada |

> Classy classification! The distinction between continuous variables (numbers) and categorical variables (text) is important when deciding what kind of plot to draw.

<br>

## Interpreting histograms
Here is a histogram of salaries for various jobs in Australia. Each row of the dataset is the average salary for that job, so the counts are counts of jobs.

![A histogram of Australian salaries](imgs/image02.png)

Tip: This left-hand pane of the exercise containing text and instructions is resizable. If the plot is too small to see clearly, making the pane wider will increase the plot size. Move your mouse in-between the left-hand pane and the drag and drop portion of the exercise so a gray vertical bar appears. In Chrome, click and drag this bar to the right. In Firefox, click the bar, move your mouse right, then click again.

Data Source: [Tidy Tuesday](https://github.com/rfordatascience/tidytuesday/blob/master/data/2018/2018-04-23/week4_australian_salary.csv)

**Instructions**

Categorize these statements about the histogram as true or false.

| True | False |
| ---- | ----- |
| The most popular salary bracket is $40k to $60k. | The histogram is left-skewed. |
| The histogram is right-skewed. | The histogram is bimodal. |
| The histogram is unimodal. | The most popular salary bracket is $560k to $580k. |

> Hooray for histograms! Counting the number of peaks, assessing the skewness (lack of symmetry), and identifying the most popular areas are useful things to look at when interpreting a histogram.

<br>

## Adjusting bin width
The appearance of a histogram is heavily influenced by the width of its bins: the intervals that determine where each bar lies on the x-axis. If the bins are too wide, you don't see enough detail in the shape of the distribution. If the bins are too narrow, the distribution can be obscured by noise. It's very difficult to know the "best" binwidth, until you physically look at the plot: draw lots of histograms with a range of binwidths until you find one that helps you answer the question.

![An agouti eating seeds](image.png)

Here you can see a histogram of agouti (a rodent) sightings from a camera trap on Barra Colorado Island in Panama. When an animal passed the camera, a photo was taken with a timestamp, so the histogram shows the distribution of the time of day when the agouti were most active.

**Which of these statements about the agouti activity is true?**

Data Source: [Rowcliffle et al. 2014](http://dx.doi.org/10.6084/m9.figshare.1160536)

**Instructions**

- [ ] The agouti had a high level of activity from 4am to 12pm, then moderate activity from 12pm to 8pm.
- [x] The agouti were most active for a couple of hours after sunrise (6:30am to 8:30am), and before sunset (4pm to 6m).
- [ ] The agouti showed a constant level of activity throughout sunlight hours.
- [ ] The agouti activity was highly variable, with over a dozen peaks in activity throughout the day

![alt text](image-1.png)
 
> Brilliant binwidth adjustment! Choosing an appropriate binwidth make it easier to interpret the histogram.

<br>

## Interpreting box plots
Here are box plots of cigarette consumption per person in the USA from 1985 to 1995 (Alaska and Hawaii are not included). Each observation in the dataset is the average number of packets of cigarette smoked per person in one state in one year. Thus each box plot represents the distribution of 48 data points (because there are 48 US states included in the dataset).

![Box plots of cigarette consumption per capita in the USA, from 1985 to 1995.](image-2.png)

Data Source: [Stock, James H. and Mark W. Watson (2003)](https://www.rdocumentation.org/packages/Ecdat/topics/Cigarette)

**Instructions**

Categorize these statements about the box plots as true or false.

| True | False  |
| ---- | ------ |
| In 1990, three states were considered to have extreme values in the number of packets of cigarettes smoked per capita. | The inter-quartile range of the number of packets of cigarettes smoked per capita was smallest in 1992. |
| The median number of packets of cigarettes smoked per capita was below 100 from 1991 onwards. | The inter-quartile range of the number of packets of cigarettes smoked per capita decreased every year from 1985 to 1995. |
| The lower quartile number of packets of cigarettes smoked per capita decreased every year from 1985 to 1995. | The upper quartile number of packets of cigarettes smoked per capita decreased every year from 1985 to 1995. |

> Beautiful box plots! Although each box plot contains less information than a histogram, because they are so compact to draw, it is easy to compare many distributions at once.

<br>

## Ordering box plots
How you order the box plots affects the kinds of questions that are easy to answer.

Here you can see the US cigarette consumption dataset again. This time each box plot represents the distribution of cigarette consumption over time for a given US state. Thus each box plot is formed from 11 data points representing 1985 to 1995.

By default, the box plots are ordered alphabetically by state name. This makes it really easy to look up the details for a specific state, but difficult to answer questions about where the highest or lowest consumption can be found. Sorting the rows by median cigarette consumption makes those questions easier to answer.

Inter-quartile range (IQR) measures the variation in the "middle half" of the population (from the 25th percentile to the 75th percentile). That means that sorting by the IQR makes it easier to answer questions about how much variation there was among the "typical" population.

Which statement is false?

**Instructions**

![US State](image-3.png)
![Median cigarette consumption (packs/capita/year)](image-4.png)
![IQR cigarette consumption (packs/capita/year)](image-5.png)


- [ ] The lower whisker for Alabama is completely above 100 packs/capita/year.
- [ ] North Carolina has the fourth highest median consumption.
- [ ] New Hampshire has the third widest inter-quartile range of consumption.
- [x] Idaho has the fourth lowest median consumption.

> Awesome ordering! There is no single “best” way to order the box plots. Different orderings make it easier to answer different questions.
