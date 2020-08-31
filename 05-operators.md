# Python Operators

**Video link:**

In this video, we learned about Python operators.

**Programs in the Video**

- [Arithmetic Operators](https://github.com/programiz/python-course/blob/master/05-operators.md#arithmetic-operators)
- [Printing message before input](https://github.com/programiz/python-course/blob/master/03-input.md#printing-message-before-input)
- [Trying to take numeric input](https://github.com/programiz/python-course/blob/master/03-input.md#trying-to-take-numeric-input)
- [Print data type of integers and floating-point numbers](https://github.com/programiz/python-course/blob/master/03-input.md#print-data-type-of-integers-and-floating-point-numbers)
- [Convert strings to integers](https://github.com/programiz/python-course/blob/master/03-input.md#convert-strings-to-integers)
- [Convert non-numeric strings to numbers](https://github.com/programiz/python-course/blob/master/03-input.md#convert-non-numeric-strings-to-numbers)

---

An operator is a symbol that is used to perform operation and values and variables.

The most frequently used operator is `=`. It is used to assign data to a variable.

```
name = "Punit"
print(name)   # Punit
```

---

## Arithmetic Operators

Here's a list of arithmetic operators:

```
Addition: +
Subtraction: -
Multiplication: *
Division: /
Floor division: //
Remainder: %
Exponent: **

```

## Examples: Arithmetic Operators

```
# Arithmetic operators in action

x = 5

result = x + 10 # addition
print(result)   # 15

result = x - 10 # subtraction
print(result)   # -5

result = x \* 10 # multiplication
print(result)    # 50

result = x / 10 # division
print(result)   # 0.5

result = x ** 2 # exponent
print(result)     # 25

quotient = x // 2 ## floor division
remainder = x % 2 ## modulus

print("Quotient is", quotient) # 2
print("Remainder is", remainder) # 1

```

---

## Using parentheses

We can use parentheses to make code more readable.

```
# harder to understand

number = 34 \* 5 - 5 / 3 # 168.33333
print(number)

# easier to understand

number = (34 \* 5) - (5 / 3) # 168.33333
print(number)

```

---

## Concatenate Strings

If the `+` operator is used with strings, it concatenated the strings.

```

str1 = "Hey "
str2 = "Jude"
print(str1 + str2) # Hey Jude

```

---

## More on Assignment Operators

_Multiple assignment at once_

```

x, y = 5, 6
print(x) # 5
print(y) # 6

```

_Compound Assignment Operators_

```

x = 5
x += 10 # x = x + 10
x -= 10 # x = x - 10

```

---

##Program to Compute Discount

_Suppose you are a university student, and you need to pay 4535 dollars tuition fee for the next semester._

_The college is giving you a discount of 10% on the early payment of your tuition fee. Since it's a good offer, you decided to make an early payment. Can you find out how much money you have to pay?_

```
fee = 4530

discount_percent = 10
discount_amount = discount_percent/100\*fee
discounted_fee = fee - discount_amount

print("Fee after discount:", discounted_fee, "dollars") # 4081.5

```

---

##Programming Task

_Can you create a program to convert distance in kilometers to miles?_

_Forumula: 1 kilometer -> 0.621371 miles_

```

# Program to convert kilometers to files

distance_km = 564.5

conversion_ratio = 0.621371

distance_miles = distance_km \* conversion_ratio

print(distance_miles) # 350.7639295

```
