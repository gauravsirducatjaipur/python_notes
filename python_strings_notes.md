# Python Notes — Strings

# 1. String

## What?

A **string** is a sequence of characters enclosed inside quotes.

Python supports:

```python
"Hello"
'Hello'
```

Example:

```python
name = "Gaurav"

print(name)
```

Output:

```text
Gaurav
```

A string can contain:

- Letters
- Numbers
- Spaces
- Special characters
- Symbols

Example:

```python
text = "Python 3.14 @ Home!"
```

---

## Why?

Strings are used whenever a program works with text.

Examples:

- Name
- Address
- Email
- Password
- Mobile number
- Message
- Product name
- Website content
- User input

Example:

```python
name = "Gaurav"
email = "gaurav@example.com"
city = "Jaipur"
```

---

## When?

Use a string when the data represents **text**.

Even if a value contains only digits, it can be stored as a string when mathematical operations are not required.

```python
mobile = "9876543210"
```

Here the mobile number is text, not a number for calculation.

---

## How?

Use single, double, or triple quotes.

```python
name = 'Gaurav'
city = "Jaipur"
message = """Welcome to Python"""
```

---

# 2. Creating Strings

## Single Quotes

```python
name = 'Gaurav'
print(name)
```

## Double Quotes

```python
name = "Gaurav"
print(name)
```

## Triple Quotes

Triple quotes are commonly used for multiline strings.

```python
message = """Hello
Welcome to Python
This is a multiline string"""

print(message)
```

Output:

```text
Hello
Welcome to Python
This is a multiline string
```

---

# 3. Single Quotes vs Double Quotes

Both are valid.

```python
name = 'Gaurav'
name = "Gaurav"
```

A useful technique is to use the opposite quote when the text contains an apostrophe.

```python
message = "Gaurav's laptop"
```

or:

```python
message = 'He said "Hello"'
```

---

# 4. String Indexing

## What?

Each character in a string has a position called an **index**.

Python uses **zero-based indexing**.

Example:

```python
name = "Python"
```

Positions:

```text
 P   y   t   h   o   n
 0   1   2   3   4   5
```

Access a character:

```python
print(name[0])
print(name[3])
```

Output:

```text
P
h
```

---

# 5. Negative Indexing

Python also supports negative indexing.

```text
 P   y   t   h   o   n
-6  -5  -4  -3  -2  -1
```

Example:

```python
name = "Python"

print(name[-1])
print(name[-2])
```

Output:

```text
n
o
```

### Remember

```text
Positive index → starts from 0
Negative index → starts from -1
```

---

# 6. String Slicing

## What?

Slicing is used to extract a portion of a string.

### Syntax

```python
string[start:stop]
```

The `stop` index is excluded.

Example:

```python
text = "Python"

print(text[0:3])
```

Output:

```text
Pyt
```

Because indexes `0`, `1`, and `2` are included.

---

# 7. Slicing with Step

### Syntax

```python
string[start:stop:step]
```

Example:

```python
text = "Python"

print(text[0:6:2])
```

Output:

```text
Pto
```

Indexes selected:

```text
0 → P
2 → t
4 → o
```

---

# 8. Common Slicing Techniques

```python
text = "Python"
```

### First 3 Characters

```python
print(text[:3])
```

Output:

```text
Pyt
```

### From Index 2

```python
print(text[2:])
```

Output:

```text
thon
```

### Copy Entire String

```python
print(text[:])
```

Output:

```text
Python
```

### Reverse String

```python
print(text[::-1])
```

Output:

```text
nohtyP
```

---

# 9. String Length — `len()`

## What?

`len()` returns the number of characters in a string.

```python
text = "Python"

print(len(text))
```

Output:

```text
6
```

Spaces are also counted.

```python
text = "Hello World"

print(len(text))
```

Output:

```text
11
```

---

# 10. String Concatenation

## What?

Concatenation means joining strings.

Use the `+` operator.

```python
first = "Gaurav"
last = "Agrawal"

name = first + " " + last

print(name)
```

Output:

```text
Gaurav Agrawal
```

---

# 11. String Repetition

The `*` operator can repeat a string.

```python
text = "Hi "

print(text * 3)
```

Output:

```text
Hi Hi Hi
```

Example:

```python
print("*" * 10)
```

Output:

```text
**********
```

---

# 12. Checking String Membership

Use:

```python
in
not in
```

Example:

```python
text = "Python Programming"

print("Python" in text)
print("Java" in text)
```

Output:

```text
True
False
```

Example:

```python
print("Java" not in text)
```

Output:

```text
True
```

---

# 13. Comparing Strings

Strings can be compared using comparison operators.

```python
a = "apple"
b = "apple"

print(a == b)
```

Output:

```text
True
```

Other operators:

```python
==
!=
<
>
<=
>=
```

Example:

```python
print("apple" == "apple")
print("apple" != "orange")
```

Output:

```text
True
True
```

String comparisons are based on character ordering.

---

# 14. Strings are Immutable

## What?

Python strings are **immutable**.

This means an existing string cannot be changed character-by-character.

Example:

```python
name = "Python"

name[0] = "J"
```

This raises:

```text
TypeError
```

Instead, create a new string:

```python
name = "Python"

name = "J" + name[1:]

print(name)
```

Output:

```text
Jython
```

---

# 15. Changing Case

Python provides several methods for changing letter case.

## `upper()`

```python
text = "python"

print(text.upper())
```

Output:

```text
PYTHON
```

## `lower()`

```python
text = "PYTHON"

print(text.lower())
```

Output:

```text
python
```

## `capitalize()`

```python
text = "python programming"

print(text.capitalize())
```

Output:

```text
Python programming
```

## `title()`

```python
text = "python programming"

print(text.title())
```

Output:

```text
Python Programming
```

## `swapcase()`

```python
text = "PyThOn"

print(text.swapcase())
```

Output:

```text
pYtHoN
```

---

# 16. `casefold()`

`casefold()` is used for aggressive lowercase conversion and is useful for case-insensitive text comparison.

```python
a = "PYTHON"
b = "python"

print(a.casefold() == b.casefold())
```

Output:

```text
True
```

---

# 17. Removing Whitespace

## `strip()`

Removes spaces from both ends.

```python
text = "   Python   "

print(text.strip())
```

Output:

```text
Python
```

## `lstrip()`

Removes whitespace from the left.

```python
text = "   Python"

print(text.lstrip())
```

## `rstrip()`

Removes whitespace from the right.

```python
text = "Python   "

print(text.rstrip())
```

---

# 18. Searching in Strings

## `find()`

Returns the index of the first occurrence.

```python
text = "Python Programming"

print(text.find("Programming"))
```

Output:

```text
7
```

If the substring is not found:

```python
print(text.find("Java"))
```

Output:

```text
-1
```

---

# 19. `index()`

`index()` also searches for a substring.

```python
text = "Python Programming"

print(text.index("Python"))
```

Output:

```text
0
```

Difference:

```text
find()  → returns -1 if not found
index() → raises ValueError if not found
```

---

# 20. Counting Characters — `count()`

```python
text = "banana"

print(text.count("a"))
```

Output:

```text
3
```

Example:

```python
print(text.count("na"))
```

Output:

```text
2
```

---

# 21. Checking Start and End

## `startswith()`

```python
text = "Python Programming"

print(text.startswith("Python"))
```

Output:

```text
True
```

## `endswith()`

```python
print(text.endswith("Programming"))
```

Output:

```text
True
```

---

# 22. Replacing Text — `replace()`

```python
text = "I like Java"

new_text = text.replace("Java", "Python")

print(new_text)
```

Output:

```text
I like Python
```

The original string is not modified because strings are immutable.

---

# 23. Splitting a String — `split()`

## What?

`split()` breaks a string into a list.

```python
text = "Python Java JavaScript"

languages = text.split()

print(languages)
```

Output:

```text
['Python', 'Java', 'JavaScript']
```

Default separator is whitespace.

### Using a Separator

```python
data = "HTML,CSS,JavaScript,React"

print(data.split(","))
```

Output:

```text
['HTML', 'CSS', 'JavaScript', 'React']
```

---

# 24. Joining Strings — `join()`

## What?

`join()` combines multiple strings into one string.

```python
languages = ["Python", "Java", "JavaScript"]

result = ", ".join(languages)

print(result)
```

Output:

```text
Python, Java, JavaScript
```

Another example:

```python
words = ["Python", "is", "easy"]

print(" ".join(words))
```

Output:

```text
Python is easy
```

### Easy Difference

```text
split() → String → List

join()  → List of Strings → String
```

---

# 25. Checking String Content

Python provides useful checking methods.

## `isalpha()`

Checks whether all characters are alphabetic.

```python
print("Python".isalpha())
print("Python123".isalpha())
```

Output:

```text
True
False
```

## `isdigit()`

```python
print("12345".isdigit())
print("123a".isdigit())
```

Output:

```text
True
False
```

## `isalnum()`

Checks whether all characters are letters or numbers.

```python
print("Python123".isalnum())
print("Python 123".isalnum())
```

Output:

```text
True
False
```

Space is not alphanumeric.

## `isspace()`

```python
print("   ".isspace())
print("Python".isspace())
```

Output:

```text
True
False
```

---

# 26. More String Checking Methods

## `islower()`

```python
print("python".islower())
```

Output:

```text
True
```

## `isupper()`

```python
print("PYTHON".isupper())
```

Output:

```text
True
```

## `istitle()`

```python
print("Python Programming".istitle())
```

Output:

```text
True
```

---

# 27. Escape Characters

Escape characters are used to represent special characters inside strings.

## New Line — `\n`

```python
print("Hello\nPython")
```

Output:

```text
Hello
Python
```

## Tab — `\t`

```python
print("Name\tAge")
```

Output:

```text
Name    Age
```

## Backslash — `\\`

```python
print("C:\\Users\\Gaurav")
```

Output:

```text
C:\Users\Gaurav
```

## Single Quote — `\'`

```python
print('Gaurav\'s Laptop')
```

Output:

```text
Gaurav's Laptop
```

## Double Quote — `\"`

```python
print("He said \"Hello\"")
```

Output:

```text
He said "Hello"
```

---

# 28. Raw Strings

## What?

A raw string treats backslashes mostly as normal characters.

Use the `r` prefix.

```python
path = r"C:\Users\Gaurav\Documents"

print(path)
```

Output:

```text
C:\Users\Gaurav\Documents
```

Raw strings are especially useful for Windows paths and regular expressions.

---

# 29. String Formatting

String formatting is used to insert values into strings.

There are several approaches.

---

# 30. String Concatenation Formatting

```python
name = "Gaurav"
age = 40

message = "My name is " + name + " and my age is " + str(age)

print(message)
```

Output:

```text
My name is Gaurav and my age is 40
```

The `str()` conversion is needed because `age` is an integer.

---

# 31. `format()` Method

```python
name = "Gaurav"
age = 40

message = "My name is {} and my age is {}".format(name, age)

print(message)
```

Output:

```text
My name is Gaurav and my age is 40
```

Using indexes:

```python
message = "Name: {0}, Age: {1}".format(name, age)

print(message)
```

---

# 32. F-Strings

## What?

An f-string allows expressions and variables to be inserted directly into a string.

Put `f` before the string.

```python
name = "Gaurav"
age = 40

message = f"My name is {name} and my age is {age}"

print(message)
```

Output:

```text
My name is Gaurav and my age is 40
```

F-strings are commonly used because they are concise and readable.

---

# 33. Expressions Inside F-Strings

```python
a = 10
b = 20

print(f"Sum = {a + b}")
```

Output:

```text
Sum = 30
```

You can use expressions inside `{}`.

---

# 34. Formatting Numbers with F-Strings

```python
price = 1250.5678

print(f"Price: {price:.2f}")
```

Output:

```text
Price: 1250.57
```

`.2f` means two digits after the decimal point.

---

# 35. Multiline Strings

Triple quotes can create multiline strings.

```python
message = """
Welcome to Python.
Learn Strings.
Practice every day.
"""

print(message)
```

Triple-quoted strings can also be used for documentation.

---

# 36. Iterating Through a String

A string can be traversed using a loop.

```python
text = "Python"

for char in text:
    print(char)
```

Output:

```text
P
y
t
h
o
n
```

---

# 37. String with `for` Loop

Example: count characters.

```python
text = "Python"
count = 0

for char in text:
    count += 1

print(count)
```

Output:

```text
6
```

In real programs, `len(text)` is simpler for getting the length.

---

# 38. Reverse a String

Using slicing:

```python
text = "Python"

reverse = text[::-1]

print(reverse)
```

Output:

```text
nohtyP
```

Using a loop:

```python
text = "Python"
reverse = ""

for char in text:
    reverse = char + reverse

print(reverse)
```

Output:

```text
nohtyP
```

---

# 39. Check Palindrome

## What?

A palindrome reads the same forward and backward.

Examples:

```text
madam
level
radar
```

Program:

```python
text = "madam"

if text == text[::-1]:
    print("Palindrome")
else:
    print("Not Palindrome")
```

Output:

```text
Palindrome
```

---

# 40. Count Vowels

```python
text = "Python Programming"

count = 0

for char in text.lower():
    if char in "aeiou":
        count += 1

print(count)
```

Output:

```text
4
```

---

# 41. Count Words

```python
text = "Python is easy to learn"

words = text.split()

print(len(words))
```

Output:

```text
5
```

---

# 42. Remove Spaces

Using `replace()`:

```python
text = "Python Programming"

result = text.replace(" ", "")

print(result)
```

Output:

```text
PythonProgramming
```

---

# 43. Check Empty String

```python
text = ""

if text:
    print("String is not empty")
else:
    print("String is empty")
```

Output:

```text
String is empty
```

An empty string is considered **False** in a Boolean context.

---

# 44. String and Type Conversion

Convert a number to string:

```python
age = 40

text = str(age)

print(text)
print(type(text))
```

Output:

```text
40
<class 'str'>
```

Convert string to integer:

```python
text = "100"

number = int(text)

print(number)
print(type(number))
```

Output:

```text
100
<class 'int'>
```

Convert string to float:

```python
price = "99.50"

value = float(price)

print(value)
```

Output:

```text
99.5
```

---

# 45. Taking String Input

`input()` returns a string by default.

```python
name = input("Enter your name: ")

print("Hello", name)
```

Example:

```text
Enter your name: Gaurav
Hello Gaurav
```

Even if the user enters:

```text
40
```

the value returned by `input()` is:

```python
str
```

Check:

```python
age = input("Enter age: ")

print(type(age))
```

Output:

```text
<class 'str'>
```

---

# 46. String Methods Quick Table

| Method | Purpose |
|---|---|
| `upper()` | Convert to uppercase |
| `lower()` | Convert to lowercase |
| `capitalize()` | Capitalize first character |
| `title()` | Capitalize each word |
| `swapcase()` | Swap uppercase/lowercase |
| `casefold()` | Strong lowercase conversion |
| `strip()` | Remove whitespace from both ends |
| `lstrip()` | Remove left whitespace |
| `rstrip()` | Remove right whitespace |
| `find()` | Find substring index |
| `index()` | Find substring index |
| `count()` | Count occurrences |
| `replace()` | Replace text |
| `split()` | String to list |
| `join()` | Join strings |
| `startswith()` | Check beginning |
| `endswith()` | Check ending |
| `isalpha()` | Check alphabetic characters |
| `isdigit()` | Check digits |
| `isalnum()` | Check letters/numbers |
| `isspace()` | Check whitespace |
| `islower()` | Check lowercase |
| `isupper()` | Check uppercase |
| `istitle()` | Check title case |

---

# 47. Important String Concepts

```text
String
  ↓
Indexing
  ↓
Slicing
  ↓
Concatenation
  ↓
Methods
  ↓
Searching
  ↓
Replacing
  ↓
Splitting
  ↓
Joining
  ↓
Formatting
  ↓
Validation
```

---

# 48. Common Mistakes

## Mistake 1 — Wrong Index

```python
text = "Python"

print(text[10])
```

This raises:

```text
IndexError
```

because index `10` does not exist.

## Mistake 2 — Trying to Modify a String

```python
text = "Python"

text[0] = "J"
```

This raises:

```text
TypeError
```

Strings are immutable.

## Mistake 3 — Mixing String and Number

Incorrect:

```python
age = 40

print("Age: " + age)
```

Correct:

```python
print("Age: " + str(age))
```

Or use an f-string:

```python
print(f"Age: {age}")
```

## Mistake 4 — Forgetting That `input()` Returns String

```python
age = input("Enter age: ")
```

`age` is a string.

For arithmetic:

```python
age = int(input("Enter age: "))
```

---

# 49. Real-Life Example — User Data

```python
name = input("Enter name: ")
city = input("Enter city: ")

name = name.strip().title()
city = city.strip().title()

print(f"Name: {name}")
print(f"City: {city}")
```

Example:

```text
Enter name:   gaurav
Enter city:   jaipur

Name: Gaurav
City: Jaipur
```

This demonstrates:

```text
input()
↓
strip()
↓
title()
↓
f-string
```

---

# Quick Revision

| Concept | Meaning |
|---|---|
| String | Sequence of characters |
| Indexing | Access individual character |
| Slicing | Extract part of a string |
| Concatenation | Join strings using `+` |
| Repetition | Repeat string using `*` |
| `len()` | Returns string length |
| `in` | Checks membership |
| `upper()` | Converts to uppercase |
| `lower()` | Converts to lowercase |
| `strip()` | Removes surrounding whitespace |
| `find()` | Searches for substring |
| `replace()` | Replaces text |
| `split()` | Converts string to list |
| `join()` | Converts strings/list into one string |
| `f-string` | Formats values inside strings |
| `input()` | Reads user input as string |
| Immutable | Existing string cannot be changed directly |

# Key Points

- Strings represent text in Python.
- Strings can use single, double, or triple quotes.
- Python uses zero-based indexing.
- Negative indexing starts from `-1`.
- Slicing uses `[start:stop:step]`.
- The stop index in slicing is excluded.
- Strings are immutable.
- `+` joins strings.
- `*` repeats strings.
- `len()` returns the number of characters.
- `split()` converts a string into a list.
- `join()` combines strings.
- `replace()` creates a new modified string.
- `find()` returns `-1` when the substring is not found.
- `input()` returns a string by default.
- Use `int()` or `float()` when numeric input is required.
- F-strings provide a convenient way to format strings.
- Strings can be traversed using loops.

# One-Line Definition

> **String = A sequence of characters enclosed inside quotes and used to represent text.**
