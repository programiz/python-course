# Python `pass`

**Video link:** [https://youtu.be/n4B3zYfk_Pg](https://youtu.be/n4B3zYfk_Pg)

In this video, we learned about the `pass` statement in Python.

**Programs in the Video**

- [Python pass Statement](#python-pass-statement)

---
## Python `pass` Statement
The `pass` statement is a null statement which is used as a placeholder for future implementation of functions, loops, etc.

Suppose you need to create a loop or a decision making a statement. However, we are not sure yet what its body will be.

Let's try doing something like this:

```python
number = 5.5

if number > 0.0:
    # implement this later
```

This results in an error message. It is because the body of the `if` statement is empty; comments don't count because Python completely ignores comments.

```
File "<string>", line 4
    # implement this later
                         ^
SyntaxError: unexpected EOF while parsing
```

In such scenarios, we can use the `pass` statement.

```python
number = 5.5

if number > 0.0:
    pass
```

This code will run without any errors.

---

So, whenever you need to create loops, `if...else` statements, functions, and classes with an empty body, use the `pass` statement.
