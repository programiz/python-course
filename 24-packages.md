# Python Packages

**Video link:** [https://youtu.be/TIt2EOuC-Bo](https://youtu.be/TIt2EOuC-Bo)

 In this video, we learned about Python packages with the help of examples. We also learned about pip, the standard package manager of Python.

**Programs in the Video**

- [Python Packages](#python-packages-1)
- [Python `pip`](#python-pip)

---

## Python Packages
A package is a directory containing multiple modules and other sub-packages.

Suppose we are developing a game with multiple objects, so it may have these different modules.
- `player.py`
- `boss.py`
- `gun.py`
- `knife.py`

Since these modules are in the same location, they look cluttered. We can structure them in this way:

- `game`
    - `characters`
        - `player.py`
        - `boss.py`
    - `weapons`
        - `gun.py`
        - `knife.py`

Here, the similar `player` and `boss` modules are kept under the `characters` package. Also, `gun` and `knife` modules are kept inside the `weapons` package.

Then, both characters and weapons packages are kept inside the main `game` package.

As you can see, our project looks much more organized and structured with the use of packages.

Let's implement this in code.

1. Create a directory named `game` that will contain all our game components.
2. We also need to create an `__init__.py` file inside `game` directory. This special file tells Python that this directory is a Python package.
3. Also create the `characters` package with an `__init__.py` file.
4. Now, create `player.py` and `boss.py` modules inside `characters` package.

In `player.py`:

```python
def get_player_info():
    print("I am the main player.")
```

In `boss.py`:

```python
def get_boss_info():
    print("I am the enemy player.")
```

While developing large programs, these modules might contain classes and multiple functions.

Let's create a `main.py` file outside `game` package.

I can now import and use them in the following ways:

```python
import game.characters.player
game.character.player.get_player_info()
```

**Output**
```
I am the main player.
```

---

```python
from game.characters import player
player.get_player_info()
```

**Output**
```
I am the main player.
```

---

```python
from game.characters.boss import get_boss_info
get_boss_info()
```

**Output**
```
I am the enemy player.
```

>**Note**: When you use packages, always try to give descriptive names to functions and classes so that you don't get confused.

---

#### Using `__init__.py`
The code inside `__init__.py` runs automatically when we import the package.

Let's add a `print` statement in this file inside the game package.

```python
print("Initializing game features")
```

When we run this code:
```python
from game.characters import player
from game.characters.boss import get_boss_info

player.get_player_info()

get_boss_info()
```

We get:

**Output**
```
Initializing game features
I am the main player.
I am the enemy player.
```

---

## Python pip
There are thousands of useful packages tailored for specific tasks that are developed and maintained by the active Python community.

When you start working on more advanced projects, you will have to use these packages at some point rather than building everything from scratch.

For example, if you are working with web development, you will probably use packages like `django` or `flask`.

`pip` is the standard package manager for Python which helps to install and manage additional packages that are not available in the Python standard library. 

#### Installing packages

```console
pip install <package_name>
```

For example, to install the `pandas` package, a popular package for data analysis in Python.

```console
pip install pandas
```

#### Installing Specific version of a package

To install version `2.21.0` of requests package,

```console
pip install requests==2.21.0
```

#### List all packages with pip

```console
pip list
```

#### Remove Packages with pip

```console
pip uninstall numpy
```

This uninstalls the `numpy` package from our machine.