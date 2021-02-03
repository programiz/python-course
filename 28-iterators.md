# Python Iterators and Iterables

**Video link:** [https://youtu.be/C_rhipZonok](https://youtu.be/C_rhipZonok)

In this video, we learned about iterables and iterators in Python with the help of examples.

**Programs in the Video**

- [Python Iterables](#python-iterables)
- [Python Iterators](#python-iterators)
- [The `__next__()` method](#the-__next__-method)
- [Working of `for` loops](#working-of-for-loops)
- [Creating Custom Iterators](#creating-custom-iterators)

---

## Python Iterables
Anything that you can loop over in Python is called an iterable. For example, a list is an iterable.
For an object to be considered an iterable, it must have the `__iter()__` method.

```python
numbers = [1, 4, 9]
print(dir(numbers))
```

**Output**
```
['__add__', '__class__', '__contains__', '__delattr__', '__delitem__', '__dir__', '__doc__', '__eq__', '__format__',
'__ge__', '__getattribute__', '__getitem__', '__gt__', '__hash__', '__iadd__', '__imul__', '__init__', '__init_subclass__',
'__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__reversed__',
'__rmul__', '__setattr__', '__setitem__', '__sizeof__', '__str__', '__subclasshook__', 'append', 'clear', 'copy', 'count', 'extend',
'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
```

We can see that there is a special `__iter__()` method among all these methods. Let's call this method.

```python
numbers = [1, 4, 9]

value = numbers.__iter__()
print(value)
```

**Output**
```
<list_iterator object at 0x7fa223878d00>
```

The `iter` method returns an iterator object. 
 
---

## Python Iterators

Iterator in Python is simply an object that can return data one at a time while iterating over it.

For an object to be an iterator, it must implement two methods:
- `__iter__()`
- `__next__()`

These are collectively called the iterator protocol.

---

## The __next__() method

The `__next__()` method returns the next value in the iteration.

```python
numbers = [1, 4, 9]
value = numbers.__iter__()

item1 = value.__next__()
print(item1)
```

**Output**
```
1
```

Now, if we run the `next` method again, it should return the next item which is `4`. It's because the `next` method also updates the state of the iterator. 


```python
numbers = [1, 4, 9]
value = numbers.__iter__()

item1 = value.__next__()
print(item1)

item2 = value.__next__()
print(item2)

item3 = value.__next__()
print(item3)
```

**Output**
```
1
4
9
```

>**Note**: Instead of calling these special methods with an underscore,
>Python has an elegant way to call `__iter__()` simply with the `iter()` function  and `__next__()` with the `next()` function.

Here, we have already reached the end of our list. Now, let's see what happens if we further try to get the next value.

```python
numbers = [1, 4, 9]
value = iter(numbers)

item1 = next(value)
print(item1)

item2 = next(value)
print(item2)

item3 = next(value)
print(item3)

item4 = next(value)
print(item4)
```

**Output**
```
1
4
9
Traceback (most recent call last):
  File "<string>", line 13, in <module>
StopIteration
```

Since our list had only 3 elements, the call to the fourth `next()` method raised the `StopIteration` exception.

---

## Working of `for` loops

Did you know that `for` loops internally use the `while` loop to iterate through sequences?

```python
num_list = [1, 4, 9]

iter_obj = iter(num_list)

while True:
    try:
        element = next(iter_obj)
        print(element)
    except StopIteration:
        break
```

**Output**
```
1
4
9
```


Here's how this code works:

- First, we have created an iterator object from a list using `iter_obj = iter(num_list)`
- Then, we have created an infinite `while` loop.
- Inside the loop, we have used the `next` method to return the next element in the sequence `element = next(iter_obj))` and printed it. We have put this code inside the `try` block. 
- When all the items of the iterator are iterated, the `try` block raises the `StopIteration` exception, and the `except` block catches it and breaks the loop.

In fact, this is exactly how `for` loops work behind the scene. A `for` loop internally creates an iterator object, and iterates over it calling the `next` method until a `StopIteration` exception is encountered.

The above code is equivalent to:
```python
num_list = [1, 4, 9]

for element in num_list:
    print(element)
```

---

## Creating Custom Iterators
Let's try to make our own iterator object to generate a sequence of even numbers such as 2, 4, 6, 8 and so on.

```python
class Even:
    def __init__(self, max):
        self.n = 2
        self.max = max

    def __iter__(self):
        return self

    def __next__(self):
        if self.n <= self.max:
            result = self.n
            self.n += 2
            return result
        else:
            raise StopIteration

numbers = Even(10)

print(next(numbers))
print(next(numbers))
print(next(numbers))
```

**Output**
```
2
4
6
```

Iterators are powerful tools when dealing with a large stream of data.
If we used regular lists to store these values, our computer would run out of memory.
With iterators, however, we can save resources as they return only one element at a time.
So, in theory, we can deal with infinite data in finite memory.
