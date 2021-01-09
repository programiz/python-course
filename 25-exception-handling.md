# Python Exception Handling

**Video link:** [https://youtu.be/brICUKrzVR0](https://youtu.be/brICUKrzVR0)

In this video, we learned about exceptions in detail and also about handling them in Python using `try...except` statement.

**Programs in the Video**

- [Exceptions](#exceptions)
- [Handling Exceptions](#handling-exceptions)
- [Handling Specific Exception](#handling-specific-exception)
- [Python `try...finally`](#python-tryfinally)

---

## Exceptions
Let's write a program that will give us an error.

```python
numerator = 10
denominator = 0

print(numerator/denominator)
```

**Output**

```
Traceback (most recent call last):
  File "<string>", line 1, in <module>
ZeroDivisionError: division by zero
```

Even though our code was correct syntax wise, it's not allowed to divide a number by `0` in Python. This is an exception. In this case, we are getting the `ZeroDivisionError` exception.

There are numerous other built-in exceptions:

|Exception|Cause of Error|
|---|---|
|`FileNotFoundError`|When a file that doesn't exist is accessed|
|`IndexError`|When the index of a sequence is out of range|
|`FloatingPointError`|When a floating point operation fails|

---

## Handling Exceptions

When our program encounters an exception, our code ends abruptly with an error message. Most of the time, rather than showing this default message, we may want to show a custom message that's more helpful or run a different set of code.

This is known as exception handling. It's the process of responding to exceptions in a custom way during the execution of a program. 

In Python, we use the `try..except` block to handle exceptions. Its syntax is:

```python
try:
    # code that may cause exception
except:
    # code to run when exception occurs
```

- Inside the `try` block, we write the code that may raise an exception.
- If an exception occurs, the control of the program jumps to the `except` block.
- If exceptions don't occur, the `except` block is skipped.

Let's see an example:

```python
try:
    numerator = int(input("Enter numerator: "))
    denominator = int(input("Enter denominator: "))

    result = numerator/denominator

    print(result)
except:
    print("Denominator cannot be 0. Try again.")

print("Program ends")
```

**Output**
```
Enter numerator: 3
Enter denominator: 0
Denominator cannot be 0. Try again.
Program ends
```

```
Enter numerator: 3
Enter denominator: 4
0.75
Program ends
```
---

## Handling Specific Exception

In our previous example, the `except` block handles all types of exception. If we want to make it handle only certain type of exception we can:

```python
try:
    numerator = int(input("Enter numerator: "))
    denominator = int(input("Enter denominator: "))

    result = numerator/denominator

    print(result)
except ZeroDivisionError:
    print("Denominator cannot be 0. Try again.")

print("Program ends")
```

**Output**

```
Enter numerator: 3
Enter denominator: 0
Denominator cannot be 0. Try again.
Program ends
```

Now the `except` block is handling only the `ZeroDivisionError`.

This is mostly useful if the code inside `try` block can raise more than one exception.

For example:

```python
try:
    numerator = int(input("Enter numerator: "))
    denominator = int(input("Enter denominator: "))

    result = numerator/denominator

    print(result)
    
    my_list = [1, 2, 3]
    i = int(input("Enter index: "))
    print(my_list[i])
except ZeroDivisionError:
    print("Denominator cannot be 0. Try again.")
except IndexError:
    print("Index is wrong.")

print("Program ends")
```

**Output**
```
Enter numerator: 6
Enter denominator: 5
1.2
Enter index: 4
Index is wrong.
Program ends
```
Here, there is no `ZeroDivisionError`, so `except ZeroDivisionError` block was skipped. If there was `ZeroDivisionError`:

```
Enter numerator: 3
Enter denominator: 0
Denominator cannot be 0. Try again.
Program ends
```

---

## Python `try...finally`
A `try` statement can also have an optional `finally` block which is executed regardless of whether an exception occurs or not.

Its syntax looks something like this:

```python
try:
    print(1/0)
except:
    print("Wrong denominator")
finally:
    print("Always printed")
```

**Output**
```
Wrong denominator
Always printed
```

The code gives the `ZeroDivisionError` so the `except` block is executed. Finally, the code inside the `finally` block is also executed.

However, if an exception doesn't occur in the `try` block, the `except` block is skipped but `finally` block is still executed at the end.

>**Note**: The `finally` block is usually used to perform cleanup actions that need to be executed under all circumstances.
>Suppose, we are working with an external file in our program. We need to close this file at the end even if there was an error while writing to it. In this case, we put the `close_file()` function inside the `finally` block.