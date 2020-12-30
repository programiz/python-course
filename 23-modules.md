# Python Modules

**Video link:** [https://www.youtube.com/watch?v=WfcozEiBIJU](https://www.youtube.com/watch?v=WfcozEiBIJU)

In this video, we learned why modules are used and how we can import them in our program.
We then learned to create custom modules with the help of examples.

**Programs in the Video**

- [Python Modules](#python-modules-1)
- [Renaming modules](#renaming-modules)
- [Python from...import statement](#python-fromimport-statement)
- [The `dir()` function](#the-dir-function)
- [Custom Modules](#custom-modules)

---

## Python Modules
A module is a file that contains Python code that we can use in our program.

There are several built-in functions like `print()`, `input()` and `sum()` that are readily available to us.
In addition to these functions, Python also has several functions that are defined inside a module which we can use after we import them. 

Let's use one such module called `math`:

```python
import math

number = 25
result = math.sqrt(number)
print(result)

print(math.pi)
```

**Output**
```
5.0
3.141592653589793
```

Once we import a module, we can use everything inside it using the dot operator.
 
We imported `math` using the `import` statement and called its `sqrt()` function that calculates the square root of a number.

Also, the value of the constant `pi` is printed to the screen.

---

## Renaming modules

While importing a module, we can also rename it to a different name as per our needs.

Let's rename the `math` module to `m`:

```python
import math as m

number = 25
result = m.sqrt(number)
print(result)

print(m.pi)
```

**Output**
```
5.0
3.141592653589793
```

We get the same output as before.

---

## Python from...import statement
When we import a module like in our previous examples, everything in the module is available to us.

However, if we only need to import a specific definition like a function or a constant, we can use the `from..import` statement.

```python
from math import sqrt

num = sqrt(64)
print(num)
```

**Output**

```
8.0
```

Here, only the `sqrt` function is imported from the `math` module.
When we use this syntax, instead of `math.sqrt`, we need to directly use the `sqrt` function.

We can also import multiple definitions from the module in a single line using this syntax:

```python
from math import pi, sin, sqrt

value = sin(pi/2)
print(value)

num = sqrt(64)
print(num)
```

**Output**
```
1.0
8.0
```

We can also use the `from...import` statement to import all definitions from a module using `*`:

```python
from math import *

value = sin(pi/2)
print(value)

num = sqrt(64)
print(num)
```

**Output**
```
1.0
8.0
```

Here, asterisk `*` means import everything.

>**Note:** Importing every definition name with the asterisk symbol is a bad programming practice and you should try to avoid it in your code.

---

## The `dir()` function

The `math` module comes with many more handy functions and constants.

We can list out all the things defined inside a module by using the `dir()` function:

```python
import math

print(dir(math))
```

**Output**

```
['__doc__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'ceil', 'comb', 'copysign', 'cos', 'cosh', 'degrees', 'dist', 'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 'hypot', 'inf', 'isclose', 'isfinite', 'isinf', 'isnan', 'isqrt', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'log2', 'modf', 'nan', 'perm', 'pi', 'pow', 'prod', 'radians', 'remainder', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'tau', 'trunc']
```

As you can see, there are many other mathematical, trigonometric and logarithmic functions inside the `math` module.

---

>The `math` module file comes when we install Python that's why we can import it directly. There are many popular modules that are not natively available for us to use.
>For example, `numpy` is a popular package that is used for scientific computing. To use `numpy`, we must first install it.
>
>Similarly, you might have heard about `django`. It's a popular framework used for creating web applications. It's also available only after we install it.

---

## Custom Modules

In Python, we can also create our own custom modules as per our needs. This helps us to keep our code organized.

Let's a module named `calculator` that will contain functions to perform arithmetic operations.

First, create a file named `calculator.py` in the same directory and add the following:

```python
def add(a, b):
    return a + b
    
def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b
    
def divide(a, b):
    return a / b 
```

This file in itself is a module. Let's import this file from the main file.

In my main file:

```python
import calculator

result1 = calculator.add(2, 3)
print(result1)

result2 = calculator.subtract(6, 3)
print(result2)

result3 = calculator.multiply(10, 3)
print(result3)

result4 = calculator.divide(6, 3)
print(result4)
```

**Output**
```
5
3
30
2.0
```

In our example, we have only used functions and constants from a module. However a module may also contain classes or any other definitions.

Now, we can already sense how useful a module is. It helps us in better code management and improves the reusability of our code.
