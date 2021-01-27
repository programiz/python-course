# Python `os` module

**Video link:** [https://youtu.be/vNP15Wov7sQ](https://youtu.be/vNP15Wov7sQ)

In this video, we learned to use the `os` module to perform various directory operations like creating, renaming, and removing directories with the help of examples. 

**Programs in the Video**

- [Getting Current Directory](#getting-current-directory)
- [Changing Directory](#changing-directory)
- [Listing all Directories and Files](#listing-all-directories-and-files)
- [Making a New Directory](#making-a-new-directory)
- [Renaming a Directory or a File](#renaming-a-directory-or-a-file)
- [Removing Directory or File](#removing-directory-or-file)

---

## Getting Current Directory
We use the `getcwd()` function of the `os` module to get the path to the current directory.

```python
import os

current_dir = os.getcwd()
print(current_dir)
```

When you run the code, the current working directory that is the directory containing our Python file is printed.

---

## Changing Directory

In Python, we can change the current working directory by using the `chdir()` function of the `os` module.

As we saw previously, the present working directory is the directory containing our Python file. Let's change the current working directory

```python
import os

current_dir = os.getcwd()
print(current_dir)

os.chdir("/path/new/location")
print(os.getcwd())
```

**Output**
```
<your file directory location>
<new location>
```

>**Note**: Now if we create a file inside the current directory, our file will be created inside `<new location>`.

```python
import os

current_dir = os.getcwd()
print(current_dir)

os.chdir("<new location>")

with open("test.txt", "w") as f:
    f.write("This is a test file.")
```

We can see the `test.txt` file is created inside the current working directory which is `<new location>`.

---

## Listing all Directories and Files

In Python, all files and sub-directories inside a directory can be retrieved using the `listdir()` function of the `os` module.

For example,

```python
import os

print(os.listdir())
```

This function returns a list containing all files and sub-directories in the current working directory.

We can also pass an optional `path` argument to `listdir()` to return files and sub-directories from a specific path.

```python
import os

print(os.listdir("<path>"))
```

---

## Making a New Directory

We can create a new directory using the `mkdir()` function of the `os` module.

```python
import os

os.mkdir("test")
```

This creates a new `test` directory in our current directory.

---

## Renaming a Directory or a File

We can rename any directory or file using the `os.rename()` function which takes in 2 arguments: `old name` and `new name`.

```python
import os

# rename directory or file
os.rename('<old_name>', '<new_name>')
```

---

## Removing Directory or File
We can remove a file using the `remove()` function of the `os` module.

```python
import os

print(os.listdir())

os.remove("<filename>")

print(os.listdir())
```

After running this code, the file is deleted, so the second `os.listdir()` will not list the file.

---

To remove a directory, we use the `rmdir()` function.

```python
import os

print(os.listdir())

os.rmdir("<path_to_directory>")

print(os.listdir())
```

>**Note**: One thing we need to remember when removing a directory is that the directory must be empty. Otherwise, an exception will be raised.

