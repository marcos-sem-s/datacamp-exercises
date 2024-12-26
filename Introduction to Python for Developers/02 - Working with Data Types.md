## Multi-line strings
You have a friend who works at an e-learning company called LLM Camp, where they teach people how to work with large language models (LLMS).

They want to use Python to store their user reviews and you've volunteered to help set this up! They've provided two of their most recent reviews:

```
# review_one
I really enjoy the courses,
and they are easy to fit into my busy schedule. 
I wish I had started using your platform sooner.
I'll be recommending you to my friends!!
# review_two
One year ago, I was unsure of how to make progress in my career. 
Now, I work as a Prompt Engineer, and I can't thank you enough! 
Keep up the great work.
```

**Instructions**

- Store the first review as a multi-line string variable called `review_one`.
- Store the second review as a multi-line string variable called `review_two`.
- Print `review_one` then print `review_two`.

``` python
review_one = """I really enjoy the courses,
and they are easy to fit into my busy schedule. 
I wish I had started using your platform sooner.
I'll be recommending you to my friends!!"""

review_two = """One year ago, I was unsure of how to make progress in my career. 
Now, I work as a Prompt Engineer, and I can't thank you enough! 
Keep up the great work."""

print(review_one)
print(review_two)
```

> Magnificent multi-line strings! Your friend is very grateful for your assistance.

<br>

## Modifying string variables
You did so well working with LLM Camp's reviews that they've asked for your help again.

They have a variable called `most_popular_course`, which contains the name of their highest-ranked course. It has been provided in `script.py` so you can see its contents. However, there are issues with it:

There's a typo. It should be `"Introduction"` rather than `"Intro"`.
They want to remove spaces and use underscores to make it easier to analyze.
For consistency, they want all characters to be lowercase.
They'd like your support in making these changes!

**Instructions**

1. Update the variable so that `"Intro"` now reads `"Introduction"`.
2. Swap spaces to underscores throughout the string contained in `most_popular_course`.
3. Update `most_popular_course` so that it only contains lowercase characters.

``` python
most_popular_course = "Intro to Embeddings with the OpenAI API"

most_popular_course = most_popular_course.replace("Intro", "Introduction")

most_popular_course = most_popular_course.replace(" ", "_")

most_popular_course = most_popular_course.lower()

print(most_popular_course)
```

> Excellent editing! In a few lines of code, you've transformed a string variable by replacing a word, swapping spaces to underscores, and converting to lowercase. Strings are easiest to work with if they follow a consistent format, so these techniques will serve you very well!

<br>

## Building a party playlist
You're planning a party and want to build a playlist containing songs and the order in which they should be played.

You decide this is a great opportunity to build a list in Python! In this exercise, you will create your `playlist` variable and add the first three songs.

**Instructions**

Create a list variable called `playlist`, containing the following numeric and string values (in order):
`1`, `"Blinding Lights"`, `2`, `"One Dance"`, `3`, `"Uptown Funk"`.
Print the list.

``` python
playlist = [1, "Blinding Lights", 2, "One Dance", 3, "Uptown Funk"]

print(playlist)
```

> Tunes! Do you see how useful lists are for storing a variety of information? Now let's look at how to extract information from them.

<br>

## Subsetting lists
You've expanded your `playlist`. It still contains the song order and song names, but now you've also added the artist name for each song, as well as some additional songs!

It repeats the same order throughout the list - 1) song number, 2) song name, 3) artist name, repeat.

The new `playlist` has been printed in the IPython Shell for your reference.

This is a great opportunity for you to practice extracting specific information from your list.

**Instructions**

1. Find the name of the second song, which is the fifth element, in the `playlist`, and print the value.

``` python
print(playlist[4])
```

2. Print the name of the artist for the final song in the `playlist`.

``` python
print(playlist[-1])
```

3. Print every song name in the `playlist`.

``` python
print(playlist[1::3])
```

> Impressive indexing! Using square brackets to subset variables is incredibly common in Python programming, so this skill will be useful to continue your coding journey.

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

## 

> 

<br>

