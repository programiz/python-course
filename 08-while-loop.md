# Python while Loop

**Video link:** [https://youtu.be/5AOfDuV6X30](https://youtu.be/5AOfDuV6X30)

In this video, we learned about loops to repeat certain blocks of code, specifically using the `while` loop.

**Programs in the Video**

- [Python while Loop](#python-while-loop-1)
- [**Task**: Guess the output](#programming-task-1)
- [**Example**: Multiplication Table](#example-multiplication-table)
- [**Task**: Reverse Multiplication Table](#programming-task-2)

---

## Python `while` loop
Looping is a fundamental concept in all programming languages, not just Python. They are used to repeat a block of code multiple times as per our requirement. One such type of loop is the `while` loop.

The syntax of the `while` loop in Python is:

```
while test_condition:
    statement(s)
```

Here, the statements inside the `while` loop are executed for as long as `test_condition` evaluates to `True`.

---

### Example: Using `while` Loops

```python
count = 0

while count < 5:
    print("I am inside a loop.")
    print("Looping is interesting.")
```

**Output**

```
I am inside a loop.
Looping is interesting.
...
```

Here, the test condition is never `False`, so the loop runs forever until the system's memory runs out.

---

Generally, we want programs that terminate at one point. For that, we can alter the value of `count` at every iteration like:

```python
count = 0

while count < 5:
    print("I am inside a Loop.")
    print("Looping is interesting.")
    count = count + 1
```

**Output**

```
I am inside a loop.
Looping is interesting.
I am inside a loop.
Looping is interesting.
I am inside a loop.
Looping is interesting.
I am inside a loop.
Looping is interesting.
I am inside a loop.
Looping is interesting.
```

To understand what is going on let's print the value of `count`:

```python
count = 0

while count < 5:
    print(count)
    count = count + 1
```

**Output**

```
0
1
2
3
4
```
Here, the block of code executes only **5** times as `count` goes from **0** to **4**. At `count = 5` the test condition is `False` and the loop terminates. 

---

## Programming Task 1

**Can you guess the output of this program?**

```python
count = 5

while count <= 10:
    print(count)
    count = count + 1
```

**Output**

```
5
6
7
8
9
10
```

---

## Example: Multiplication Table

```python
number = int(input("Enter a number: "))

count = 1

while count <= 10:
    product = number * count
    print(product)
    count = count + 1
```

**Output**

```
Enter a number: 6
6
12
18
24
30
36
42
48
54
60
```

To make it more readable, we can print `number`, `count`, and `product` adjacently using the following code:

```python
number = int(input("Enter a number: "))

count = 1

while count <= 10:
    product = number * count
    print(number, "x", count, "=", product)
    count = count + 1
```

**Output**

```
Enter a number: 6
6 * 1 = 6
6 * 2 = 12
6 * 3 = 18
6 * 4 = 24
6 * 5 = 30
6 * 6 = 36
6 * 7 = 42
6 * 8 = 48
6 * 9 = 54
6 * 10 = 60
```

---

## Programming Task 2

**Can you modify our multiplication table program so that we get a multiplication table from 10 to 1 instead of 1 to 10.**

```python
number = int(input("Enter a number: "))

count = 10

while count >= 1:
    product = number * count
    print(number, "x", count, "=", product)
    count = count - 1
```

**Output**

```
Enter a number: 6
6 x 10 = 60
6 x 9 = 54
6 x 8 = 48
6 x 7 = 42
6 x 6 = 36
6 x 5 = 30
6 x 4 = 24
6 x 3 = 18
6 x 2 = 12
6 x 1 = 6
```