# Python `break` and `continue`

**Video link:** [https://youtu.be/Mho_1WO-ht4](https://youtu.be/Mho_1WO-ht4)

In this video, we learned about `break` and `continue` statements in Python that can be used to alter the flow of a normal loop.

**Programs in the Video**

- [Python break Statement](#python-break-statement)
- [Python continue Statement](#python-continue-statement)
- [Programming Task](#programming-task)

---
## Python `break` Statement
The `break` statement is used to terminate the loop completely. The control of the program flows to the statement immediately after the body of the loop.

```python
for item in range(1, 6):
    print(item)
    break
```

**Output**
```
1
```

Here, in the first iteration, the value of `item` is **1**. This is printed by the `print()` function.

When the `break` statement is encountered, the loop immediately ends, so nothing else gets printed.

If `break` was used in front of the `print()` statement, the loop would have terminated immediately without printing anything.

```python
for item in range(1, 6):
    break
    print(item)
```

---

`break` statements are almost always used inside decision-making statements like `if...else` to end the loop only when a certain condition is met.


### Using `break` Statement with `for`

```python
for item in range(1, 6):
    if item == 3:
        break
    print(item)

print("The end")
```

**Ouput**
```
1
2
The end
```

---

### Using `break` with `while`

Let's create a program that prints number entered by the user, but terminates once the user enters a negative number.

```python
while True:
    number = float(input("Enter a number: "))
    if number < 0:
        break
    print("You entered:", number)
```

**Output**

```
Enter a number: 4
You entered: 4.0
Enter a number: 67
You entered: 67.0
Enter a number: -9
```

Here, the program terminates as soon as the user enteres a negative number.

---


## Python `continue` Statement
The `continue` statement in Python skips the rest of the code inside the loop for that iteration.

The loop will not terminate but continues on with the next iteration.

---

### Example: Using `continue` with `for`

```python
for i in range(5):
    number = float(input("Enter a number: "))

    # check if number if negative
    if number < 0:
        continue

    print(number)

```

**Output**

```
Enter a number: 4
You entered: 4.0
Enter a number: 54
You entered: 54.0
Enter a number: -9
Enter a number: 76
You entered: 76.0
Enter a number: 67
You entered: 67.0
```

Here, the `continue` statement is used to skip the current iteration when the number entered by the user is negative.

Unlike `break`, `continue` does not terminate the loop entirely, the loop runs specified number of times (5 in this case).

---

## Programming Task

**Can you create a program so that all items of the `languages` list are printed except `Swift` and `C++`?**

```python
languages = ["Python", "Java", "Swift", "C", "C++"]
```

```python
languages = ["Python", "Java", "Swift", "C", "C++"]

for language in languages:
    if language == "Swift" or language == "C++":
        continue
    print(language)

```

**Output**

```
Python
Java
C
```
