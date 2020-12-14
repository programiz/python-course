# Python Inheritance

**Video link:** [https://youtu.be/C8qE3mKiBrQ](https://youtu.be/C8qE3mKiBrQ)

In this video, you learned about inheritance in Python with the help of examples. We also covered the concepts of method overriding and the `super()` function.

**Programs in the Video**

- [Inheritance in Python](#inheritance-in-python)
- [Example of Inheritance](#example-of-inheritance)
- [Method Overriding](#method-overriding)
- [The `super()` function](#the-super-function)

---

## Inheritance in Python
Let's derive a dog and cat class from an animal class and get a feel of how inheritance works.

Suppose we have an `Animal` class:

```python
class Animal:
    def eat(self):
        print("I can eat")
```

Now, let's derive a `Dog` class from `Animal`:

```python
class Animal:
    def eat():
        print("I can eat")
        
class Dog(Animal):
    def bark(self):
        print("I can bark")
```

Objects of `Dog` can access methods and attributes of both `Dog` and `Animal`:


```python
class Animal:
    def eat():
        print("I can eat")
        
class Dog(Animal):
    def bark(self):
        print("I can bark")

dog1 = Dog()

dog1.bark()
dog1.eat()
```

**Output**
```
I can bark
I can eat
```

Similarly, if we want, we can derive another `Cat` class from the `Animal` class:


```python
class Animal:
    def eat():
        print("I can eat")
        
class Dog(Animal):
    def bark(self):
        print("I can bark")

class Cat(Animal):
    def get_grumpy(self):
        print("I am getting grumpy.")

dog1 = Dog()

dog1.bark()
dog1.eat()

cat1 = Cat()
cat1.eat()
```

**Output**

```
I can bark
I can eat
I can eat
```

---

## Example of Inheritance

Let's implement a program to calculate the perimeter of different polygons like triangles and quadrilaterals using inheritance.

Let's first create a base class called `Polygon`:

```python
class Polygon:
    def __init__(self, sides):
        self.sides = sides

    def display_info(self):
        print("A polygon is a two dimensional shape with straight lines")

    def get_perimeter(self):
        perimeter = sum(self.sides)
        return perimeter
```

All polygons like triangles and quadrilaterals will derive these features.

Let's create a `Triangle` class that will inherit from the `Polygon` class:


```python
class Polygon:
    def __init__(self, sides):
        self.sides = sides

    def display_info(self):
        print("A polygon is a two dimensional shape with straight lines")

    def get_perimeter(self):
        perimeter = sum(self.sides)
        return perimeter


class Triangle(Polygon):
    def display_info(self):
        print("A triangle is a polygon with 3 edges")
```

I have redefined the `display_info()` method to display information specific to triangles.

Similarly, I will also define a new `Quadrilateral` class.

```python
class Polygon:
    def __init__(self, sides):
        self.sides = sides

    def display_info(self):
        print("A polygon is a two dimensional shape with straight lines")

    def get_perimeter(self):
        perimeter = sum(self.sides)
        return perimeter


class Triangle(Polygon):
    def display_info(self):
        print("A triangle is a polygon with 3 edges")


class Quadrilateral(Polygon):
    def display_info(self):
        print("A quadrilateral is a polygon with 4 edges")
```

Now, let's find the perimeter of a triangle. I will create an object from `Triangle` and use its `get_perimeter()` method.


```python
class Polygon:
    def __init__(self, sides):
        self.sides = sides

    def display_info(self):
        print("A polygon is a two dimensional shape with straight lines")

    def get_perimeter(self):
        value = 0
        for side in self.sides:
            value += side
        return value


class Triangle(Polygon):
    def display_info(self):
        print("A triangle is a polygon with 3 edges")


class Quadrilateral(Polygon):
    def display_info(self):
        print("A quadrilateral is a polygon with 4 edges")

t1 = Triangle([5, 6, 7])
perimeter = t1.get_perimeter()
print("Perimeter:", perimeter)
```

**Output**

```
Perimeter: 18
```

---

## Method Overriding

If you have noticed, in the above example, we have the `display_info()` method in both our base class and the derived classes.

Let's see what will happen if we call the `display_info()` method for the `t1` triangle.

```python
class Polygon:
    def __init__(self, sides):
        self.sides = sides

    def display_info(self):
        print("A polygon is a two dimensional shape with straight lines")

    def get_perimeter(self):
        perimeter = sum(self.sides)
        return perimeter


class Triangle(Polygon):
    def display_info(self):
        print("A triangle is a polygon with 3 edges")


class Quadrilateral(Polygon):
    def display_info(self):
        print("A quadrilateral is a polygon with 4 edges")

t1 = Triangle([5, 6, 7])
perimeter = t1.get_perimeter()
print("Perimeter:", perimeter)

t1.display_info()
```

**Output**

```
Perimeter: 18
A triangle is a polygon with 3 edges
```

We can see that the `display_info()` method of the `Triangle` class is called and `display_info()` of its parent class is not executed.

This is called method overriding.

**If the same method is defined in both the base and the derived class, then the method of the derived class overrides the method of the base class.**


If we need, we can call the `display_info()` method of our parent `Polygon` class from inside its child classes like this: 

```python
class Polygon:
    def __init__(self, sides):
        self.sides = sides

    def display_info(self):
        print("A polygon is a two dimensional shape with straight lines")

    def get_perimeter(self):
        perimeter = sum(self.sides)
        return perimeter


class Triangle(Polygon):
    def display_info(self):
        print("A triangle is a polygon with 3 edges")
        Polygon.display_info(self)


class Quadrilateral(Polygon):
    def display_info(self):
        print("A quadrilateral is a polygon with 4 edges")

t1 = Triangle([5, 6, 7])
perimeter = t1.get_perimeter()
print("Perimeter:", perimeter)

t1.display_info()
```

**Output**
```
Parameter: 18
A triangle is a polygon with 3 edges
A polygon is a two dimensional shape with straight lines
```

>**Note:** `Polygon` is the name of the parent class. Since we are calling the method using a class rather than an object, we also need to pass the `self` object manually.

This code is a bit more unorthodox than what we have been using. There is a more elegant way to achieve the same task by using the `super()` function.

---

## The `super()` function

The `super()` function returns a temporary object of the superclass for a subclass.

```python 
class Polygon:
    def __init__(self, sides):
        self.sides = sides

    def display_info(self):
        print("A polygon is a two dimensional shape with straight lines")

    def get_perimeter(self):
        value = 0
        for side in self.sides:
            value += side
        return value


class Triangle(Polygon):
    def display_info(self):
        print("A triangle is a polygon with 3 edges")
        # Polygon.display_info(self)
        super().display_info()

class Quadrilateral(Polygon):
    def display_info(self):
        print("A quadrilateral is a polygon with 4 edges")

t1 = Triangle([5, 6, 7])
perimeter = t1.get_perimeter()
print("Perimeter:", perimeter)

t1.display_info()
```

**Output**

```
Perimeter: 18
A triangle is a polygon with 3 edges
A polygon is a two dimensional shape with straight lines
```

In this case, `super()` is an object of `Polygon`. We are using it to call `display_info()` of the `Polygon` class.