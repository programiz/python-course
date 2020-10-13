# Python List and Tuple

**Video link:** [https://youtu.be/hANUgg72TDc](https://youtu.be/hANUgg72TDc)

In this video, we learned about two compound data types in Python: lists and tuples.

**Programs in the Video**

- [Create a List](#create-a-list)
- [Access List Elements](#access-list-elements)
- [Negative Indexing](#negative-indexing)
- [Slicing of a List](#slicing-of-a-list) 
- [Change Items of a List](#change-items-of-a-list)
- [`in` keyword](#in-keyword)
- [Iterating through a List](#iterating-through-a-list)
- [Python Tuples](#python-tuples)
- [Python Tuple vs List](#python-tuple-vs-list)
- [**Task**: Guess the Output](#programming-task)
---

## Python List

### Create a List
In Python, a list is a sequence of items in an order.
We create lists by placing items inside square brackets `[]` separated by commas.

A list can contain mixed data type as well as duplicate elements.

```python
# a list of integers
numbers = [1, 5, 6, -4]
print(numbers)

# mixed list
random_list = [2.5, "Hello", -5, 2.5]
print(random_list)

# empty list
list1 = []
print(list1)
```

**Output**
```
[1, 5, 6, -4]
[2.5, 'Hello', -5, 2.5]
[]
```

We can use the built-in `len()` function to find length of a list.

```python
# a list of integers
numbers = [1, 5, 6, -4]
print(len(numbers))

# empty list
list1 = []
print(len(list1))
```

**Output**

```
4
0
```

---

## Access List Elements

A list is a sequence, and its items are always in order.

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]
print(languages)
```

**Output**

```
['Python', 'JavaScript', 'C++', 'Kotlin']
```

Here, every elements in the list maintain an order.

We can access individual items of lists by using the item's index. Index starts from 0.
So the index of the first item is 0, the second item is 1 and so on.

|Item|Index|
|---|---|
|'Python'|0|
|'JavaScript'|1|
|'C++'|2|
|'Kotlin'|3|

We can use indices in the following way:

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]

# first item
print(languages[0])

# third item
print(languages[2])
```

**Output**
```
Python
C++
```

If the specified index does not exist in the list, Python throws an `IndexError`
exception.

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]
print(languages[4])
```

**Output**

```
Traceback (most recent call last):
  File "<string>", line 2, in <module>
IndexError: list index out of range
```
---

### Negative Indexing

In Python, we can also use negative indexing for sequences like lists.
Using a negative index gives us items from the last.

|Item|Index|
|---|---|
|'Python'|-4|
|'JavaScript'|-3|
|'C++'|-2|
|'Kotlin'|-1|

Negative index can be used like normal index:

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]

# last element
print(languages[-1])

# third to last element
print(languages[-3])
```

**Output**

```
Kotlin
JavaScript
```

---

### Slicing of a List

It is also possible to access a whole section of items from the list, not just a single item.

For example,

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]

# first three items -> 0, 1, 2
print(languages[0:3])

# second to last items -> 1, 2, 3
print(languages[1:4])
```

**Output**

```
['Python', 'JavaScript', 'C++']
['JavaScript', 'C++', 'Kotlin']
```

While using slicing, the starting index is inclusive but the ending index is exclusive.

>**Notes**:
>- If we use the empty start index, the slicing starts from the beginning of the list.
>- If we use the empty end index, the slicing ends at the last index.

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]

# first to third element
print(languages[:3])

# second to last element
print(languages[1:])
```

**Output**

```
['Python', 'JavaScript', 'C++']
['JavaScript', 'C++', 'Kotlin']
```

---

### Change Items of a List

Lists are mutable. Let's see how we can change items of a list.

For example,

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]

# modifying the second item
languages[1] = "Ruby"

print(languages)
```

**Output**

```
['Python', 'Ruby', 'C++', 'Kotlin']
```

We can also modify a range of items of a list.

For example,

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]

# modifying the second item to third item
languages[1:3] = ["Ruby", "Dart"]

print(languages)
```

**Output**

```
['Python', 'Ruby', 'Dart', 'Kotlin']
```

---

### `in` keyword
The `in` keyword is used to check whether an item is in the list or not.

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]
print("Python" in languages)

print("Rust" in languages)
```

**Output**
```
True
False
```

---

### Iterating through a List

If we want to get individual items of a list one by one, we can use a `for` loop.

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]

for language in languages:
    print(language)
```

**Output**

```
Python
JavaScript
C++
Kotlin
```

In each iteration, the value of `language` is each individual item from the `languages` list.

---

### List Methods

#### `append()` method

To add items to end of the list, we can use the `append()` method.

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]
languages.append("Rust")

print(languages)
```

**Output**
```
['Python', 'JavaScript', 'C++', 'Kotlin', 'Rust']
```

---

#### `insert()` method

To add items to a specified index in the list, we can use the `insert()` method.

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]
languages.insert(1, "Rust")

print(languages)
```

**Output**
```
['Python', 'Rust', 'JavaScript', 'C++', 'Kotlin']
```

---

#### `remove()` method

To remove specified item from a list, we can use the `remove()` method.

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]
languages.remove("C++")

print(languages)
```

**Output**
```
['Python', 'JavaScript', 'Kotlin']
```

---

#### `copy()` method

To create a copy of a list, we can use the `copy()` method.

```python
languages = ["Python", "JavaScript", "C++", "Kotlin"]

languages1 = languages.copy()
print(languages1)

```

**Output**
```
["Python", "JavaScript", "C++", "Kotlin"]
```

---

## Python Tuples

A tuple in Python is similar to a list. It is also an ordered collection of items.

The only difference between the two is that lists are mutable (elements of a list can be changed), whereas tuples are immutable (elements of a tuple cannot be changed).

To create a tuple, we need to wrap items inside parentheses `()` and separate items by a comma.

```python
numbers = (21, -5, 6, 9)
print(numbers)
```

**Output**
```
(21, -5, 6, 9)
```

We can access elements from a tuple in a similar way to lists.

```python
numbers = (1, 5, 6, 3)
print(numbers[2])
```

**Output**
```
6
```

We can also perform slicing similar to lists.

```python
numbers = (1, 5, 6, 3)
print(numbers[1:4])
```

**Output**
```
(5, 6, 3)
```

We can loop through a tuple using a `for` loop:

```python
numbers = (1, 5, 6, 3)

for number in numbers:
   print(number)
```

**Output**
```
1
5
6
3
```

---

## Python Tuple vs List

The difference between tuple and list is that a list can be changed but tuple cannot be changed.

Let's try changing an item of a tuple.
```python
languages_tuple = ("Python", "JavaScript", "C++", "Kotlin")
languages_tuple[0] = "Java"
print(languages_tuple)
```

**Output**
```
Traceback (most recent call last):
  File "<string>", line 2, in <module>
TypeError: 'tuple' object does not support item assignment
```

---

## Programming Task

**Can you guess the output of this program?**

```python
mixed_list = ["Hello", -34, "Java", True]

print("1.", mixed_list[-1])

mixed_list[1] = "Hi"
print("2.", mixed_list)

mixed_tuple = (1, 3, 4, 5)

mixed_tuple[1] = 100
print("3.", mixed_tuple)
```

**Output**
```
1. True
2. ['Hello', 'Hi', 'Java', True]
Traceback (most recent call last):
File "<string>", line 10, in <module>
TypeError: 'tuple' object does not support item assignment
```