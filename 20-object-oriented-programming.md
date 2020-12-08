# Python Object-Oriented Programming

**Video link:** [https://youtu.be/pnWINBJ3-yA](https://youtu.be/pnWINBJ3-yA)

In this video, you learned about object-oriented programming along with the help of examples.

**Programs in the Video**

- [Python Classes and Objects](#python-classes-and-objects)
- [The `__init__()` Method](#the-__init__-method)
- [Example: Add Two Complex Numbers](#example-add-two-complex-numbers)
- [Why object-oriented programming?](#why-object-oriented-programming)
- [**Task**: Perimeter of Triangle](#programming-task)

---

## Python Classes and Objects
Think of a class as a blueprint of a house. It contains all the details about the floors, doors, windows etc.
Based on these descriptions we build the house. The actual physical house is the object.

```python
class Student:
    pass

student1 = Student()
student2 = Student()
```

Here, `student1` and `student2` are objects of the `Student` class.

Now, we can start adding different attributes to these object instances.

```python
class Student:
    pass

student1 = Student()
student1.name = "Harry"
student1.marks = 85

print(student1.name)
print(student1.marks)
```

**Output**
```
Harry
85
```

Let's now see how we can define methods inside a class.

```python
class Student:
    def check_pass_fail(self):
        if self.marks >= 40:
            return True
        else:
            return False

student1 = Student()
student1.name = "Harry"
student1.marks = 85

did_pass = student1.check_pass_fail()
print(did_pass)
```

**Output**

```
True
```

Here, the `check_pass_fail()` method is defined inside the `Student` class.

Now, any object created from the Student class can access this method.

We have called this method without passing any arguments, however, the method definition takes one argument named `self`.

Whenever we define methods for a class, we need to use `self` as the first parameter.
This `self` represents the object calling it. In our example, `self` refers to the `student1` object, and `self.marks` refers to the `marks` attribute of `student1`.

Let's try the same for another student object.

```python
class Student:
    def check_pass_fail(self):
        if self.marks >= 40:
            return True
        else:
            return False

student1 = Student()
student1.name = "Harry"
student1.marks = 85

did_pass = student1.check_pass_fail()
print(did_pass)

student2 = Student()
student2.name = "Janet"
student2.marks = 30
did_pass = student2.check_pass_fail()
print(did_pass)
```

**Output**

```
True
False
```

>**Note:** Using `self` is just a convention but we highly recommend using `self`.

---

## The `__init__()` Method
Adding attributes to the object manually after defining it is not a good practice.

Python offers a much more elegant and compact way of defining attributes right while instantiating the object.
For that, we use the `init` method.

If you are coming from other languages like C++ or Java, the Python `__init__()` method closely resembles constructors.

```python
class Student:
    
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks
        
    def check_pass_fail(self):
        if self.marks >= 40:
            return True
        else:
            return False

student1 = Student("Harry", 85)
print(student1.name)
print(student1.marks)
```

**Output**

```
Harry
85
```

When we create an object, this `__init__()` method is automatically called. We have used `Harry` and `85` during object creation,
these values are passed to `name` and `marks` in the `__init()__` method.

Remember, the first parameter `self` represents the object calling it, while the second and third parameter take the two arguments which we used during object creation.

Now, for the `student1` object, the `name` attribute will be `Harry` and `marks` will be `85`.

Let's try creating one more object.

```python
class Student:
    
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks
        
    def check_pass_fail(self):
        if self.marks >= 40:
            return True
        else:
            return False

student1 = Student("Harry", 85)
print(student1.name)
print(student1.marks)

student2 = Student("Janet", 30)
print(student1.name)
print(student1.marks) 
```

**Output**
```
Harry
85
Janet
30
```

We get the attributes of student2 as well.

Let's check if they passed or failed the exams using the `check_pass_fail()` method.

```python
class Student:
    
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks
        
    def check_pass_fail(self):
        if self.marks >= 40:
            return True
        else:
            return False

student1 = Student("Harry", 85)
did_pass = student1.check_pass_fail()
print(did_pass)

student2 = Student("Janet", 30)
did_pass = student2.check_pass_fail()
print(did_pass)
```

**Output**

```
True
False
```

---

## Example: Add Two Complex Numbers

In this example, we will add two complex numbers manually.
Python already handles this by default, but we will create our own Complex class to better understand the concepts of object-oriented programming.

If you do not know, a complex number has real and imaginary parts. When we add two complex numbers, we need to add real and imaginary parts separately.

Let's first create a class that represents complex numbers.

```python
class Complex:
    def __init__(self, real, imag):
        self.real = real
        self.imag = imag

n1 = Complex(5, 6)
n2 = Complex(-4, 2)
```

Now, let's create a method to add these complex numbers.

```python
class Complex:
    def __init__(self, real, imag):
        self.real = real
        self.imag = imag
        
    def add(self, number):
        real = self.real + number.real
        imag = self.imag + number.imag
        result = Complex(real, imag)
        return result

n1 = Complex(5, 6)
n2 = Complex(-4, 2)
result = n1.add(n2)
```

The value returned by `add()` is itself an object of the `Complex` class.

Let's print the attributes of the result object.

```python
class Complex:
    def __init__(self, real, imag):
        self.real = real
        self.imag = imag
        
    def add(self, number):
        real = self.real + number.real
        imag = self.imag + number.imag
        result = Complex(real, imag)
        return result

n1 = Complex(5, 6)
n2 = Complex(-4, 2)
result = n1.add(n2)

print("real =", result.real)
print("imag =", result.imag)
```

**Output**

```
real = 1
imag = 8
```

---

## Why object-oriented programming?

Creating objects allows us to organize related data and functionalities together. This helps us to write structured and flexible code. 

Now, instead of thinking in terms of individual data and functions, we start thinking in terms of objects and how one object interacts with the other.
This helps us to divide a complex problem into smaller sub-problems.

Also, using an object-oriented style of programming makes our code reusable because we can define multiple objects with similar attributes and functionalities from a single Class.

---

## Programming Task

**Task**

- Create a class named `Triangle`.
- Create an object from it. The object will have three attributes named `a`, `b` and `c` that represent the sides of the triangle.
- The `Triangle` class will have two methods:
    - The `__init__()` method to initialize the sides
    - A Method to calculate the perimeter of the triangle from its sides
- The perimeter of the triangle should be printed from outside the class

Here's the barebone for this program:

```python
class Triangle:
    def __init__(self, a, b, c):
        # write code here
        pass
    
    # write code here
    
t1 = Triangle(3, 4, 5)
# write code here
```

#### Solution

```python
class Triangle:
    def __init__(self, a, b, c):
        self.a = a
        self.b = b
        self.c = c
    
    def get_perimeter(self):
        perimeter = self.a + self.b + self.c
        return perimeter
    
t1 = Triangle(3, 4, 5)

perimeter = t1.get_perimeter()
print("The perimeter of the t1 triangle is", perimeter)
```

**Output**
```
The perimeter of the t1 triangle is 12
```
