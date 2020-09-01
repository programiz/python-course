# Take Input from the User

**Video link:** [https://youtu.be/DRBybZ6hsY0](https://youtu.be/DRBybZ6hsY0)

In this video, we learned to take input from the user.

**Programs in the Video**

- [Take input from the user](#take-input-from-the-user-1)
- [Printing message before input](#printing-message-before-input)
- [Trying to take numeric input](#trying-to-take-numeric-input)
- [Print data type of integers and floating-point numbers](#print-data-type-of-integers-and-floating-point-numbers)
- [Convert strings to integers](#convert-strings-to-integers)
- [Convert non-numeric strings to numbers](#convert-non-numeric-strings-to-numbers)

---

## input() Function

We use the `input()` function to take input from the user.

### Take Input from the User

```python
# Take user input

name = input()
print(name)
```

**Output**

```
Felix
Felix
```

---

### Printing Message Before Input

We can pass a string message inside `input()` to make our program descriptive.

```python
# Displaying prompt message before taking input

name = input("Enter name: ")
print(name)
```

**Output**

```
Enter name: Felix
Felix
```

---

## Trying to take numeric input

The `input()` function always takes input in the string format. We can check this by using the `type()` function.

```python
# Print the type of input.

number = input("Enter a number: ")
print(type(number))
```

**Output**

```
<class 'str'>
```

`<class 'str'>` means it's a string.

---

### Print data type of integers and floating-point numbers

```python
# print type of integers and floats

number1 = 5
print(type(number1))

number2 = 5.5
print(type(number2))
```

**Output**

```
<class 'int'>
<class 'float'>
```

---

## Convert strings to integers and floats

We cannot directly take numeric inputs using the `input()` function. However, we can convert strings to integers and floats using the 'int()' and 'float()' functions respectively.

### Convert strings to integers

```python
number = input("Enter a number: ")

# convert numeric string to integer
number = int(number)

print(type(number))
```

**Output**

```
<class 'int'>
```

Here, we have converted number in string format to integer.

We can also write this above program as:

```python
# take input and convert it to int
number = int(input("Enter a number: "))

print(type(number))
```

**Output**

```
<class 'int'>
```

---

### Convert strings to floats

Similary, we can use `float()` to convert a string to a floating-point number.

```python
# take input and convert it to float
number = float(input("Enter a number: "))

print(type(number))
```

**Output**

```
<class 'float'>
```

---

## Convert non-numeric strings to numbers

We can only convert numeric strings (string in number format) to numbers. If we try to convert non-numeric strings to numbers, we will get an error.

```python
# take input and convert it to float
number = float(input("Enter a number: "))

print(type(number))
```

**Output**

```
Enter a number: Punit
Traceback (most recent call last):
  File "<string>", line 1, in <module>
ValueError: could not convert string to float: 'Punit'
```
