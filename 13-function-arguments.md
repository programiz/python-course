# Python Function Arguments

**Video link:** [https://youtu.be/Gf-Ws2cXEuA](https://youtu.be/Gf-Ws2cXEuA)

In this video, we learned about the different ways in which we can pass arguments to a function in Python. We also learned to assign default values to function arguments.

**Programs in the Video**

- [Positional Arguments](#positional-arguments)
- [Default Arguments](#default-arguments)
- [Keyword Arguments](#keyword-arguments)

---

## Positional Arguments
Positional arguments are the arguments that need to be passed to the function call in a proper order.

For example,

```python
def add_numbers(n1, n2):
    result = n1 + n2
    return result

result = add_numbers(5.4, 6.7)
print(result)
```

Here, we have called the `add_numbers()` function with two arguments.

These arguments we passed to the function are called positional arguments.

It is because the first argument `5.4` is assigned to the first parameter `n1` and the second argument `6.7` is assigned to the second parameter `n2`. These arguments are passed based on their position.

If we remove the second argument, it will lead to an error message:

```python
def add_numbers(n1, n2):
    result = n1 + n2
    return result

result = add_numbers(5.4)
print(result)
```

**Output**

```
Traceback (most recent call last):
  File "<string>", line 5, in <module>
TypeError: add_numbers() missing 1 required positional argument: 'n2'
```

This error message is telling us that we need to pass a second argument during the function call because our add numbers function takes two arguments.

---

## Default Arguments

Function arguments can have default values in Python.

We can provide a default value to an argument by using the assignment operator `=`. 

For example,

```python
def add_numbers(n1 = 100, n2 = 1000):
    result = n1 + n2
    return result

result = add_numbers(5.4)
print(result)
```

**Output**

```
1005.4
```

Here, `n1` takes the value passed in function call.

Since there is no second argument in the function call, `n2` takes the default value of `1000`.

If we run the function without any arguments:

```python
def add_numbers(n1 = 100, n2 = 1000):
    sum = n1 + n2
    return sum

result = add_numbers()
print(result)
```

**Output**
```
1100
```
---

## Keyword Arguments

In Python, we can not only pass arguments to a function based on position, but also using their parameter name.

```python
def greet(name, message):
    print("Hello", name)
    print(message)

greet("Jack", "What's going on?")

greet(message = "Howdy?", name = "Jill")
```

**Output**

```
Hello Jack
What's going on?
Hello Jill
Howdy?
```

During the second function call, we have passed arguments by their parameter name.

Python allows functions to be called using keyword arguments. When we call functions in this way, the order (position) of the arguments can be changed.
