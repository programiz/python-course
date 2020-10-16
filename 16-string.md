# Python String

**Video link:** [https://youtu.be/GQywwPUrsgA](https://youtu.be/GQywwPUrsgA)

In this video, we learned about Python strings in depth.

**Programs in the Video**

- [Create a String](#create-a-string)
- [Access String Characters](#access-string-characters)
- [Negative Indexing](#negative-indexing)
- [Slicing of a String](#slicing-of-a-string) 
- [Change and Delete String Characters](#change-and-delete-string-characters)
- [Python String Operations](#python-string-operations)
- [Iterating through a String](#iterating-through-a-string)
- [Python String Methods](#python-string-methods)
- [**Task**: Guess the Output](#programming-task)
---

### Create a String
A string is a sequence of characters or textual data. In Python, we create strings by enclosing characters inside quotations like:

```python
# single quote
text = 'Hello there'
print(text)

# double quotes
text = "Hello there"
print(text)

# triple quotes for multiline strings
text = """Hello there.
How are you doing"""
print(text)
```

**Output**
```
Hello there
Hello there
Hello there.
How are you doing
```

However, we can't use mismatching quotations like:

```python
# mismatching strings
text = 'Hello there"
print(text)
```

**Output**

```
File "<string>", line 2
    text = 'Hello there"
                       ^
SyntaxError: EOL while scanning string literal
```


Suppose we want to create a string:
```
He said, "What's there?"
```

It contains both single quotes and double quotes, so using either of those would give error:

```python
text =  "He said, "What's there?""
print(text)
```

**Output**
```
File "<string>", line 1
    text =  "He said, "What's there?""
                       ^
SyntaxError: invalid syntax
```

To fix this, we can escape characters like quotations by using a backslash `\` before it.

```python
text =  "He said, \"What\'s there?\""
print(text)
```

**Output**
```
He said, "What's there?"
```
---

## Access String Characters

A string is a sequence of characters, and these characters are in order. So, we can access individual characters of a string using indices just like with lists and tuples. 

```python
text = "Python"
print(text)
```

**Output**

```
Python
```

Here, every elements in the list maintain an order.

We can access individual characters of string by using its index. Index starts from `0`.
So the index of the first character is 0, the second character is 1 and so on.

|Character|Index|
|---|---|
|'P'|0|
|'y'|1|
|'t'|2|
|'h'|3|
|...|...|

We can use indices in the following way:

```python
text = "Python"

# first character
print(text[0])

# fourth character
print(text[3])
```

**Output**
```
P
h
```

If the specified index does not exist in the string, Python throws an `IndexError`
exception.

```python
text = "Python"
print(text[10])
```

**Output**

```
Traceback (most recent call last):
  File "<string>", line 2, in <module>
IndexError: string index out of range
```
---

### Negative Indexing

In Python, we can also use negative indexing for sequences like string.
Using a negative index gives us characters from the last.

|Character|Index|
|---|---|
|'P'|-6|
|'y'|-5|
|'t'|-4|
|'h'|-3|
|'o'|-2|
|'n'|-1|

Negative index can be used like normal index:

```python
text = "Python"

# last character
print(text[-1])

# third to last character
print(text[-3])
```

**Output**

```
n
h
```

---

### Slicing of a String

It is also possible to access multiple characters from the string, not just a single character.

For example,

```python
text = "Python"

# 2nd, 3rd and 4th characters
print(text[1:4])
```

**Output**

```
yth
```

While using slicing, the starting index is inclusive but the ending index is exclusive.

>**Notes**:
>- If we use the empty start index, the slicing starts from the beginning of the string.
>- If we use the empty end index, the slicing ends at the last string character.

```python
text = "Python"

# first to fourth characters
print(text[:4])

# from third to last character
print(text[2:])
```

**Output**

```
Pyth
thon
```

---

### Change and Delete String Characters

Strings in Python are immutable, and we cannot add or change characters of a string. Let's see what happens when we try to change characters of a string:

```python
text = "Python"
text[0] = "p"
print(text)
```

**Output**

```
Traceback (most recent call last):
  File "<string>", line 2, in <module>
TypeError: 'str' object does not support item assignment
```

---

### Python String Operations

#### Concatenation
It denotes the joining of two strings into one. To join two strings, we can use the plus `+` operator.

```python
text1 = "Python"
text2 = "Programming"

result = text1 + " " + text2
print(result)
```

**Output**
```
Python Programming
```

#### Repeating strings
We use the asterisk `*` operator to repeat a string a certain number of times:

```python
text = "Python"
new_text = text * 3

print(new_text)
```

**Output**
```
PythonPythonPython
```
---

### Iterating through a String

If we want to get individual characters of a string one by one, we can use a `for` loop.

```python
text = "Python"

for character in text:
    print(character) 
```

**Output**

```
P
y
t
h
o
n
```

In each iteration, the value of `character` is each individual character from the `text` string.

We can use `len()` to find length of a string:

```python
text = "Python"
print(len(text))
```

**Output**
```
6
```

We can also use the `in` operator to find out if a substring is present in a given string:

```python
text = "Python"
print("P" in text)

print("yth" in text)

print("ont" in text)
```

**Output**
```
True
True
False
```

---

### Python String Methods

Strings are probably the most frequently used data type. To make working with strings easier, Python has numerous string methods readily available for us to use.

#### `lower()` and `upper()` method

To make all the characters lowercase, we can use the `lower()` method.

```python
text = "I like Python 3"
result = text.lower()

print(result)
```

**Output**
```
i like python 3
```

Similarly, if we want all uppercase characters, we can use the `upper()` method.

```python
text = "I like Python 3"
result = text.upper()

print(result)
```

**Output**
```
I LIKE PYTHON 3
```

---

#### `find()` method

To find the index of the Python substring, we can use the `find()` method.

```python
text = "I like Python 3"
result = text.find("Python")

print(result)
```

**Output**
```
7
```

---

#### `replace()` method

To replace a substring with another, we can use the `replace()` method.

```python
text = "I like Python 3"
result = text.replace("Python 3", "Java")

print(result)
```

**Output**
```
I like Java
```

---

## Programming Task

**Can you guess the output of this program?**

```python
quote = "Talk is cheap. Show me the code."

print("1.", quote[3])
print("2.", quote[-3])
print("3.", quote.replace("code", "program"))
```

**Output**
```
1. k
2. d
3. Talk is cheap. Show me the program.
```