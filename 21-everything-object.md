# Everything in Python is an Object

**Video link:** [https://youtu.be/X1RN6ADsOW4](https://youtu.be/X1RN6ADsOW4)

In this video, you built a solid knowledge of Python objects by learning to check the type of objects, listing their attributes & methods, and understanding what actually goes under the hood.

**Programs in the Video**

- [The type() function](#the-type-function)
- [The dir() function](#the-dir-function)
- [The id() function](#the-id-function)
- [How variables actually work](#how-variables-actually-work)

---

## The type() function
Everything in Python is already an object, whether it's strings, numbers, functions or even classes.

We can check this using the type() function.

```python
numbers = [1, 4, 9, 16]
print(type(numbers))
```

**Output**

```
<class 'list'>
```

This means that lists are instantiated from the built-in Python class named `list`.

Let's try other objects:

```python
numbers = [1, 4, 9, 16]
print(type(numbers))

n1 = 5
print(type(n1))

flag = True
print(type(True))

def my_function():
    pass

print(type(my_function)
```

**Output**
```
<class 'list'>
<class 'int'>
<class 'bool'>
<class 'function'>
```

We can see that all these entities are instantiated from a class, which means they are all objects.

---

## The dir() function
We can list out all the attributes and methods of a given object by using the `dir()` function.

```python
numbers_list = [1, 2]
print(dir(numbers_list))
```

**Output**

```
['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__', '__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
```

Let's use the `__add__` method.  It is used to append all the items of another list to the end of the list.

```python
numbers_list = [1, 2]

print(dir(numbers_list))

result = numbers_list.__add__([3, 4])
print(result)
```

**Output**
```
[1, 2, 3, 4]
```

We can also accomplish this task by using the plus operator.

```python
numbers_list = [1, 2]

print(dir(numbers_list))

# result = numbers_list.__add__([3, 4])
result = numbers_list + [3, 4]

print(result)
```

**Output**

```
[1, 2, 3, 4]
```

In fact, the plus operator internally calls the `__add__()` method. Even though we are working with operators, we are actually using attributes and methods of the object internally.

---

## The id() function

In Python, every object has an id for identity. The id of an object is always unique and constant for this object during its lifetime.

We can check the id of an object by using the `id()` function.

```python
number1 = 5
print(id(number1))

number2 = 10
print(id(number2))
```

**Output**

```
9784992
9785152
```

Let's try assigning `number1` to `number2`.

```python
number1 = 5
print(id(number1))

number2 = number1
print(id(number2))
```

**Output**

```
9784992
9784992
```

The id is the same.
Python does this for memory optimization.

---

## How variables actually work?

We have been learning that variables store a value. However, this is not technically true.

A variable is more like a name tag and it can refer to any value.

Suppose, we have a list `a` and we assigned another variable `b` to this variable:

```python
a = [1, 2, 3]
b = a
```

Now, if we try to change the value of `a`:

```python
a = [1, 2, 3]
b = a

a.append(4)

print("a =", a)
print("b =", b)
```

**Output**
```
[1, 2, 3, 4]
[1, 2, 3, 4]
```

Here, both variables `a` and `b` are changed. It's because `a` and `b` are referring to the same object. And, if we check the id of variables `a` and `b`, they will be the same.

That's why we use the list's `copy()` method to copy one list to another if we do not want this behavior.

```python
a = [1, 2, 3]
b = a.copy()

a.append(4)

print("a =", a)
print("b =", b)
```

**Output**
```
[1, 2, 3]
[1, 2, 3, 4]
```

Now, `a` and `b` refer to two different objects and modifying one won't affect the other.