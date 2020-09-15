# Python Comments

**Video link:** [https://youtu.be/rhF1x2lnRQA](https://youtu.be/rhF1x2lnRQA)

In this video, we learned about Python comments that make our code much more easier to read and understand.

**Programs in the Video**

- [Python Comments](#python-comments-1)
- [Prevent Executing Code Using Comments](#prevent-executing-code-using-comments)
- [Python Multiline Comments](#python-multiline-comments)
- [Why are Comments Important?](#why-are-comments-important)

---

## Python Comments
Comments are hints that we can add to our program to make our code easier to understand. Let's take an example.

Suppose we have a program to print a text entered by the user.

```python
name = input("Enter your name: ")
print("Your name is", name)
```

To make this program a bit more readable, we can add comments like:

```python
# program to take the user's name

name = input("Enter your name: ")
print(name)
```

**Output**
```
Enter your name: Ninja
Ninja
```

Python single-line comments start with a **hash(#)** symbol and are completely ignored by Python interpreter.

>**Note**: Do not use unnecessary comments for self-explanatory blocks of code.

---

## Prevent Executing Code Using Comments

We can also use comments to debug our code. Rather than removing them completely, it is a common practice to comment out codes so that they are ignored during execution.

**For example:**

```python
name = input("Enter name: ")
age = int(input("Enter age: "))

print("name:", name)
print("age:", age)
```

Suppose we don't want to run the input statement to take the age at this moment. So instead of removing them, we can comment them:


```python
name = input("Enter name: ")
# age = int(input("Enter age: "))

print(name)
# print(age)
```

**Output**

```
Enter name: Felix
name: Felix
```

Later on, we can just remove these hashes to run the commented code again.

>**Note**:  Remember the keyboard shortcut to apply comments. In most text editors, it's **Ctrl + /** if you are on Windows & **Cmd + /** if you are on a Mac.

---

## Python Multiline comments

Python doesn't have multiline comments like other programming languages such as C++ and Java. However, we can use the hash symbol at the beginning of each line to get the same effect.


```python
# print(1)
# print(2)
# print(3)
```

You can also use multiline strings as comments like:

```python
'''This program takes an integer input from the user
and prints it'''

number = int(input("Enter an integer: "))
print("You entered:", number)
```

**Output**

```
Enter an integer: 70
You entered: 70
```

We can see that these unassigned multiline strings are ignored.

---

## Why are Comments Important?

* Comments make it easier for other developers to understand and use your code.
* Comments are also used for simple debugging purposes.

>**Note**: Comments should not be used as a substitute to explain poorly written code. You should always try to write clean, understandable code, and then use comments as an addition.