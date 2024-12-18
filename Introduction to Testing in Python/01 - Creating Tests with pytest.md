## The first test suite
In this exercise, you will write the first test suite that includes the types of tests that you have learned using the `pytest` library.

The function `multiple_of_two` checks whether the `num` is a multiple of `2` or not. You will implement and run two regular `assert` tests.

The `pytest` package has already been imported.

**Instructions**

1. Write an `assert` statement that is expected to be `True`.
2. Write an `assert` statement that is expected to be `False`.

``` python
def multiple_of_two(num):
    if num == 0:
  raise(ValueError)
    return num % 2 == 0

def test_numbers():
    assert multiple_of_two(4) == True
    assert multiple_of_two(3) is False
```

> Perfect! This basic functionality gives you almost unlimited capabilities in test creation. Now you know how to create your own test suites!

<br>

## pytest.raises
In this exercise, you will continue writing the first test suite using the `pytest` library.

The function `multiple_of_two` checks whether the `num` is a multiple of `2` or not. In this exercise, you will implement a test that expects to raise an `Exception`.

The `pytest` package has been imported.

**Instructions**

- Define a **context manager** for the exception test.
- Write a test to check that the zero input multiple_of_two(num=0) results in the ValueError exception.

``` python
def multiple_of_two(num):
    if num == 0:
  raise(ValueError)
    return num % 2 == 0

def test_zero():
    with pytest.raises(ValueError):
  multiple_of_two(0)
```

> Yes! Knowing what exactly you can not do and checking it with `pytest.raises` is always good.

<br>

## Run the test!
Yay! Your `pytest` test suite is ready to be launched. Now you will enter a simple command to run the test suite you developed in the previous exercise. Let's run the tests via the command-line interface.

A quick overview of the exercise: you can find the exercise instructions below this section, the `run_the_test.py` script on the right, and the **terminal** at the bottom (below the script).

**Ide Exercise Instruction**

- Add import of the `pytest` library to the code.
- Enter the pytest `run_the_test.py` command to CLI and press **Enter**.
- Press the "Submit Answer" button at the end.

``` python
import pytest

def multiple_of_two(num):
    if num == 0:
  raise(ValueError)
    return num % 2 == 0

def test_numbers():
    assert multiple_of_two(2) is True
    assert multiple_of_two(3) is False

def test_zero():    
    with pytest.raises(ValueError):
  multiple_of_two(0)
```

```
pytest run_the_test.py
```

> Great job on your first IDE exercise! Your first test suite works!

<br>

## Run with the keyword
Sometimes you want to run only the tests with a certain name (assuming that the names of the tests are meaningful). In this exercise, you will practice running tests with keyword selection. To be accurate, you have to run only the tests containing the word "numbers".

**Ide Exercise Instruction**

- Add import of the `pytest` library to the code.
- Execute the `pytest` command to run `run_the_test.py`, specifying the keywords as `"numbers"`.
- Press **Enter**.
- Press the "Submit Answer" button at the end.

```
pytest run_the_test.py -k 'numbers'
```

> That works! It can be useful to select certain tests using their names. For example if you have a lot of tests and you want to save some time on the tests that already passed.

<br>

## Markers use cases
Now, you will practice deciding what markers to use in a specific task. This is exactly how you can use `pytest` in real-life projects. Here you have to assign the tasks to one of the markers below.

**Instructions**

Decide what marker to use for the specific task by dropping a task on a marker.

| @pytest.mark.skip | @pytest.mark.xfail | @pytest.mark.skipif |
| ----------------- | ------------------ | ------------------- |
| Skip the test no matter what. | To verify that the test checking 'a' + 'b' != 'ab' will fail. | To skip the test if Python version is less than `3.4.x`. |
| A test should be skipped indefinitely until the mark is removed. | To verify that the test fails.| To check the condition and skip the test if it is `True`. |

> Well done on the first markers exercise! Choosing an appropriate marker for your test usually saves you a lot of time.

<br>

## Failed tests with xfail
In this exercise, you will use `pytest` markers for the first time in order to specify the behavior of the test. You have already seen the function `multiple_of_two`, which checks whether the `num` is a multiple of `2` or not. The `pytest` library was already imported for you.

**Instructions**

- Add the correct `pytest` marker for a test that is expected to fail.
- Write any `assert` test that is expected to fail.

``` python
def multiple_of_two(num):
    if num == 0:
        raise(ValueError)
    return num % 2 == 0

@pytest.mark.xfail
def test_fails():
    assert multiple_of_two(2) == 3
```

> You did it! You can use failed tests to prevent unexpected behavior of your program. In the next exercise, you will deal with the conditional skipping.

<br>

## Conditional skipping
Sometimes, you want to skip a test if some condition is met. For example, you want to conduct a test unless today is Saturday. In this case, you can use the `datetime` library for getting the current day of the week and the `pytest` marker for conditional skipping the test function. To pass a condition to the conditional skipping `pytest` marker, you can use `@pytest.mark.skipif(condition)` The `pytest` library was already imported for you.

**Instructions**

- Add the "conditional skip" decorator to make it work.
- Add the `condition_string` into the decorator call.
- Complete the assertion tests.

``` python
day_of_week = datetime.now().isoweekday()

def get_unique_values(lst):
    return list(set(lst))

condition_string = 'day_of_week == 6'
@pytest.mark.skipif(condition_string)
def test_function():
    assert get_unique_values([1,2,3]) == [1,2,3]
    assert get_unique_values([1,2,3,1]) == [1,2,3]
```

> Congratulations on finishing Chapter 1! You learned about how to create tests with pytest, how to run them from CLI, and how you can use pytest markers to save your time. In the next chapter you will learn how to automate the environment preparation with pytest fixtures.
