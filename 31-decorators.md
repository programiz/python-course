# Python Decorators

**Video link:** [https://youtu.be/8hWIWyBfdQE](https://youtu.be/8hWIWyBfdQE)

In this video, we learned how to create decorators and why we should use them.

**Programs in the Video**

- [Prerequisites for Decorators](#prerequisites-for-decorators)
- [Python Decorators](#python-decorators-1)
- [Decorating Functions with Parameters](#decorating-functions-with-parameters)
- [Chaining Decorators in Python](#chaining-decorators-in-python)

---

## Prerequisites for Decorators
Before we learn about decorators, we must first understand a few basic things in Python.

**We must be comfortable with the fact that everything in Python is an object, including classes as well as functions**.
Variables are simply identifiers bound to these objects.

Since functions are also objects, we can also pass functions as arguments to other functions:

```python
def inc(x):
    return x + 1

def operate(func, x):
    result = func(x)
    return result

print(operate(inc, 3))
```

**Output**
```
4
```

**In Python, we can also define a function inside a function**:

```python
def print_msg(message):
    greeting = "Hello"
    def printer():
        print(greeting, message)

    printer()


print_msg("Python is awesome")
```

**Output**

```
Hello Python is awesome
```

**Functions is that they can also return a function as a value.** Let's modify our previous code:

```python
def print_msg(message):
    greeting = "Hello"
    def printer():
        print(greeting, message)

    return printer

func = print_msg("Python is awesome")
func()
```

**Output**
```
Hello Python is awesome
```

Do you notice something weird here? Even though `print_msg()` function is done executing, the returned inner `printer()` function
can still access the `message` and `greeting` variables. Such a function is called a closure function.

A closure is simply an inner function that remembers the values and variables in its enclosing scope even if the outer function is done executing.

Python Decorators make an extensive use of closures.

---

## Python Decorators

A Python decorator is a function that takes in a function, adds some functionality to it and returns the original function.

Let's try to build a decorator function that prints out some information before and after executing another function.

```python
def printer():
    print("Hello, World!")


def display_info(func):
    def inner():
        print("Executing",func.__name__,"function")
        func()
        print("Finished execution")
    return inner
```

Let's call `printer()` normally first.


```python
def printer():
    print("Hello, World!")


def display_info(func):
    def inner():
        print("Executing",func.__name__,"function")
        func()
        print("Finished execution")
    return inner

printer()
```

**Output**

```
Hello, World!
```

Now, let's use the decorator function to run the same `printer` function.

```python
def printer():
    print("Hello, World!")


def display_info(func):
    def inner():
        print("Executing",func.__name__,"function")
        func()
        print("Finished execution")
    return inner

decorated_func = display_info(printer)
decorated_func()
```

**Output**

```
Executing printer function
Hello, World!
Finished execution
```

In python, we have a much more elegant way of to achieve this functionality using the `@` symbol.


```python
def display_info(func):
    def inner():
        print("Executing",func.__name__,"function")
        func()
        print("Finished execution")
    return inner

@display_info
def printer():
    print("Hello, World!")

printer()
```

**Output**
```
Executing printer function
Hello, World!
Finished execution
```

---

## Decorating Functions with Parameters

Suppose we have a simple `divide` function.

```python
def divide(a, b):
    return a/b
```

We know this code will throw an exception if we pass the value for `b` as `0`.

Let's make a decorator function called `smart_divide` to prevent this.

```python
def smart_divide(func):
    def inner(a, b):
        print("Dividing", a, "by", b)
        if b == 0:
            print("Cannot divide by 0!")
            return

        return func(a, b)
    return inner


@smart_divide
def divide(a, b):
    return a/b

value1 = divide(15, 3)
print(value1)

value2 = divide(5, 0)
print(value2)
```

**Output**

```
Dividing 15 by 3
5.0
Dividing 5 by 0
Cannot divide by 0!
None
```

---

## Chaining Decorators in Python

In Python, a function can be decorated multiple times with different or the same decorator.

Here, are two decorator functions called `star` and `percent`. These functions print a series of star and percentage symbols before and after executing the function

```python
def star(func):
    def inner(arg):
        print("*" * 30)
        func(arg)
        print("*" * 30)
    return inner

def percent(func):
    def inner(arg):
        print("%" * 30)
        func(arg)
        print("%" * 30)
    return inner

@star
@percent
def printer(msg):
    print(msg)

printer("Decorators are wonderful")
```

**Output**
```
******************************
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
Decorators are wonderful
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
******************************
```

As you can see, these decorators are chained and they wrap the original function.

Here, we have first called the `star` function, and then the `percent` function. So the `star` function wraps the `percent` function which in turn wraps the `printer` function.
