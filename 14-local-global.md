# Python Local and Global Variables

**Video link:** [https://youtu.be/ngCDTEWVjrQ](https://youtu.be/ngCDTEWVjrQ)

In this video, we learned about the concept of global and local variables in Python.

**Programs in the Video**

- [Local Variables](#local-variables)
- [Global Variables](#global-variables)

---

## Local Variables
A variable declared inside the function's body or in the local scope is known as a local variable.

Suppose we have the following function:

```python
def add_numbers(n1, n2):
    result = n1 + n2
    print(result)

add_numbers(2, 5)
```

Let's try to print the `result` variable from outside the function.

```python
def add_numbers(n1, n2):
    result = n1 + n2

add_numbers(2, 5)
print(result)
```

**Output**

```
Traceback (most recent call last):
  File "<string>", line 5, in <module>
NameError: name 'result' is not defined
```

This error is saying that the result variable is not defined in line 5.

Any variable that is created inside a function is local to it. The `result` variable is local to the `add_numbers()` function.

We can fix this by using a return statement:

```python
def add_numbers(n1, n2):
    result = n1 + n2
    return result

output = add_numbers(2, 5)
print(output)
```

---

## Global Variables

In Python, a variable declared outside of the function or in global scope is known as a global variable.

This means that a global variable can be accessed inside or outside of the function.

For example,

```python
message = "How you doing?"

def greet():
    print(message)

greet()
```

**Output**

```
How you doing?
```

Here, `message` is a global variable and can be used anywhere in the program.

Let's see what happens if a local variable with the same name is defined.

```python
message = "How you doing?"

def greet():
    message = "How are you?"
    print("Message inside function:", message)

greet()
print("Message outside function:", message)
```

**Output**
```
Message inside function How are you?
Message outside function: How you doing?
```

Rather than changing the global `message` variable, a new local variable is created with the new value.

However, the global `message` variable is not changed, so it gets printed outside the function as it is.

---

### `global` keyword

If we need to change the global variable inside the function, we can use the `global` keyword:

```python
def greet():
    global message
    message = "How are you?"
    print("Message inside function", message)

greet()
print("Message outside function:", message)
```

**Output**

```
Message inside function How are you?
Message outside function: How are you?
```

The global variable tells Python that the variable we are referring to is the global variable.

After we change the global `message` variable, the changes are reflected in the global scope as well.