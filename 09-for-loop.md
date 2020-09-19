# Python for Loop

**Video link:** [https://youtu.be/yaqMSBr_NCU](https://youtu.be/yaqMSBr_NCU) 

In this video, we learned about loops to repeat certain blocks of code, specifically using the `for` loop.

**Programs in the Video**

- [Python Sequences](#python-sequences)
- [Python for Loop](#python-for-loop-1)
- [Looping Through a List](#looping-through-a-list)
- [Python range()](#python-range)
- [**Example**: Multiplication Table](#example-multiplication-table)
- [**Task**: Sum of Numbers](#programming-task)

---
## Python Sequences
A sequence is a collection of items in an order. We have already used strings numerous times in our programs.
A string is basically a sequence of characters.

```python
# Python sequences
text = "Python"
languages = ['English', 'French', 'German']
```

The sequence with three items separated by commas and enclosed in square brackets is called a list.
We will learn about them in the upcoming tutorials.

---

## Python `for` loop
The for loop in Python is used to iterate over a sequence, and in each iteration, we can access individual items of that sequence.

The syntax of the `for` loop in Python is:

```
for item in sequence:
   statement(s)
```

Here, the statements inside the `for` loop are executed for every item in `sequence`.

---

### Example: Using `for` Loops

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

Here, using a for loop we have accessed individual items of this string one by one.

During the first iteration of the loop, the variable `character` will be the first letter `'P'` and it gets printed to the screen.

The loop continues similarly until we reach the last item in the sequence.

---

## Looping Through a List

We can use the `for` loop to iterate through each item of this list one by one.

```python
languages = ["English", "French", "German"]

for language in languages:
    print(language)
```

**Output**

```
English
French
German
```

---

## Python `range()`

In the previous tutorial, we used `while` loop to repeat a block of code a certain number of times.

```python
count = 1

while count <= 5:
    print(count)
    count = count + 1
```

**Output**

```
1
2
3
4
5
```

We can use `range()` with a `for` loop to write this program in a much simpler way.

```python
for count in range(1, 6):
    print(count)
```

**Output**
```
1
2
3
4
5
```

The `range()` function creates a sequence of numbers from 1 to 5. The last value passed (6 in this case) is exclusive.

---
## Example: Multiplication Table

```python
number = int(input("Enter an integer: "))

for count in range(1, 11):
    product = number * count
    print(number, "*", i, "=", product)
```

**Output**
```
Enter an integer: 9
9 * 1 = 9
9 * 2 = 18
9 * 3 = 27
9 * 4 = 36
9 * 5 = 45
9 * 6 = 54
9 * 7 = 63
9 * 8 = 72
9 * 9 = 81
9 * 10 = 90
```

---

## Programming Task

**Can you create a program to find the sum of numbers from 1 to 100.**

The result should be equal to **1 + 2 + 3 + ... + 100**.

```python
total = 0

# looping from 1 to 100
for number in range(1, 101):
    total = total + number
print(total)
```

**Output**

```
5050
```
