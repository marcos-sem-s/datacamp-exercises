## The benefits of Python
You saw in the video that Python is a very popular programming language. Can you remember why it is so popular? Select all correct answers

- [x] Uses natural language that is easy to understand
- [x] Applicable for a variety of use cases
- [ ] Fast code execution speed
- [x] Open source

> Great work! While Python is not as fast as programming languages such as C or C++, it is versatile, easy to interpret, and used by many people throughout the world who share their code for others to use too!

<br>

## Use-cases for Python
Python's versatility makes it an appropriate programming language for a variety of use cases. Can you identify which of the following products and tasks would be suitable for building using Python?

**Instructions**

Choose whether the product or task is suitable for development using Python or another programming language.

| Python | Other languages |
| ------ | --------------- |
| To teach programming | Hardware programming |
| Recommendation engines | Mobile apps |

> Nicely done. While Python has a broad range of use cases, sometimes other languages are more appropriate such as Javascript for interactive websites or Swift for mobile apps. Now let's look at how you can run Python code!

<br>

## Working with Python files
The DataCamp exercise interface includes several sections, one of which is used to run Python files.

Can you identify which of the following are valid Python file names? Select all correct answers

- [x] script.py
- [ ] script.txt
- [ ] script.code
- [x] calculator.py

> Nicely done! Python files, just like other file types, can have any file name, but common examples include script.py, main.py, app.py, and run.py.

<br>

## Python as a calculator
Working with numbers and performing calculations are very common tasks when programming. In this exercise, you'll need to perform a variety of calculations!

Feel free to use the IPython Shell to test out some calculations and, when you're ready, fill in the `script.py` by replacing the scaffolding `____` with your code.

**Instructions**

- Print the sum of 19 + 17.
- Print the result of subtracting 12 from 99.
- Multiply 27 by 23.
- Divide 99 by 12.

``` python
print(19 + 17)

print(12 - 99)

print(27 * 23)

print(99 / 12)
```

> Perfect! Python can help you do the math, a characteristic that will be helpful for a variety of tasks when building software or automating tasks!

<br>

## Advanced calculations
Python makes it possible to perform more challenging calculations, such as exponentiation and modulo. In this exercise, you'll make advanced calculations and print their results.

**Instructions**

- Print the result of nine-squared.
- Find the remainder of dividing 337 by 27.

``` python
print(9 ** 2)

print(337 % 27)
```

> Cracking calculations! So far you've worked with numbers, but what if you want to store information and refer to it later? Let's find out how to do this in the next video!

<br>

## Naming conventions
There are several common approaches used when naming variables, Pascal Case, Camel Case, and Snake Case. Can you identify which approach these variables are using, as well as identify invalid variable names?

**Instructions**

Classify each variable into the appropriate bucket depending on how it is named.

| Pascal Case | Snake Case | Invalid Name |
| ----------- | ---------- | ------------ |
| `DayOfWeek = "Friday"` | `account_balance = 4320.91` | `day of week = "Friday"` |
| `AccountBalance = 4320.91` | `day_of_week = "Friday"`  | `Account Balance = 4320.91` |

> While both snake case and camel case are valid approaches and will work in Python, it's important to be consistent in how you name your variables. Time to create your own!

<br>

## Checking data types
Python makes our life easier by inferring the type of data we are working with, avoiding the need for us to explicitly declare the data type!

Let's practice checking the data type of different values and variables. Two variables, current_quarter and revenue_on_target have been created and their values printed in the IPython Shell. These variables are available to use in script.py.

**Instructions**

1. Print the data type of the current_quarter variable.

``` python
print(type(current_quarter))
```

2. Print the data type of the value 9.75.

``` python
print(type(9.75))
```

3. Print the data type of the revenue_on_target variable.

``` python
print(type(revenue_on_target))
```

> Terrific type checking! We will learn through the course that specific tasks are possible depending on the data types we are working with, such as calculations, or conditional filtering, so knowing the type of data we are working with is extremely important.

<br>

## Working with variables
Variables allow you to store information to refer back to later, such as customer information and timestamps of events. You can also modify the values that are assigned to these variables if circumstances change!

**Instructions**

- Create a string variable called `name`, setting it equal to `John Smith`.
- Create an integer variable called `age` with a value of `47`.
- Create a string variable called `address` with a value of `The Shard, London, SE1 9SG`.
- Print the three variables.

``` python
name = 'John Smith'

age = 47

address = 'The Shard, London, SE1 9SG'

print(name, age,  address)
```

> Valuable variable creation skills! Storing information in this way makes it easier to scale your script as you can refer to variables rather than having to write out information or perform calculations from scratch.

<br>

##

> Checking and updating conditions
Boolean values can be used to check whether a condition has been satisfied, such as whether mandatory information has been submitted via a website or if a payment has been processed successfully.

Additionally, variables are not necessarily static, they can change over time like a customer changing their bank account details.

Here, you'll work with John Smith's data from the previous exercise, adding another variable along with updating his information.

**Instructions**

- Based on John's age, create a variable called `is_adult` and assign a value of `True` or `False`, reflecting whether John is an adult or not.
- John has upgraded his accommodation - change his `address` to `Buckingham Palace, London, SW1A 1AA`.
- Print John's `address` and `is_adult` variables.

``` python 
age = 47

is_adult = True

address = 'Buckingham Palace, London, SW1A 1AA'

print(address, is_adult)
```

> Excellent! The more information you work with, the more important variables become! In the next chapter, you'll see how we can work with lots of information in individual variables using different data types. See you there!
