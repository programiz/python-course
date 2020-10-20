# Python Set

**Video link:** [https://youtu.be/-vfzvT0Fh0A](https://youtu.be/-vfzvT0Fh0A)

In this video, we learned about a compound data type in Python called set.

**Programs in the Video**

- [Creating Sets](#creating-sets)
- [Add Items to a Set](#add-items-to-a-set)
- [Remove Items from a Set](#remove-items-from-a-set)
- [Check if an item is in a Set](#check-if-an-item-is-in-a-set) 
- [Iterating Through a Set](#iterating-through-a-set)
- [Python Set Operations](#python-set-operations)
- [**Task**: Guess the Output](#programming-task)
---

## Creating Sets
Similar to a set in mathematics, a Python set is a collection of non-duplicate and immutable items in no particular order.

To create a set, we put items separated by a colon `,` inside the curly braces `{}`.

```python
animals = {"dog", "cat", "tiger", "elephant"}
print(animals)
```

**Output**
```
{'cat', 'dog', 'tiger', 'elephant'}
```

If we add duplicate items,

```python
animals = {"dog", "cat", "tiger", "elephant", "dog"}
print(animals)
```

**Output**
```
{'cat', 'dog', 'tiger', 'elephant'}
```

We can see that there is only one dog as sets don't have duplicate items.

>**Notes:**
>- The order of items is different from how we defined them because sets are unordered.
>- We can create an empty set using `set()`. We cannot use `{}` because it creates an empty dictionary.

---

## Add Items to a Set

Sets in Python are mutable. We can add and remove items from them.

To add a single item to a set, we use the `add()` method.

```python
animals = {"dog", "cat", "tiger", "elephant", "dog"}
animals.add("monkey")

print(animals)
```

**Output**

```
{'tiger', 'monkey', 'cat', 'dog', 'elephant'}
```

We can also add all the items of iterables like lists, tuples, and other sets to a set. For that, we use the `update()` method.

```python
animals = {"dog", "tiger", "elephant"}
wild_animals = ["tiger", "leopard", "elephant"]

animals.update(wild_animals)
print(animals)
```

**Output**
```
{'tiger', 'dog', 'cat', 'elephant', 'leopard'}
```

We can also pass multiple iterables to the `update()` method:

```python
animals = {"dog", "tiger", "elephant"}
wild_animals = ["tiger", "leopard", "elephant"]

animals.update(wild_animals, {"dolphin"})
print(animals)
```

**Output**
```
{'dog', 'dolphin', 'leopard', 'elephant', 'tiger'}
```

---

## Remove Items from a Set

To remove an item in a set, we can either use the `discard()` method or the `remove()` method.

However, there is an important difference between them. If the item we are trying to remove is not in the set, `discard()` returns `None`, whereas, the `remove()` method throws an error.

```python
animals = {"tiger", "cat", "elephant", "dog"}
animals.remove("ferret")

print(animals)
```

**Output**

```
Traceback (most recent call last):
  File "<string>", line 2, in <module>
KeyError: 'ferret'
```

Meanwhile,

```python
animals = {"tiger", "cat", "elephant", "dog"}
animals.discard("ferret")

print(animals)
```

**Output**

```
{'tiger', 'elephant', 'cat', 'dog'}
```

We can also remove all items in a set at once by using the `clear()` method.

```python
animals = {"tiger", "cat", "elephant", "dog"}
animals.clear()

print(animals)
```

**Output**
```
set()
```

---

## Check if an item is in a Set

Similar to other compound data types, we can check if an item is in a set or not by using the `in` keyword.

For example,

```python
animals = {"tiger", "cat", "elephant", "dog"}
print("tiger" in animals)

print("ferret" in animals)
```

**Output**

```
True
False
```

---

## Iterating Through a Set

Similar to other sequences, we can easily iterate through items of a set by using a `for` loop.

```python
animals = {"tiger", "cat", "elephant", "dog"}

for animal in animals:
    print(animal)
```

**Output**

```
elephant
dog
tiger
cat
```

The items of the set are printed one by one. However, the order in which these items are printed is random

---

## Python Set Operations

Python sets have same properties to that of sets in mathematics. Let's look at some set operations.

### Union of Sets
The union of two sets is a set of all items in both the sets.

To find the union of sets, we can either use the `union()` method or the pipe symbol `|`.

```python
domestic_animals = {"dog", "cat", "elephant"}
wild_animals = {"lion", "tiger", "elephant"}

animals = domestic_animals.union(wild_animals)
animals1 = animals = domestic_animals | wild_animals

print(animals)
print(animals1)
```

**Output**
```
{'tiger', 'elephant', 'dog', 'cat', 'lion'}
{'tiger', 'elephant', 'dog', 'cat', 'lion'}
```
---

### Intersection of Two Sets
The intersection of two sets is a set of items that are common in both sets.

To find the union of sets, we can either use the `intersection()` method or the ampersand symbol `&`.

```python
domestic_animals = {"dog", "cat", "elephant"}
wild_animals = {"lion", "tiger", "elephant"}

common_animals = domestic_animals.intersection(wild_animals)
common_animals1 = domestic_animals & wild_animals

print(common_animals)
print(common_animals1)
```

**Output**
```
{'elephant'}
{'elephant'}
```

---

## Programming Task

**Can you guess the output of this program?**

```python
animals = {"dog", "cat", "tiger", "elephant", "dog"}
print("1.", animals)

animals.remove("cat")
animals.remove("dog")
print("2.", animals)

animals.add("snake")
print("3.", animals)

result = {1, 5, 10} & {100, 10, 3, 5}
print("4.", result)
```

**Output**
```
1. {'dog', 'cat', 'tiger', 'elephant'}
2. {'tiger', 'elephant'}
3. {'elephant', 'snake', 'tiger'}
4. {10, 5}
```
