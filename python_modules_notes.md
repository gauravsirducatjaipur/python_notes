# Python Notes — Modules

# 1. Module

## What?

A **module** is a Python file (`.py`) that contains reusable code such as:

- Variables
- Functions
- Classes
- Statements

Example:

```text
math_utils.py
```

```python
def add(a, b):
    return a + b

def square(n):
    return n * n
```

Another Python file can import and reuse this code.

---

## Why?

Modules are used to:

- Reuse code
- Organize large programs
- Avoid writing the same code repeatedly
- Separate related functionality
- Make programs easier to maintain
- Create reusable libraries

Instead of putting everything in one file:

```text
app.py
```

we can organize code:

```text
project/
│
├── main.py
├── calculator.py
├── user.py
└── database.py
```

---

## When?

Use modules when:

- A program becomes large.
- Related functions should be grouped together.
- Code needs to be reused in multiple files.
- You want to separate different responsibilities.
- You want to use Python's built-in or third-party libraries.

---

## How?

Create a `.py` file and import it.

Example:

```text
calculator.py
main.py
```

`calculator.py`:

```python
def add(a, b):
    return a + b
```

`main.py`:

```python
import calculator

result = calculator.add(10, 20)

print(result)
```

Output:

```text
30
```

---

# 2. Types of Python Modules

Python modules can broadly be divided into:

```text
Python Modules
│
├── Built-in / Standard Library Modules
├── User-defined Modules
└── Third-party Modules
```

Examples:

```text
Built-in / Standard Library:
math
random
datetime
os
sys
json

User-defined:
calculator.py
student.py
employee.py

Third-party:
numpy
pandas
requests
matplotlib
```

---

# 3. User-defined Module

## What?

A module created by the programmer is called a **user-defined module**.

Example:

### `calculator.py`

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b
```

### `main.py`

```python
import calculator

print(calculator.add(10, 20))
print(calculator.subtract(20, 5))
```

Output:

```text
30
15
```

---

# 4. `import`

## What?

`import` is used to load a module so its code can be used in the current Python file.

### Syntax

```python
import module_name
```

Example:

```python
import math

print(math.sqrt(25))
```

Output:

```text
5.0
```

---

# 5. Accessing Module Members

When a complete module is imported:

```python
import math
```

Access its members using:

```python
module_name.member_name
```

Example:

```python
import math

print(math.pi)
print(math.sqrt(16))
```

Output:

```text
3.141592653589793
4.0
```

The dot `.` is used to access members of a module.

---

# 6. Import Specific Members

Instead of importing the complete module namespace, you can import specific names.

```python
from math import sqrt

print(sqrt(25))
```

Output:

```text
5.0
```

Now you can use:

```python
sqrt(25)
```

instead of:

```python
math.sqrt(25)
```

---

# 7. Import Multiple Members

```python
from math import sqrt, pi

print(sqrt(16))
print(pi)
```

Output:

```text
4.0
3.141592653589793
```

---

# 8. Import Everything Using `*`

You may see:

```python
from math import *
```

Then:

```python
print(sqrt(25))
print(pi)
```

However, this style is generally discouraged in larger programs because it can make it unclear where names came from and can cause naming conflicts.

Prefer:

```python
import math
```

or:

```python
from math import sqrt
```

---

# 9. Module Alias — `as`

## What?

`as` gives a module a shorter or alternative name.

```python
import math as m

print(m.sqrt(25))
```

Output:

```text
5.0
```

Common examples:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
```

---

# 10. Alias for Specific Members

You can also create an alias for an imported member.

```python
from math import sqrt as square_root

print(square_root(36))
```

Output:

```text
6.0
```

---

# 11. Standard Library Modules

Python comes with a large **standard library**.

Common modules include:

```text
math
random
datetime
os
sys
json
re
statistics
pathlib
collections
```

These modules do not normally require a separate `pip install`.

---

# 12. `math` Module

The `math` module provides mathematical functions and constants.

```python
import math

print(math.sqrt(25))
print(math.ceil(4.2))
print(math.floor(4.8))
print(math.pi)
```

Output:

```text
5.0
5
4
3.141592653589793
```

Common functions:

```text
sqrt()
ceil()
floor()
pow()
factorial()
```

Common constants:

```text
pi
e
```

---

# 13. `random` Module

The `random` module generates pseudo-random values.

```python
import random

print(random.randint(1, 10))
```

The result will be a random integer between `1` and `10`, inclusive.

Choose a random item:

```python
colors = ["red", "green", "blue"]

print(random.choice(colors))
```

---

# 14. `datetime` Module

Used for dates and times.

```python
from datetime import datetime

now = datetime.now()

print(now)
```

Example formatted output:

```text
2026-09-21 12:30:15.123456
```

Get date:

```python
print(now.date())
```

Get time:

```python
print(now.time())
```

---

# 15. `os` Module

The `os` module provides operating-system-related functionality.

```python
import os

print(os.getcwd())
```

This returns the current working directory.

List files:

```python
print(os.listdir())
```

Create a directory:

```python
os.mkdir("demo")
```

> Always be careful when using file-system operations such as deleting or moving files.

---

# 16. `sys` Module

The `sys` module provides access to Python runtime/system-related information.

```python
import sys

print(sys.version)
```

Command-line arguments:

```python
print(sys.argv)
```

Exit:

```python
sys.exit()
```

---

# 17. `json` Module

The `json` module is used to work with JSON data.

Convert Python dictionary to JSON string:

```python
import json

student = {
    "name": "Gaurav",
    "age": 40
}

json_data = json.dumps(student)

print(json_data)
```

Output:

```text
{"name": "Gaurav", "age": 40}
```

Convert JSON string to Python object:

```python
data = json.loads(json_data)

print(data["name"])
```

Output:

```text
Gaurav
```

---

# 18. `statistics` Module

The `statistics` module provides common statistical functions.

```python
import statistics

marks = [80, 90, 70, 85, 95]

print(statistics.mean(marks))
print(statistics.median(marks))
```

---

# 19. Third-party Modules

Third-party modules are developed outside Python's standard library.

Examples:

```text
NumPy
Pandas
Requests
Matplotlib
Seaborn
Django
Flask
```

They are commonly installed using `pip`.

Example:

```bash
pip install pandas
```

Then:

```python
import pandas as pd
```

---

# 20. `pip`

## What?

`pip` is Python's package installer.

It is commonly used to install third-party packages.

Example:

```bash
pip install requests
```

Install a specific package version:

```bash
pip install requests==2.32.3
```

Upgrade:

```bash
pip install --upgrade requests
```

List installed packages:

```bash
pip list
```

Show package information:

```bash
pip show requests
```

---

# 21. Module vs Package

## Module

A module is usually a single `.py` file.

```text
calculator.py
```

## Package

A package is a directory used to organize related Python modules.

Example:

```text
myapp/
│
├── __init__.py
├── calculator.py
├── user.py
└── product.py
```

Conceptually:

```text
Module  → Python file
Package → Collection/organization of modules
```

Modern Python can also use namespace packages without requiring `__init__.py` in every package directory, but traditional packages commonly include it.

---

# 22. Creating a Package

Example project:

```text
myapp/
│
├── main.py
│
└── utils/
    ├── __init__.py
    ├── calculator.py
    └── string_utils.py
```

`calculator.py`:

```python
def add(a, b):
    return a + b
```

`main.py`:

```python
from utils.calculator import add

print(add(10, 20))
```

Output:

```text
30
```

---

# 23. Import from a Package

You can import a module from a package.

```python
from utils import calculator

print(calculator.add(10, 20))
```

Or import a specific function:

```python
from utils.calculator import add

print(add(10, 20))
```

---

# 24. `__name__`

Every Python module has a special variable:

```python
__name__
```

If a file is run directly:

```python
print(__name__)
```

Output:

```text
__main__
```

If the file is imported as a module, `__name__` usually contains the module's name.

---

# 25. `if __name__ == "__main__"`

This is commonly used to control code that should run only when the file is executed directly.

### `calculator.py`

```python
def add(a, b):
    return a + b

if __name__ == "__main__":
    print(add(10, 20))
```

If you run:

```bash
python calculator.py
```

Output:

```text
30
```

If another file imports:

```python
import calculator
```

the `add()` function becomes available, but the code inside:

```python
if __name__ == "__main__":
```

does not execute as the main program.

---

# 26. Why Use `if __name__ == "__main__"`?

It helps a file work in two ways:

```text
1. As a reusable module
2. As a directly executable program
```

This is a common Python pattern.

---

# 27. Module Search Path

When Python imports a module, it searches locations listed in:

```python
sys.path
```

Example:

```python
import sys

for path in sys.path:
    print(path)
```

These paths help Python find modules and packages.

---

# 28. Import Order

A typical import section can look like:

```python
import os
import sys
import math

import requests
import pandas as pd

from calculator import add
```

A common organization is:

```text
Standard library
       ↓
Third-party packages
       ↓
Local application modules
```

---

# 29. Reloading a Module

Python caches imported modules in the current process.

The `importlib` module provides `reload()` when a module needs to be re-executed during development.

```python
import importlib
import calculator

importlib.reload(calculator)
```

This is mainly useful in interactive development environments.

---

# 30. Module Attributes

A module can contain:

- Variables
- Functions
- Classes
- Imported names
- Special attributes

Example:

```python
# calculator.py

PI = 3.14

def add(a, b):
    return a + b
```

Use:

```python
import calculator

print(calculator.PI)
print(calculator.add(10, 20))
```

Output:

```text
3.14
30
```

---

# 31. `dir()` with Modules

`dir()` can show names available in an object/module.

```python
import math

print(dir(math))
```

It returns a list of names available in the `math` module.

This is useful for exploration.

---

# 32. `help()` with Modules

`help()` displays documentation.

```python
import math

help(math)
```

You can also inspect a specific function:

```python
help(math.sqrt)
```

---

# 33. Importing Multiple Modules

You can import multiple modules.

```python
import math
import random
import datetime
```

Then use:

```python
print(math.sqrt(16))
print(random.randint(1, 10))
print(datetime.datetime.now())
```

---

# 34. Local Module Example

### Folder

```text
project/
│
├── main.py
└── calculator.py
```

### `calculator.py`

```python
def add(a, b):
    return a + b

def multiply(a, b):
    return a * b
```

### `main.py`

```python
import calculator

print(calculator.add(10, 20))
print(calculator.multiply(5, 4))
```

Output:

```text
30
20
```

---

# 35. Practical Project Structure

For a larger Python application:

```text
my_project/
│
├── main.py
│
├── config.py
│
├── database.py
│
├── utils.py
│
├── models/
│   ├── __init__.py
│   ├── user.py
│   └── product.py
│
└── services/
    ├── __init__.py
    ├── user_service.py
    └── product_service.py
```

Each module can focus on a specific responsibility.

---

# 36. Common Import Errors

## `ModuleNotFoundError`

Example:

```python
import abcxyz
```

If Python cannot find the module, you may get:

```text
ModuleNotFoundError
```

Possible reasons:

- Module is not installed.
- Wrong module name.
- Incorrect project path.
- Virtual environment is not active.
- Import path is incorrect.

---

# 37. `ImportError`

`ImportError` can occur when Python finds the module/package but cannot import the requested name.

Example:

```python
from math import abcxyz
```

If that name does not exist in `math`, Python raises an import-related error.

---

# 38. Module Naming Best Practices

Good:

```text
calculator.py
student.py
database.py
string_utils.py
```

Avoid confusing names:

```text
test.py
random.py
math.py
```

especially if they conflict with standard-library modules.

For example, naming your file:

```text
random.py
```

can interfere with:

```python
import random
```

because Python may import your local file instead of the standard-library module.

---

# 39. Common Mistake — Circular Imports

Circular import example:

```text
a.py imports b.py
b.py imports a.py
```

This can cause import problems.

Better project design usually separates shared functionality into another module.

Example:

```text
a.py
b.py
common.py
```

Both `a.py` and `b.py` can import from `common.py`.

---

# 40. Module vs Function

| Feature | Module | Function |
|---|---|---|
| Meaning | Python file containing reusable code | Reusable block of code |
| Created using | `.py` file | `def` |
| Contains | Functions, classes, variables, etc. | Statements |
| Import | Yes | Usually imported from a module |
| Example | `calculator.py` | `add()` |

---

# 41. Module vs Package

| Feature | Module | Package |
|---|---|---|
| Basic structure | `.py` file | Directory |
| Purpose | Group related code in one file | Organize multiple modules |
| Example | `calculator.py` | `utils/` |
| Can contain modules | No | Yes |

---

# 42. Standard Library vs Third-party Module

| Type | Meaning | Example |
|---|---|---|
| Standard Library | Comes with Python | `math`, `os`, `json` |
| Third-party | Installed separately | `pandas`, `requests` |
| User-defined | Created by programmer | `calculator.py` |

---

# 43. Real-Life Example — Calculator Module

### `calculator.py`

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def multiply(a, b):
    return a * b

def divide(a, b):
    return a / b
```

### `main.py`

```python
import calculator

print("Addition:", calculator.add(10, 5))
print("Subtraction:", calculator.subtract(10, 5))
print("Multiplication:", calculator.multiply(10, 5))
print("Division:", calculator.divide(10, 5))
```

Output:

```text
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2.0
```

---

# 44. Real-Life Example — Student Module

### `student.py`

```python
def calculate_average(marks):
    return sum(marks) / len(marks)

def is_pass(marks):
    return calculate_average(marks) >= 40
```

### `main.py`

```python
import student

marks = [80, 70, 90]

print(student.calculate_average(marks))
print(student.is_pass(marks))
```

Output:

```text
80.0
True
```

---

# 45. Module Workflow

```text
Create .py File
      ↓
Write Reusable Code
      ↓
Save Module
      ↓
Import Module
      ↓
Access Members
      ↓
Reuse Code
```

For third-party packages:

```text
Find Package
      ↓
pip install
      ↓
Import
      ↓
Use Package
```

---

# 46. Quick Revision

| Concept | Meaning |
|---|---|
| Module | Python file containing reusable code |
| `import` | Import a module |
| `from ... import` | Import specific members |
| `as` | Create an alias |
| Standard Library | Modules included with Python |
| User-defined Module | Module created by programmer |
| Third-party Module | Package installed separately |
| `pip` | Python package installer |
| Package | Organization of related modules |
| `__name__` | Special module variable |
| `__main__` | Indicates direct execution context |
| `if __name__ == "__main__"` | Runs code only when file is executed directly |
| `sys.path` | Module search locations |
| `dir()` | Lists available names |
| `help()` | Shows documentation |
| `importlib.reload()` | Reloads an already imported module |

---

# 47. Key Points

- A module is normally a `.py` file containing reusable Python code.
- Modules improve code organization and reuse.
- Use `import` to load a module.
- Use `from module import name` to import a specific member.
- Use `as` to create an alias.
- Python provides a large standard library.
- Third-party packages are commonly installed using `pip`.
- A package organizes related modules.
- Dictionaries, lists, functions, and classes can all exist inside modules.
- `__name__` identifies the module's execution context.
- `if __name__ == "__main__"` is used for direct-execution code.
- `sys.path` contains locations where Python searches for modules.
- `dir()` helps inspect module members.
- `help()` provides documentation.
- Avoid naming local files after important standard-library modules.
- Keep modules focused on related responsibilities.

# One-Line Definitions

> **Module = A Python file containing reusable code such as functions, classes, and variables.**

> **Package = A directory used to organize related Python modules.**

> **Library = A collection of reusable code/modules/packages that provides functionality for programs.**
