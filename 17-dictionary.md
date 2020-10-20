# Python Dictionary

**Video link:** [https://youtu.be/_4wOvc-vt4k](https://youtu.be/_4wOvc-vt4k)

In this video, we learned about Python dictionary that allows us to work with key/value pairs.

**Programs in the Video**

- [Create Dictionaries](#create-dictionaries)
- [Access Dictionary Elements](#access-dictionary-elements)
- [Add and Change Dictionary Elements](#add-and-change-dictionary-elements)
- [Remove Elements From a Dictionary](#remove-elements-from-a-dictionary) 
- [Iterating Through a Dictionary](#iterating-through-a-dictionary)
- [**Task**: Guess the Output](#programming-task)
---

## Create Dictionaries 
A dictionary is a collection of key/value pairs. It is similar to associative arrays in other programming languages.

To create a dictionary, we put the key/value pairs separated by a colon `:` inside the curly braces `{}`.

```python
person1 = {"name": "Linus", "age": 21}
print(person1)
```

**Output**
```
{"name": "Linus", "age": 21}
```

|Key|Value|
|---|---|
|"name"|"Linus"|
|"age"|21|

>**Notes:**
>- Keys of a dictionary can be any immutable objects like numbers, strings and tuples. However, they cannot be objects that can be modified like lists.
>- Keys must be unique for identification.

---

## Access Dictionary Elements

Dictionaries are optimized to get values when the key is known.

Similar to numbered indexes like `0`, `1`, `2` to get elements from sequences like lists and tuples, keys are used as indices for dictionaries.

```python
person1 = {"name": "Linus", "age": 21}
print(person1["name"])
print(person1["age"])
```

**Output**

```
Linus
21
```

If we try to access a key that is not in the dictionary, we will get `KeyError`.

```python
person1 = {"name": "Linus", "age": 21}
print(person1["hobbies"])
```

**Output**
```
Traceback (most recent call last):
  File "<string>", line 2, in <module>
KeyError: 'hobbies'
```

Sometimes instead of getting this error, we may just want to know if the key exists or not and decide what to do based on it

In that case we can use the dictionary's `get()` method:

```python
person1 = {"name": "Linus", "age": 21}
print(person1.get("namr"))
print(person1.get("hobbies"))
```

**Output**
```
Linus
None
```

Instead of an error, we get `None` which denotes empty or no value. This value can be used with `if` statement to make different decision as per the need.

We can also pass a second default argument to the `get()` method that will be returned instead of `None` if the key is not found.

```python
person1 = {"name": "Linus", "age": 21}
print(person1.get("hobbies", ["dancing", "fishing"]))
```

**Output**
```
["dancing", "fishing"]
```

---

## Add and Change Dictionary Elements

```python
person1 = {"name": "Linus", "age": 21}

# changing existing keys
person1["name"] = "Dennis"
print(person1)

# adding new keys
person1["hobbies"] = ["dancing", "fishing"]
print(person1)
```

**Output**

```
{'name': 'Dennis', 'age': 21}
{'name': 'Dennis', 'age': 21, 'hobbies': ['dancing', 'fishing']}
```

---

## Remove Elements From a Dictionary

To remove an item from the dictionary, we can use the dictionary's `pop()` method. The `pop()` method also returns the value of the removed key.

For example,

```python
person1 = {"name": "Linus", "age": 21}
print(person1.pop("name"))

print(person1)
```

**Output**

```
Linus
{"age": 21}
```

---

## Iterating Through a Dictionary

Similar to sequences, we can easily iterate through items of a dictionary by using a `for` loop. We get one key in every iteration:

```python
person1 = {"name": "Linus", "age": 21}

for key in person1:
   print(key)
   print(person1[key])
```

**Output**

```
name
Linus
age
21
```

>**Note:** Starting from Python 3.7, the order of items in a dictionary is preserved. So when we iterate through a dictionary, we get the keys in the order in which they are inserted in the dictionary.

---

## Programming Task

**Can you guess the output of this program?**

```python
synonyms = {"mountain": "peak", "forest": "jungle"}
print("1.", synonyms["mountain"])

synonyms["terrain"] = "land"
print("2.", synonyms)

synonyms.pop("forest")
print("3.", synonyms)
```

**Output**
```
1. peak
2. {'mountain': 'peak', 'forest': 'jungle', 'terrain': 'land'}
3. {'mountain': 'peak', 'terrain': 'land'}
```
