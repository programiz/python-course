# Python File Handling

**Video link:** [https://youtu.be/crluPcyuchU](https://youtu.be/crluPcyuchU)

In this video, we learned how to perform various file operations like reading and writing into files with the help examples.

**Programs in the Video**

- [File Operations](#file-operations)
- [Opening a File](#opening-a-file)
- [Reading files in Python](#reading-files-in-python)
- [Exception Handling with Files](#exception-handling-with-files)
- [Writing to files in Python](#writing-to-files-in-python)
- [Appending to files in Python](#appending-to-files-in-python)
- [Python `readlines()` and `writelines()`](#python-readlines-and-writelines)

---

## File Operations
Files are named locations on our storage device for recording data. Python provides numerous builtin functions to work with these files.

There are three steps we need to follow to work with files:

- Open a file
- Perform Operation (Read or Write)
- Close the file

---

## Opening a File

In Python, we use the builtin `open()` function to open files.

Suppose we have a file called `message.txt` with the following content:
```
I love programming.
I love Programiz.
```

We can open it using:

```python
f = open('message.txt')
```

The `open()` function is opening the file which returns a file object that can be used to perform file operations.

By default, the file will be opened in the read mode. We could also have used:

```python
# read mode
f = open('message.txt', 'r')

# write mode
f = open('message.txt', 'w')
```

|Mode|Description|
|---|---|
|`r` (Read Mode)|Opens a file for reading (default)|
|`w` (Write Mode)|Opens a file for writing, Creates a new file if it does not exist, Clears the content of the file if it exists|
|`a` (Append Mode)|Opens a file for appending at the end of the file, Creates a new file if it does not exist|

---

## Reading files in Python

After opening a file, we can read its contents using the `read()` method of the file object.

```python
f = open('message.txt', 'r')

content = f.read()
print(content)

f.close()
```

**Output**
```
I love programming.
I love Programiz.
```

>**Note**: We should always close the file using `close()` method after working with files. It is a good programming practice.

It is also possible to read only a certain number of characters from a file using the `read()` method.
For this, we pass an optional `size` argument. 

Let's read only the first 6 characters:

```python
f = open('message.txt', 'r')

content = f.read(6)
print(content)

f.close()
```

**Output**
```
I love
```

Now if we read the same file again, it starts reading from the 7th character because we have already read upto the 6th character.

```python
f = open('message.txt', 'r')

content = f.read(6)
print(content)

more_content = f.read(12)
print(more_content)

f.close()
```

**Output**
```
I love
 programming
```

---

## Exception Handling with Files

We might encounter unexpected errors while working with external files.
So, it's a good practice to open files using the `try...finally` statement. 

```python
try:
    f = open('message.txt', 'r')

    content = f.read(6)
    print(content)

    more_content = f.read(12)
    print(more_content)
finally:
    f.close()
```

Now, even if our program encounters an error, our file will be closed. It is because the `finally` block always gets executed.

There is even a better way to write this same code in Python using the `with...open` syntax.


```python
with open('message.txt', 'r') as f:
    content = f.read(6)
    print(content)

    more_content = f.read(12)
    print(more_content)
```
>**Note**: It is highly recommended to use this syntax while working with files because we don't need to explicitly call the `close()` method
> and our code becomes much cleaner than before.

---

## Writing to files in Python

To write content to a file, we must first open it in write mode. Then, we can start writing content to it using the `write()` method.

There are two things you need to remember while writing to a file:

- If you try to open a file that doesn't exist, a new file is automatically created.
- If a file already exists, its contents are removed, and our new content is added to it.


```python
with open('python.txt', 'w') as f:
    f.write("Python is awesome")
    f.write("I love Python")
```

A `python.txt` file is created in the same directory with the following content:

```
Python is awesomeI love Python
```

To add a new line, we can use `\n`:

```python
with open('python.txt', 'w') as f:
    f.write("Python is awesome\n")
    f.write("I love Python")
```

The `python.txt` file now has:

```
Python is awesome
I love python
```

Notice that while running this program for the second time, the `python.txt` file was already created.
Since opening an existing file in write mode will overwrite the file, all the previous data was erased and new content was written again.

>**Note**: Be careful while using the write mode because you may accidentally erase the old data without realizing it.

---

## Appending to Files in Python

We use this mode if we want to add additional data to the end of the file without erasing our previous data.

Let's add an additional line to the previous `python.txt` file.

```python
with open('python.txt', 'a') as f:
    f.write("\nPython is my first programming language.")
```

Contents of `python.txt`:

```
Python is awesome
I love Python 
Python is my first programming language.
```

---

## Python `readlines()` and `writelines()`

The `readlines()` method returns a list containing each line of the file.

Let's open the same python.txt file we have been working on in read mode and use `readlines()`:

```python
with open('python.txt', 'r') as f:
    lines = f.readlines()
print(lines)
```

**Output**

```
['Python is awesome\n', 'I love Python\n', 'Python is my first programming language.']
```

Similarly, there is also a `writelines()` method to write multiple items into a file. It writes the items of a list to the file.

```python
with open('javascript.txt', 'w') as f:
    lines = ['JS is also awesome', '\nJS is my second programming language.']
    f.writelines(lines)
```

A new file named `javascript.txt` is created with the following contents:

```
JS is also awesome
JS is my second programming language.
```