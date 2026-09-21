# Python File Handling Notes

## WWH Model: What → Why → When → How

---

# 1. File Handling

## What is File Handling?

File Handling means **creating, opening, reading, writing, updating, and deleting files** using Python.

Python provides the built-in `open()` function to work with files.

### Example

```python
file = open("data.txt", "r")
data = file.read()
print(data)
file.close()
```

---

## Why use File Handling?

File handling is used when data needs to be stored permanently.

Examples:

- Store student records
- Store employee information
- Save application logs
- Read configuration files
- Generate reports
- Store user data
- Read CSV/text files
- Maintain application data

---

## When should we use File Handling?

Use file handling when data must remain available after the Python program stops.

### Memory vs File

```text
Variable
   ↓
Temporary data
   ↓
Program ends → Data normally lost
```

```text
File
   ↓
Permanent storage
   ↓
Program ends → Data remains
```

---

# 2. File Handling Workflow

A common file-handling workflow is:

```text
Open File
    ↓
Read / Write / Append
    ↓
Process Data
    ↓
Close File
```

With `with`:

```text
with open()
    ↓
Read / Write
    ↓
Automatic close
```

---

# 3. open() Function

## What?

`open()` is used to open a file.

## Syntax

```python
open(filename, mode)
```

### Example

```python
file = open("data.txt", "r")
```

Here:

- `"data.txt"` → file name
- `"r"` → reading mode

---

# 4. File Modes

| Mode | Meaning |
|---|---|
| `r` | Read |
| `w` | Write |
| `a` | Append |
| `x` | Create |
| `b` | Binary |
| `t` | Text |
| `r+` | Read + Write |
| `w+` | Write + Read |
| `a+` | Append + Read |

---

# 5. Read Mode - `r`

## What?

`r` opens an existing file for reading.

## Example

```python
file = open("data.txt", "r")

data = file.read()

print(data)

file.close()
```

### Important

If the file does not exist:

```text
FileNotFoundError
```

---

# 6. Reading Complete File using read()

## What?

`read()` reads the complete file content.

## Example

Suppose `data.txt` contains:

```text
Hello Python
Welcome to File Handling
```

Python:

```python
file = open("data.txt", "r")

data = file.read()

print(data)

file.close()
```

Output:

```text
Hello Python
Welcome to File Handling
```

---

# 7. read(size)

## What?

`read(size)` reads a specific number of characters.

## Example

```python
file = open("data.txt", "r")

data = file.read(5)

print(data)

file.close()
```

If file contains:

```text
Python Programming
```

Output:

```text
Pytho
```

---

# 8. readline()

## What?

`readline()` reads one line at a time.

## Example

```python
file = open("data.txt", "r")

line = file.readline()

print(line)

file.close()
```

If file contains:

```text
Python
Java
JavaScript
```

Output:

```text
Python
```

---

# 9. Multiple readline()

```python
file = open("data.txt", "r")

print(file.readline())
print(file.readline())
print(file.readline())

file.close()
```

Output:

```text
Python
Java
JavaScript
```

---

# 10. readlines()

## What?

`readlines()` reads all lines and returns them as a **list**.

## Example

```python
file = open("data.txt", "r")

lines = file.readlines()

print(lines)

file.close()
```

Output:

```python
['Python\n', 'Java\n', 'JavaScript\n']
```

---

# 11. read() vs readline() vs readlines()

| Function | Returns |
|---|---|
| `read()` | Complete content as string |
| `read(n)` | `n` characters |
| `readline()` | One line |
| `readlines()` | List of lines |

---

# 12. Loop Through File

Instead of loading all lines at once, we can iterate through the file.

```python
file = open("data.txt", "r")

for line in file:
    print(line)

file.close()
```

### Better for large text files

```python
for line in open("data.txt", "r"):
    print(line)
```

However, using `with open()` is preferred because it manages the file resource automatically.

---

# 13. Write Mode - `w`

## What?

`w` opens a file for writing.

If the file does not exist, Python creates it.

If the file already exists, its previous content is **overwritten**.

## Example

```python
file = open("data.txt", "w")

file.write("Hello Python")

file.close()
```

File content:

```text
Hello Python
```

---

# 14. Important: `w` Overwrites Data

Suppose `data.txt` contains:

```text
Hello
Python
```

Now:

```python
file = open("data.txt", "w")

file.write("Java")

file.close()
```

New content:

```text
Java
```

The old content is removed.

---

# 15. Writing Multiple Lines

## Using `write()`

```python
file = open("data.txt", "w")

file.write("Python\n")
file.write("Java\n")
file.write("JavaScript\n")

file.close()
```

File:

```text
Python
Java
JavaScript
```

---

# 16. writelines()

## What?

`writelines()` writes multiple strings to a file.

## Example

```python
lines = [
    "Python\n",
    "Java\n",
    "JavaScript\n"
]

file = open("data.txt", "w")

file.writelines(lines)

file.close()
```

### Important

`writelines()` does **not automatically add `\n`**.

Correct:

```python
file.writelines([
    "Python\n",
    "Java\n",
    "JavaScript\n"
])
```

---

# 17. Append Mode - `a`

## What?

`a` adds new content to the end of an existing file.

It does not remove existing content.

## Example

Existing file:

```text
Python
```

Code:

```python
file = open("data.txt", "a")

file.write("\nJava")

file.close()
```

New content:

```text
Python
Java
```

---

# 18. Write vs Append

| Mode | Existing content |
|---|---|
| `w` | Overwrites |
| `a` | Preserves and adds at end |

### Remember

```text
w → Write / Replace
a → Append / Add
```

---

# 19. Create Mode - `x`

## What?

`x` creates a new file.

If the file already exists, Python raises:

```text
FileExistsError
```

## Example

```python
file = open("newfile.txt", "x")

file.write("New file")

file.close()
```

---

# 20. Closing a File

## What?

`close()` closes the opened file.

## Example

```python
file = open("data.txt", "r")

data = file.read()

print(data)

file.close()
```

## Why close?

Closing a file:

- Releases system resources
- Ensures data is properly written
- Prevents unnecessary file locks
- Is good resource-management practice

---

# 21. `with open()` - Recommended Approach

## What?

`with open()` automatically closes the file after the block finishes.

## Syntax

```python
with open("data.txt", "r") as file:
    data = file.read()
```

## Example

```python
with open("data.txt", "r") as file:
    data = file.read()

print(data)
```

No explicit:

```python
file.close()
```

is required.

---

# 22. Why use `with open()`?

It is recommended because the file is automatically closed, including when an exception occurs inside the block.

### Example

```python
with open("data.txt", "r") as file:
    data = file.read()
    print(data)
```

After the block:

```text
File automatically closed
```

---

# 23. Checking File Closed

```python
file = open("data.txt", "r")

print(file.closed)

file.close()

print(file.closed)
```

Output:

```text
False
True
```

With `with`:

```python
with open("data.txt", "r") as file:
    print(file.closed)

print(file.closed)
```

Output:

```text
False
True
```

---

# 24. File Object

When we write:

```python
file = open("data.txt", "r")
```

`file` is a **file object**.

We can use file-object methods such as:

```python
file.read()
file.readline()
file.readlines()
file.write()
file.writelines()
file.seek()
file.tell()
file.close()
```

---

# 25. File Pointer

## What?

Python maintains a current position called the **file pointer**.

### Example

```python
file = open("data.txt", "r")

print(file.read(5))
print(file.read(5))

file.close()
```

If file contains:

```text
PythonProgramming
```

The first `read(5)` reads:

```text
Pytho
```

The next `read(5)` continues from the current position:

```text
nProg
```

---

# 26. tell()

## What?

`tell()` returns the current file pointer position.

## Example

```python
with open("data.txt", "r") as file:

    print(file.tell())

    file.read(5)

    print(file.tell())
```

Output for a normal ASCII text file:

```text
0
5
```

---

# 27. seek()

## What?

`seek()` moves the file pointer to a specific position.

## Syntax

```python
file.seek(position)
```

## Example

```python
with open("data.txt", "r") as file:

    print(file.read(5))

    file.seek(0)

    print(file.read(5))
```

Output:

```text
Pytho
Pytho
```

---

# 28. File Paths

A file can be referenced using:

### Relative path

```python
open("data.txt", "r")
```

### Folder path

```python
open("data/data.txt", "r")
```

### Windows absolute path

Use a raw string:

```python
open(r"C:\Users\Gaurav\data.txt", "r")
```

Or escaped backslashes:

```python
open("C:\\Users\\Gaurav\\data.txt", "r")
```

---

# 29. Encoding

Text files use character encoding.

A common choice is UTF-8.

## Example

```python
with open("data.txt", "r", encoding="utf-8") as file:
    data = file.read()
    print(data)
```

When writing:

```python
with open("data.txt", "w", encoding="utf-8") as file:
    file.write("Hello Python")
```

Using explicit encoding is useful when working with multilingual text.

---

# 30. File Handling with Exception Handling

## What?

File operations can generate exceptions.

## Example

```python
try:
    with open("data.txt", "r") as file:
        data = file.read()
        print(data)

except FileNotFoundError:
    print("File not found")
```

---

# 31. FileNotFoundError

```python
try:
    with open("abc.txt", "r") as file:
        print(file.read())

except FileNotFoundError:
    print("abc.txt does not exist")
```

Output:

```text
abc.txt does not exist
```

---

# 32. PermissionError

```python
try:
    with open("data.txt", "r") as file:
        print(file.read())

except PermissionError:
    print("Permission denied")
```

This can occur when the operating system does not allow the requested file operation.

---

# 33. OSError

Many operating-system-level file problems are represented by `OSError` or one of its subclasses.

```python
try:
    with open("data.txt", "r") as file:
        print(file.read())

except OSError as e:
    print("File operation failed:", e)
```

---

# 34. Text Files

Text mode is the default.

```python
with open("data.txt", "r", encoding="utf-8") as file:
    data = file.read()
```

Common text files:

- `.txt`
- `.csv`
- `.html`
- `.css`
- `.js`
- `.py`
- `.json`

---

# 35. Binary Files

## What?

Binary files contain data that should be handled as bytes rather than normal text.

Examples:

- Images
- Audio
- Video
- PDF
- ZIP files

Use `b` mode.

## Example

```python
with open("image.jpg", "rb") as file:
    data = file.read()
```

---

# 36. Binary Write

```python
with open("copy.jpg", "wb") as file:
    file.write(data)
```

### Common binary modes

| Mode | Meaning |
|---|---|
| `rb` | Read binary |
| `wb` | Write binary |
| `ab` | Append binary |

---

# 37. Copy an Image

```python
with open("source.jpg", "rb") as source:
    data = source.read()

with open("copy.jpg", "wb") as destination:
    destination.write(data)
```

This copies the binary content.

---

# 38. File Properties

Useful file-object attributes include:

```python
with open("data.txt", "r", encoding="utf-8") as file:
    print(file.name)
    print(file.mode)
    print(file.closed)
```

Example output:

```text
data.txt
r
False
```

After leaving the `with` block, the file is closed.

---

# 39. Reading a File Line by Line

```python
with open("students.txt", "r", encoding="utf-8") as file:

    for line in file:
        print(line.strip())
```

`strip()` removes surrounding whitespace such as the newline at the end.

---

# 40. Write Student Data

```python
students = [
    "Rahul,20\n",
    "Aman,21\n",
    "Priya,22\n"
]

with open("students.txt", "w", encoding="utf-8") as file:
    file.writelines(students)
```

File:

```text
Rahul,20
Aman,21
Priya,22
```

---

# 41. Append Student Data

```python
with open("students.txt", "a", encoding="utf-8") as file:
    file.write("Neha,23\n")
```

New file:

```text
Rahul,20
Aman,21
Priya,22
Neha,23
```

---

# 42. Read and Process Student Data

```python
with open("students.txt", "r", encoding="utf-8") as file:

    for line in file:

        name, age = line.strip().split(",")

        print("Name:", name)
        print("Age:", age)
```

Output:

```text
Name: Rahul
Age: 20
Name: Aman
Age: 21
Name: Priya
Age: 22
```

---

# 43. Read + Write Mode `r+`

## What?

`r+` allows both reading and writing.

The file must already exist.

```python
with open("data.txt", "r+", encoding="utf-8") as file:

    data = file.read()

    print(data)

    file.write("\nNew data")
```

---

# 44. Write + Read Mode `w+`

## What?

`w+` allows writing and reading.

Important: opening an existing file with `w+` **truncates/clears its existing content**.

```python
with open("data.txt", "w+", encoding="utf-8") as file:

    file.write("Hello Python")

    file.seek(0)

    print(file.read())
```

Output:

```text
Hello Python
```

---

# 45. Append + Read Mode `a+`

## What?

`a+` allows appending and reading.

The file pointer is positioned at the end for writing.

```python
with open("data.txt", "a+", encoding="utf-8") as file:

    file.write("\nNew line")

    file.seek(0)

    print(file.read())
```

---

# 46. File Modes Quick Table

| Mode | Read | Write | Creates if missing | Truncates existing |
|---|---:|---:|---:|---:|
| `r` | Yes | No | No | No |
| `w` | No | Yes | Yes | Yes |
| `a` | No | Yes | Yes | No |
| `x` | No | Yes | Yes | Error if exists |
| `r+` | Yes | Yes | No | No |
| `w+` | Yes | Yes | Yes | Yes |
| `a+` | Yes | Yes | Yes | No |

---

# 47. Newline Character `\n`

`\n` represents a new line.

```python
with open("data.txt", "w") as file:
    file.write("Python\n")
    file.write("Java\n")
    file.write("JavaScript\n")
```

File:

```text
Python
Java
JavaScript
```

---

# 48. Carriage Return and Newline

For normal Python text-file work, prefer:

```python
"\n"
```

Python's text mode handles platform-specific newline translation.

---

# 49. File Handling with `input()`

```python
name = input("Enter your name: ")

with open("user.txt", "w", encoding="utf-8") as file:
    file.write(name)
```

If user enters:

```text
Gaurav
```

`user.txt` contains:

```text
Gaurav
```

---

# 50. File Handling with Functions

```python
def save_data(data):

    with open("data.txt", "w", encoding="utf-8") as file:
        file.write(data)


def read_data():

    with open("data.txt", "r", encoding="utf-8") as file:
        return file.read()


save_data("Hello Python")

print(read_data())
```

Output:

```text
Hello Python
```

---

# 51. File Handling with List

```python
numbers = [10, 20, 30, 40, 50]

with open("numbers.txt", "w", encoding="utf-8") as file:

    for number in numbers:
        file.write(str(number) + "\n")
```

File:

```text
10
20
30
40
50
```

---

# 52. Reading Numbers from File

```python
numbers = []

with open("numbers.txt", "r", encoding="utf-8") as file:

    for line in file:
        numbers.append(int(line.strip()))

print(numbers)
```

Output:

```python
[10, 20, 30, 40, 50]
```

---

# 53. File Handling and JSON

For structured application data, JSON is often more suitable than manually formatting text.

```python
import json

student = {
    "name": "Rahul",
    "age": 20,
    "course": "MERN"
}

with open("student.json", "w", encoding="utf-8") as file:
    json.dump(student, file, indent=4)
```

Read:

```python
with open("student.json", "r", encoding="utf-8") as file:
    data = json.load(file)

print(data)
```

Output:

```python
{'name': 'Rahul', 'age': 20, 'course': 'MERN'}
```

---

# 54. Delete a File

## What?

Python can delete files using the `os` module.

```python
import os

os.remove("data.txt")
```

### Safer version

```python
import os

if os.path.exists("data.txt"):
    os.remove("data.txt")
else:
    print("File does not exist")
```

---

# 55. Rename a File

```python
import os

os.rename("old.txt", "new.txt")
```

---

# 56. Check Whether File Exists

```python
import os

if os.path.exists("data.txt"):
    print("File exists")
else:
    print("File does not exist")
```

---

# 57. Create a Folder

Use `os.mkdir()`:

```python
import os

os.mkdir("students")
```

If the folder already exists, an exception can occur.

A convenient alternative is:

```python
os.makedirs("students", exist_ok=True)
```

---

# 58. Get Current Working Directory

```python
import os

print(os.getcwd())
```

This returns the directory from which the Python process is currently working.

---

# 59. List Files and Folders

```python
import os

print(os.listdir())
```

To list a particular folder:

```python
print(os.listdir("students"))
```

---

# 60. File Handling + Exception Handling

A practical pattern:

```python
try:

    with open("data.txt", "r", encoding="utf-8") as file:
        data = file.read()

except FileNotFoundError:
    print("File not found")

except PermissionError:
    print("Permission denied")

else:
    print(data)

finally:
    print("File operation completed")
```

---

# 61. Common Mistakes

## Mistake 1: Forgetting to close a manually opened file

```python
file = open("data.txt", "r")
data = file.read()
```

Better:

```python
with open("data.txt", "r") as file:
    data = file.read()
```

---

## Mistake 2: Using `w` when you wanted to append

```python
open("data.txt", "w")
```

This can overwrite existing content.

Use:

```python
open("data.txt", "a")
```

when you want to add content.

---

## Mistake 3: Reading a non-existing file

```python
open("abc.txt", "r")
```

Can raise:

```text
FileNotFoundError
```

---

## Mistake 4: Forgetting `\n`

```python
file.write("Python")
file.write("Java")
```

Result:

```text
PythonJava
```

Use:

```python
file.write("Python\n")
file.write("Java\n")
```

---

## Mistake 5: Expecting `writelines()` to add newlines

```python
file.writelines(["Python", "Java", "C++"])
```

This writes them together.

Use:

```python
file.writelines(["Python\n", "Java\n", "C++\n"])
```

---

## Mistake 6: Forgetting `seek()` before rereading

```python
with open("data.txt", "r+") as file:
    file.read()
    print(file.read())
```

The second `read()` starts from the current pointer.

Use:

```python
file.seek(0)
```

when you need to return to the beginning.

---

# 62. `flush()`

## What?

`flush()` asks Python to push buffered written data to the underlying file stream.

```python
with open("data.txt", "w", encoding="utf-8") as file:
    file.write("Hello")
    file.flush()
```

Usually, when using `with`, the file is flushed/closed automatically when the block exits.

---

# 63. File Handling vs Database

| File | Database |
|---|---|
| Simple storage | Structured storage |
| Good for small/simple data | Better for large/relational data |
| Easy to create | Requires database system |
| Limited querying | Powerful querying |
| Manual data management | Better concurrency and transactions |

---

# 64. Real-Life Example: Application Log

```python
from datetime import datetime

message = "User logged in"

with open("app.log", "a", encoding="utf-8") as file:
    file.write(f"{datetime.now()} - {message}\n")
```

Each new event can be appended to the log.

---

# 65. Real-Life Example: Student Record

```python
name = input("Enter student name: ")
marks = input("Enter marks: ")

with open("students.txt", "a", encoding="utf-8") as file:
    file.write(f"{name},{marks}\n")

print("Student saved successfully")
```

---

# 66. Real-Life Example: Simple Notes App

```python
while True:

    print("1. Add Note")
    print("2. View Notes")
    print("3. Exit")

    choice = input("Enter choice: ")

    if choice == "1":

        note = input("Enter note: ")

        with open("notes.txt", "a", encoding="utf-8") as file:
            file.write(note + "\n")

        print("Note saved")

    elif choice == "2":

        try:
            with open("notes.txt", "r", encoding="utf-8") as file:
                print(file.read())

        except FileNotFoundError:
            print("No notes found")

    elif choice == "3":
        break

    else:
        print("Invalid choice")
```

---

# 67. File Handling Cheat Sheet

### Open

```python
file = open("data.txt", "r")
```

### Read

```python
file.read()
```

### Read one line

```python
file.readline()
```

### Read all lines

```python
file.readlines()
```

### Write

```python
file.write("Hello")
```

### Write multiple lines

```python
file.writelines(["A\n", "B\n"])
```

### Append

```python
file = open("data.txt", "a")
```

### Pointer position

```python
file.tell()
```

### Move pointer

```python
file.seek(0)
```

### Close

```python
file.close()
```

### Recommended

```python
with open("data.txt", "r", encoding="utf-8") as file:
    data = file.read()
```

---

# 68. Quick Revision

| Concept | Key Point |
|---|---|
| `open()` | Opens a file |
| `r` | Read |
| `w` | Write/overwrite |
| `a` | Append |
| `x` | Create new file |
| `b` | Binary mode |
| `t` | Text mode |
| `read()` | Reads content |
| `readline()` | Reads one line |
| `readlines()` | Returns list of lines |
| `write()` | Writes string |
| `writelines()` | Writes multiple strings |
| `tell()` | Returns pointer position |
| `seek()` | Moves pointer |
| `close()` | Closes file |
| `with open()` | Automatically manages closing |
| `os.remove()` | Deletes file |
| `os.rename()` | Renames file |
| `os.path.exists()` | Checks existence |

---

# 69. One-Line Definitions

- **File Handling:** Working with files to store and retrieve data.
- **`open()`:** Opens a file and returns a file object.
- **`read()`:** Reads file content.
- **`readline()`:** Reads one line.
- **`readlines()`:** Reads lines and returns them as a list.
- **`write()`:** Writes a string to a file.
- **`writelines()`:** Writes multiple strings.
- **`close()`:** Closes an opened file.
- **`seek()`:** Moves the file pointer.
- **`tell()`:** Returns the current file pointer position.
- **`with open()`:** Safely manages a file resource and closes it automatically.
- **Text File:** File containing character/text data.
- **Binary File:** File handled as raw bytes.
- **File Mode:** Specifies how a file will be opened and used.

---

# 70. Final Example

```python
import os


filename = "students.txt"

try:

    # Create/write file
    with open(filename, "w", encoding="utf-8") as file:
        file.write("Rahul,20\n")
        file.write("Aman,21\n")

    # Append data
    with open(filename, "a", encoding="utf-8") as file:
        file.write("Priya,22\n")

    # Read data
    with open(filename, "r", encoding="utf-8") as file:
        data = file.read()

    print(data)

    # Check file
    if os.path.exists(filename):
        print("File exists")

except FileNotFoundError:
    print("File not found")

except PermissionError:
    print("Permission denied")

except OSError as e:
    print("File operation failed:", e)

else:
    print("File handling completed successfully")

finally:
    print("Program execution completed")
```

This example combines:

- `open()`
- `w`
- `a`
- `r`
- `write()`
- `read()`
- `with`
- `encoding`
- `os.path.exists()`
- Exception Handling
- `try`
- `except`
- `else`
- `finally`
