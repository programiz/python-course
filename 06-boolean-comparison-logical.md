# Python Booleans, Comparison and Logical Operators

**Video link:** [https://youtu.be/mrryXQnlYN8](https://youtu.be/mrryXQnlYN8)

In this video, we learned about the boolean data type as well as comparison and logical operators in Python.

**Programs in the Video**

- [Boolean Data Type](#boolean-data-type)
- [Comparison Operators](#comparison-operators)
- [Logical Operators](#logical-operators)
- [**Task**: Guess the Output](#programming-task)

---

## Boolean Data Type
Boolean is a logical data type that represents one of two values: either `True` or `False`.

```python
result1 = True
result2 = False

print(result1) # True
print(result2) # False
```

---

## Comparison Operators
Python has a set of comparison operators that allow us to compare two values. If the comparison is right, we get `True` and if the comparison is wrong, we get `False`.

```python
number = 5
print(number < 10) # True

number = 15
print(number < 10) # False

```

Here's a list of comparison operators:

```
Comparison Operators:

<          Less than
>          Greater than
==         Equal   
!=         Not equal
>=         Greater than or equal to
<=         Less than or equal to
```

## Examples: Comparison Operators

```python
# comparison operators in action

number = 15
print(number > 10) # True

number = 10
print(number > 10) # False

number = 10
# equal to
print(number == 10) # True

number = 10.0
# comparing float and integer
print(number == 10) # True

number = '10'
# comparing string and integer
print(number == 10) # False

number = '10'
# not equal to
print(number != 10) # True

number = 10
# less than or equal to
print(number <= 10) # True

number = 10
# greater than or equal to
print(number >= 10) # True
```

---


## Logical Operators
Python also has three logical operators that operate on the boolean values. Here's a list of the logical operators:

```
Logical Operators

and         True if both operands are True
or          True if either of the operands is True
not         True if the operand is False
```

---

### `and` Operator

If both of the expressions are `True`, then the result is `True`.

```python
age = 22
gpa = 3.8

result = age >= 18 and gpa > 3.6
print(result) # True
```

However, if either of these expressions is `False`, the result is `False`.

```python
age = 22
gpa = 3.8

print(age >= 18 and gpa > 3.9) # false
```

---

### `or` Operator
If either of the expression is `True`, then the result is `True`. If both expressions are `False`, only then the result is `False`.

```python
age = 22
gpa = 3.8

print(age >= 18 or gpa > 3.9)
```

---

### `not` Operator
The not operator gives the complement of the result:

* If `True`, result is `False`.
* If `False`, result is `True`.

```python
result = True
print(result) # True

result = True
print(not result) # False
```
---

## Programming Task

**Can you guess the output of this program?**


```python
language = "Python"
print("1.", language == "python")

age = 18
print("2.", age >= 18)
print("3.", age > 18)

print("4.", age >= 18 and language == "Java")
```

**Output**

```
1. False
2. True
3. False
4. False
```
