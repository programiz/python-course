# Python if...else Statement

**Video link:** [https://youtu.be/497MClrekMY](https://youtu.be/497MClrekMY)

In this video, we learned about decision making in Python using the **if...else** statement.

**Programs in the Video**

- [Python if statement](#python-if-statement)
- [Python if...else statement](#python-ifelse-statement-1)
- [Python if...elif...else statement](#python-ifelifelse-statement)
- [**Task**: Check if number if positive, negative, or zero](#programming-task)

---

## Python `if` statement
In Python, we use the `if` statement to create programs that can make decisions. The syntax of the `if` statement is:

```
if test_condition:
    statement(s)
```

If `test_condition` is `True`, the body of the `if` statement is executed.

However, if `test_condition` is `False`, the body of the `if` statement is skipped from execution.

---

### Example: Check if student passed the exam

**Suppose you are a university student and to pass the examination you need to score 50 or more. Lets look at a program to
check if you passed the exam.**

```python
score = int(input("Enter a number: "))

if score >= 50:
   print("You have passed your exams.")
   print("Congratulations!")
```

**Output**

For a number greater than or equal to 50:
```
Enter a number: 75
You have passed your exams.
Congratulations!
```

Otherwise (number smaller than 50):
```
Enter a number: 35
```
As we can see, there is no output as the if block is skipped. We can add one more if statement to handle this as:

```python
score = 35

if score >= 50:
   print("You have passed your exam.")
   print("Congratulations!")

if score < 50:
   print("Sorry, you have failed your exam.")
```

**Output**

```
Sorry, you have failed your exam.
```

---

## Python `if...else` statement

The `if` statement can have an optional `else` clause to run when `test_condition` is `False`. The syntax of `if..else` is:

```
if test_condition:
    statement(s)
else:
    statement(s)
```

Now, we can simply write the above program as:

```python
score = 35

if score >= 50:
   print("You have passed your exam.")
   print("Congratulations!")
else:
   print("Sorry, you have failed your exam.")
```

___

## Python `if...elif...else` statement

The `if` statement can also have multiple `elif` clauses to handle more than two test cases.
The syntax of `if...elif...else` is:

```
if test_condition1:
    statements_1
elif test_condition2:
    statement_2
...
else:
    statements_3
```

The marks scored by a student is from 0 to 100. We can add the `elif` to above program to validate the marks entered as:

```python
score = 105

if score > 100 or score < 0:
   print("Score is invalid.")
elif score >= 50:
   print("You have passed your exam.")
   print("Congratulations!")
else:
   print("Sorry, you have failed your exam.")
```

**Output**

```
Score is invalid.
```

---

## Programming Task

**Can you create a program to check whether a number is positive or negative or 0?**

**To create this program, create a variable named `number` and assign a `float` value to it based on the user input.**
**Then using a if statement, check if the number variable is positive or negative or 0.**

* __If number is positive, print "The number is positive"__
* __If number is 0, print "The number is 0"__
* __If number is negative, print "The number is negative"__

```python
# Solution 1

number = float(input("Enter a number: "))

if number > 0:
    print("The number is positive")
elif number == 0:
    print("The number is 0")
else:
    print("The number is negative")
```


```python
# Solution 2

number = float(input("Enter a number: "))

if number > 0:
    print("The number is positive")
elif number < 0:
    print("The number is negative")
else:
    print("The number is 0")
```

```python
# Solution 3: Using Nested if else

number = float(input("Enter a number: "))

if number >= 0:
    # At this point, number is either 0 or a positive number
    if number > 0:
        print("The number is positive")
    else:
        print("The number is 0")
else:
    print("The number is negative")
```
