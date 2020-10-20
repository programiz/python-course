# Python range() Function

**Video link:** [https://youtu.be/muKeRgZ9LnU](https://youtu.be/muKeRgZ9LnU)

In this video, we learned about the Python `range()` function that returns a sequence.

**Programs in the Video**

- [Using range()](#using-range)
- [`range()` in `for` Loop](#range-in-for-loop)
- [`range()` with only `stop` Parameter](#range-with-only-stop-parameter)
- [`range()` with `step` Parameter](#range-with-step-parameter)
- [**Task**: Create Given List](#programming-task)
---

## Using `range()`
Suppose, we want a sequence of numbers from `1` and `10`. To get this sequence, we can use the `range()` function like:

```python
result = range(1, 11)
print(result)
```

**Output**
```
range(1, 11)
```

The `range()` function returns a range object which is a sequence of numbers. We can see what is inside this object by converting it to other types like `list`.

```python
result = range(1, 11)

# converting to list
result = list(result)

print(result)
```

**Output**
```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

>**Notes:**
>- Here, the start of the sequence `1` is inclusive, but the end `11` is exclusive. That's why it gives us a sequence from `1` up to `10`, and not `1` up to `11`.
>- By default, the step between the numbers (difference between two consecutive elements) is `1`.

---

## `range()` in `for` Loop
Since `range()` generates a sequence of numbers, it is commonly used with `for` loops to iterate over the loop a certain number of times.

For example,

```python
for value in range(1, 6):
    print(value, "iteration")
```

**Output**

```
1 iteration
2 iteration
3 iteration
4 iteration
5 iteration
```

---

## `range()` with only `stop` Parameter

In our examples up to now, we have passed two parameters to the `range()` function:
- `start` - start of the sequence
- `stop` - end of the sequence (exclusive)

It is also possible to use `range()` without passing the `start` parameter. If the `start` parameter is not passed, `0` is used as its default value.

```python
result = range(11)

result = list(result)
print(result)
```

**Output**

```
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

To iterate a loop 5 times we can now simply use:

```python
for value in range(5):
    print(value)
```

**Output**

```
0
1
2
3
4
```

---

## `range()` with `step` Parameter

By default, the difference between two consecutive numbers in the sequence is `1`.

For example,

```python
result = list(range(1, 11))
print(result)
```

**Output**

```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

It is because the default value of the `step` parameter of the `range()` function is `1`. The above code is equivalent to:

```python
result = list(range(1, 11, 1))
print(result)
```

If we change the `step` argument to 3:

```python
result = list(range(1, 11, 3))
print(result)
```

**Output**
```
[1, 4, 7, 10]
```
---

We can also use negative numbers in the range function:

```python
result = list(range(5, -6, -1))
print(result)
```

**Output**

```
[5, 4, 3, 2, 1, 0, -1, -2, -3, -4, -5]
```

>**Note:** `range()` only works for integers. We cannot use floating-point numbers inside the `range()` function.

---

## Programming Task

**Can you create the following list using the range function?**
```
[3, 6, 9, 12, 15, 18, 21, 24, 27, 30]
```

```python
sequence = range(3, 31, 3)

print(list(sequence))
```

**Output**
```
[3, 6, 9, 12, 15, 18, 21, 24, 27, 30]
```
