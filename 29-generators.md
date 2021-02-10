# Python Generators

**Video link:** [https://youtu.be/ebj4qZ8SyMU](https://youtu.be/ebj4qZ8SyMU)

In this video, we learned how to create custom iterators in Python using generator functions.

**Programs in the Video**

- [Why Generators?](#why-generators)
- [Python Generators](#python-generators-1)
- [Infinite Stream of Data with Generators](#infinite-stream-of-data-with-generators)
- [**Task**: Create Infinite Stream of Odd Numbers](#programming-task)
---

## Why Generators?
Before we learn about generators, let's see an example of an iterator implemented in Python.

```python
class Even:
    def __init__(self, max):
        self.n = 2
        self.max = max

    def __iter__(self):
        return self

    def __next__(self):
        if self.n <= self.max:
            result = self.n
            self.n += 2
            return result
        else:
            raise StopIteration

numbers = Even(10)

print(next(numbers))
print(next(numbers))
print(next(numbers))
```

**Output**
```
2
4
6
```

This code generates a sequence of even numbers. For this we have created a custom iterator.

For an object to be iterator it should implement:
- The  `__iter__()` method - To return an iterator object
- The  `__next__()` method - To return the next element in the stream & possibly raise `StopIteration` exception when
there are no values to be returned.

As you can see, the process of creating iterators is both lengthy and counterintuitive. Generators come to the rescue in such situations.

---

## Python Generators

Now, let's implement the same iterator from previous section using a generator.
A generator is simply a function but with slight modification. In generator function, we use the `yield` keyword to get the next item of the iterator.

```python
def even_generator():
    n = 0
    
    n += 2
    yield n

    n += 2
    yield n
    
    n += 2
    yield n

numbers = even_generator()

print(next(numbers))
print(next(numbers))
print(next(numbers))
```

**Output**

```
2
4
6
```

First, we have created a generator function that has three yield statements. When we call this generator, it returns an iterator object.

Then, we have called the `__next__()` method to retrieve elements from this iterator. The first `yield` returns the value of `n = 2`.

The difference between `return` and `yield` is that the `return` statement terminates the function completely while the `yield` statement pauses the function saving all its states for next successive calls.

So, when we call `yield` for the second and third time, we get `4` and `6` respectively.

Let's make this generator return even numbers till a certain `max` number:

```python
def even_generator(max):
    n = 2
    
    while n <= max:
        yield n
        n += 2

numbers = even_generator(4)

print(next(numbers))
print(next(numbers))
print(next(numbers))
```

**Output**

```
2
4
Traceback (most recent call last):
File "<string>", line 12, in <module>
StopIteration
```

In this case, our generator could generate even numbers only till `4`. So, using `next()` function for the third time raised a `StopIteration` exception.

Notice how we have never explicitly defined the `__iter__()` method, `__next__()` method, or raised a `StopIteration` exception. They are handled implicitly by generators making our program much simpler and easier to understand.

---

## Infinite Stream of Data with Generators

Iterators and generators are generally used to handle a large stream of data--theoretically even an infinite stream of data. These large streams of data cannot be stored in memory at once. To handle this, we can use generators to handle only one item at a time. 

Now, let's build a generator to produce an infinite stream of fibonacci numbers. The fibonacci series is a series where the next element is the sum of the last two elements.

```
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233,.....
```

```python
def generate_fibonacci():
    n1 = 0
    yield n1
    
    n2 = 1
    yield n2
    
    while True:
        n1, n2 = n2, n1 + n2
        yield n2
        
seq = generate_fibonacci()

print(next(seq))
print(next(seq))
print(next(seq))
print(next(seq))
print(next(seq))
```

**Output**
```
0
1
1
2
3
```
If we had used a for loop and a list to store this infinite series, we would have run out of memory.

However, with generators, we can keep accessing these items for as long as we want. It is because we are just dealing with one item at a time.

---

## Programming Task

Create a generator function to generate an infinite stream of odd numbers and print the first 10 elements.

```python
def generate_odd():
    n = 1
    while True:
        yield n
        n += 2

odd_generator = generate_odd()

for num in range(10):
    print(next(odd_generator))
```

**Output**
```
1
3
5
7
9
11
13
15
17
19
```