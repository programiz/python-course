# Python Functions

**Video link:** [https://youtu.be/-Bkupx9gX0o](https://youtu.be/-Bkupx9gX0o)

In this video, we learned about Python functions that make our program more organized and manageable by dividing our code into smaller and modular chunks.

**Programs in the Video**

- [Python Functions](#python-functions-1)
- [Function Arguments](#function-arguments)
- [Passing Multiple Arguments](#passing-multiple-arguments)
- [Return Value from Function](#return-value-from-function)
- [**Example**: Grading Students](#example)
- [**Task**: Function to Add and Multiply](#programming-task)

---
## Python Functions
A function is a group of related statements that performs a specific task.

For example,

```python
def greet():
    print("Hello")
    print("How do you do?")
```
Here, we have defined a function named `greet`.

To create a function, we use the `def` keyword followed by the function name, parenthesis `()`, and a colon `:`.
The body of the function is specified using indentation.

When we run the program, we don't see any output.

It is because defining a function won't do anything. To bring the function into action, we need to call it.

```python
def greet():
    print("Hello")
    print("How do you do?")

greet()
```

**Output**

```
Hello
How do you do?
```

One advantage of defining a function is that we can call it any number of times.

```python
def greet():
    print("Hello")
    print("How do you do?")

greet()
greet()
greet()
```

**Output**

```
Hello
How do you do?
Hello
How do you do?
Hello
How do you do?
```

Also, we need to define a function first before we can call it.

The following code gives an error:

```python
# function call
greet()

# function definition
def greet():
    print("Hello")
    print("How do you do?")
```

When the `greet()` function is called, Python doesn't know that this function exists because it's defined after the function call.

---

## Function Arguments

Suppose we want to make our `greet()` function a bit more personal.

Instead of printing `Hello`, we want to print something like `Hello Jack` or whatever the person's name is.

For this, we can use function arguments:

```python
def greet(name):
    print("Hello", name)
    print("How do you do?")

greet("Jack")
```
**Output**

```
Hello Jack
How do you do?
```

Function arguments are passed inside the parenthesis during the function call.

It can then be accessed using the `name` parameter in the function definition.

---

## Passing Multiple Arguments

If we need to pass multiple arguments to a function, we can separate them by commas.

Let's create a function to add two numbers.

```python
def add_numbers(n1, n2):
    result = n1 + n2
    print("The sum is", result)


number1 = 5.4
number2 = 6.7
add_numbers(number1, number2)

```

**Output**

```
The sum is 12.100000000000001
```
We have passed `number1` and `number2` as arguments to the `add_numbers()` function.
These arguments are accepted as `n1` and `n2` once they are passed to the `add_numbers()` function.

>**Note:** We get this number instead of 12.1 because of floating-point representation error in Python.

---

## Return Value from Function

```python
def add_numbers(n1, n2):
    result = n1 + n2
    print("The sum is", result)


add_numbers(5.4, 6.7)
```
Sometimes it's better just to find the sum inside the function and print the result somewhere else.

We can achieve that by using the `return` statement.

```python
def add_numbers(n1, n2):
    result = n1 + n2
    return result

result = add_numbers(5.4, 6.7)
print("The sum is", result)
```

**Output**

```
The sum is 12.100000000000001
```

---

## Types of functions

There are two types of functions:

- **Built-in functions** - Functions that are built into Python.
- **User-defined functions** - Functions defined by the users themselves.

Some built-in functions:

|Function|Description|
|---|---|
|`float()`|converts to decimal number and returns it|
|`int()`|converts to integer and returns it|
|`input()`|function to take input from the user|

---

## Example

#### Grading Student Based on Marks Obtained by Making Functions

Suppose you just attended a University examination. The marks you obtained in various subjects are stored in a list like this:

```python
marks = [55, 64, 75, 80, 65]
```

**You want to find the average marks you obtained in the exam.**

**Based on the average marks you want to find your grade as:**

- **You will get Grade A if the average marks is equal to or above 80**
- **You will get Grade B if the average marks is equal to or above 60 and less than 80**
- **You will get Grade C if the average marks is equal to or above 50 and less than 60**
- **And if the average marks is less than 50, you will get Grade F**

```python
# find the average marks and return it
def find_average_marks(marks):
    sum_of_marks = sum(marks)
    number_of_subjects = len(marks)
    
    average_marks = sum_of_marks/number_of_subjects
    
    return average_marks

# compute grade and return it
def compute_grade(average_marks):
    if average_marks >= 80.0:
        grade = 'A'
    elif average_marks >= 60:
        grade = 'B'
    elif average_marks >= 50:
        grade = 'C'
    else:
        grade = 'F'
    
    return grade

marks = [55, 64, 75, 80, 65]
average_marks = find_average_marks(marks)
grade =compute_grade(average_marks)

print("Your average marks is", average_marks)
print("Your grade is", grade)
```

**Output**
```
Your average marks is 67.8
Your grade is B
```

---

## Programming Task

**Can you create a program to add and multiply two numbers?**

**For this, create two functions `add_numbers()` and `multiply_numbers()`.
These functions should compute the result and return them to the function call and should print from outside the function.**


```python
# function to add two numbers
def add_numbers(num1, num2):
    return num1 + num2

# function to multiply two numbers
def multiply_numbers(num1, num2):
    return num1 * num2

number1 = 5
number2 = 30

sum_result = add_numbers(number1, number2)
print("Sum is", sum_result)

product_result = multiply_numbers(number1, number2)
print("Product is", product_result)
```

**Output**

```
Sum is 35
Product is 150
```
