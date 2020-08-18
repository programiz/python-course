# Print Function and Variables

In this lesson, we learned about the `print()` function and variables.

## print() Function

The `print()` is a built-in function in Python. It prints whatever object that is inside the parentheses `()`.

### Program to Print Strings

A string is a textual data. They must be wrapped inside quotation marks.

```
# Printing Strings

print('Hello World')
print("Python 3 is awesome")g
```

**Output**

```
Hello World
Python 3 is awesome
```

### Program to Print Numbers

The `print()` function can also be used to print numbers. There are two commonly used numeric data in Python:

- integers: 5, -34, 0 etc.
- floating-point numbers: 5.0, -45.2, 3.5 etc.

```
# Printing numbers

print(5)
print(34.5)
```

**Output**

```
5
34.5
```

## Variables in Python

We use variables to store data and use them later in the program.

### Store Data in a Variable

We use the `=` operator to assign a value to a variable.

```
# store data in variables and print them

city = "Kathmandu"
print(city)
```

**Output**

```
Kathmandu
```

### Change Value Stored in a Variable

We can also change the data a variable holds.

```
# change value of a variable
city = "Kathmandu"
print(city)

city = "New York"
print(city)
```

**Output**

```
Kathmandu
New York
```

### Assign one Variable to Another

```
# assign one variable to another

city = "Kathmandu"
destination_city = "New York"

city = destination_city
print(city)
```

**Output**

```
New York
```

```
# assign one variable to another

my_favorite_number = 5
print(my_favorite_number)

pi = 3.14
print(pi)

my_favorite_number = pi

print(my_favorite_number)
print(pi)
```

**Output**

```
5
3.14
3.14
```

## Print Multiple Objects in One print()

We can print multiple objects in a single `print()` function by separating them with commas.

```
# print two objects in one print()

city = "Kathmandu"
print("City:", city)
```

**Output**

```
City: Kathmandu
```

When we print more than one object in a single print() function, they are by default separated by commas.

```
# print four objects in one print()

city = "Kathmandu"
kfc_locations = 2
print("City:", city, "KFC Locations:", kfc_locations)
```

**Output**

```
City: city KFC locations:
```

## Giving Good Variable Names

We should always try to give descriptive and meaningful variable names so that it's easier to understand our code.
