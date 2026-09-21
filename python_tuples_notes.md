# Python Notes — Tuples

# 1. Tuple

## What?

A **tuple** is an ordered and immutable collection used to store multiple values in a single variable.

Tuples are generally created using parentheses `()`.

```python
numbers = (10, 20, 30, 40)

print(numbers)
```

Output:

```text
(10, 20, 30, 40)
```

A tuple can contain:

- Numbers
- Strings
- Boolean values
- Other tuples
- Lists
- Mixed data types

Example:

```python
data = (10, "Python", True, 25.5)
```

---

## Why?

Tuples are useful when:

- Data should remain unchanged.
- Order matters.
- Duplicate values are allowed.
- A fixed collection of values is required.
- You want to communicate that data should not be modified.

Real-life examples:

```text
Coordinates
RGB color values
Database records
Days of the week
Months
Configuration values
Student record
```

Example:

```python
coordinates = (26.9124, 75.7873)
```

---

## When?

Use a tuple when:

- The collection should not be changed after creation.
- You want an ordered fixed sequence.
- You need to return multiple values from a function.
- Data integrity is important.

---

## How?

Use parentheses:

```python
items = ("Python", "Java", "C++")
```

A tuple can also be created without parentheses using commas:

```python
items = "Python", "Java", "C++"

print(items)
```

Output:

```text
('Python', 'Java', 'C++')
```

---

# 2. Creating a Tuple

## Empty Tuple

```python
items = ()

print(items)
```

Output:

```text
()
```

## Tuple of Numbers

```python
numbers = (10, 20, 30, 40)
```

## Tuple of Strings

```python
languages = ("Python", "Java", "JavaScript")
```

## Mixed Tuple

```python
data = (10, "Python", True, 25.5)
```

---

# 3. Single-Item Tuple

This is an important concept.

A comma is required to create a one-item tuple.

Correct:

```python
number = (10,)

print(type(number))
```

Output:

```text
<class 'tuple'>
```

Without the comma:

```python
number = (10)

print(type(number))
```

Output:

```text
<class 'int'>
```

### Remember

```text
(10)  → int
(10,) → tuple
```

The comma creates the tuple.

---

# 4. Tuple Indexing

## What?

Each item in a tuple has an index.

Python uses **zero-based indexing**.

```python
languages = ("Python", "Java", "C++", "JavaScript")
```

Indexes:

```text
Python      → 0
Java        → 1
C++         → 2
JavaScript  → 3
```

Example:

```python
print(languages[0])
print(languages[2])
```

Output:

```text
Python
C++
```

---

# 5. Negative Indexing

Negative indexing starts from the last item.

```python
languages = ("Python", "Java", "C++", "JavaScript")
```

```text
Python      → -4
Java        → -3
C++         → -2
JavaScript  → -1
```

Example:

```python
print(languages[-1])
print(languages[-2])
```

Output:

```text
JavaScript
C++
```

---

# 6. Tuple Slicing

## What?

Slicing extracts a portion of a tuple.

### Syntax

```python
tuple[start:stop]
```

The `stop` index is excluded.

Example:

```python
numbers = (10, 20, 30, 40, 50)

print(numbers[1:4])
```

Output:

```text
(20, 30, 40)
```

---

# 7. Tuple Slicing with Step

```python
numbers = (10, 20, 30, 40, 50, 60)

print(numbers[0:6:2])
```

Output:

```text
(10, 30, 50)
```

### Reverse Tuple

```python
print(numbers[::-1])
```

Output:

```text
(60, 50, 40, 30, 20, 10)
```

---

# 8. Tuples are Immutable

## What?

A tuple is **immutable**.

This means its existing elements cannot be changed, added, or removed directly after creation.

Example:

```python
numbers = (10, 20, 30)

numbers[1] = 200
```

This raises:

```text
TypeError
```

---

## Why?

Immutability is useful when data should remain fixed.

Example:

```python
coordinates = (26.9124, 75.7873)
```

The coordinate pair can be treated as a fixed value.

---

# 9. Tuple vs List Mutability

List:

```python
numbers = [10, 20, 30]

numbers[1] = 200

print(numbers)
```

Output:

```text
[10, 200, 30]
```

Tuple:

```python
numbers = (10, 20, 30)

numbers[1] = 200
```

Raises:

```text
TypeError
```

### Remember

```text
List  → Mutable
Tuple → Immutable
```

---

# 10. `len()` with Tuple

`len()` returns the number of items.

```python
numbers = (10, 20, 30, 40)

print(len(numbers))
```

Output:

```text
4
```

---

# 11. Tuple Membership

Use:

```python
in
not in
```

Example:

```python
languages = ("Python", "Java", "C++")

print("Python" in languages)
print("PHP" in languages)
```

Output:

```text
True
False
```

Example:

```python
print("PHP" not in languages)
```

Output:

```text
True
```

---

# 12. Tuple Methods

Because tuples are immutable, they have fewer methods than lists.

The two main tuple methods are:

```text
count()
index()
```

---

# 13. `count()`

`count()` returns the number of times a value occurs.

```python
numbers = (10, 20, 10, 30, 10)

print(numbers.count(10))
```

Output:

```text
3
```

---

# 14. `index()`

`index()` returns the index of the first matching value.

```python
languages = ("Python", "Java", "C++")

print(languages.index("Java"))
```

Output:

```text
1
```

If the value does not exist, `ValueError` is raised.

---

# 15. Tuple Concatenation

Use `+` to combine tuples.

```python
a = (1, 2, 3)
b = (4, 5, 6)

result = a + b

print(result)
```

Output:

```text
(1, 2, 3, 4, 5, 6)
```

A new tuple is created.

---

# 16. Tuple Repetition

Use `*` to repeat a tuple.

```python
numbers = (1, 2)

print(numbers * 3)
```

Output:

```text
(1, 2, 1, 2, 1, 2)
```

---

# 17. Tuple Packing

Putting multiple values into one tuple is called **tuple packing**.

```python
student = "Gaurav", 40, "Jaipur"

print(student)
```

Output:

```text
('Gaurav', 40, 'Jaipur')
```

Python automatically creates a tuple because of the commas.

---

# 18. Tuple Unpacking

Assign tuple values to multiple variables.

```python
student = ("Gaurav", 40, "Jaipur")

name, age, city = student

print(name)
print(age)
print(city)
```

Output:

```text
Gaurav
40
Jaipur
```

The number of variables should normally match the number of values.

---

# 19. Extended Tuple Unpacking

The `*` operator can collect remaining values.

```python
numbers = (10, 20, 30, 40, 50)

first, *middle, last = numbers

print(first)
print(middle)
print(last)
```

Output:

```text
10
[20, 30, 40]
50
```

Notice that the starred variable receives a **list**.

---

# 20. Swapping Variables Using Tuple Unpacking

Python allows easy variable swapping.

```python
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```

Output:

```text
20
10
```

Conceptually, Python packs the right side and unpacks it into the variables.

---

# 21. Loop Through a Tuple

```python
languages = ("Python", "Java", "JavaScript")

for language in languages:
    print(language)
```

Output:

```text
Python
Java
JavaScript
```

---

# 22. Tuple with `enumerate()`

Use `enumerate()` when both index and value are required.

```python
languages = ("Python", "Java", "JavaScript")

for index, language in enumerate(languages):
    print(index, language)
```

Output:

```text
0 Python
1 Java
2 JavaScript
```

---

# 23. Nested Tuples

A tuple can contain other tuples.

```python
data = (
    ("Gaurav", 40),
    ("Rahul", 35),
    ("Amit", 30)
)

print(data)
```

Access nested values:

```python
print(data[0][0])
print(data[1][1])
```

Output:

```text
Gaurav
35
```

---

# 24. Tuple Containing a List

A tuple itself is immutable, but it can contain a mutable object such as a list.

```python
data = ("Python", [10, 20, 30])

data[1].append(40)

print(data)
```

Output:

```text
('Python', [10, 20, 30, 40])
```

### Important

The tuple's references cannot be replaced, but the mutable list object inside it can change.

For example, this is not allowed:

```python
data[0] = "Java"
```

But modifying the contained list is possible:

```python
data[1].append(40)
```

---

# 25. Convert List to Tuple

Use `tuple()`.

```python
numbers = [10, 20, 30]

result = tuple(numbers)

print(result)
print(type(result))
```

Output:

```text
(10, 20, 30)
<class 'tuple'>
```

---

# 26. Convert Tuple to List

Use `list()`.

```python
numbers = (10, 20, 30)

result = list(numbers)

print(result)
print(type(result))
```

Output:

```text
[10, 20, 30]
<class 'list'>
```

This is useful when tuple data needs to be modified.

---

# 27. Modifying Tuple Indirectly

A tuple cannot be modified directly, but you can convert it to a list.

```python
numbers = (10, 20, 30)

temp = list(numbers)

temp[1] = 200

numbers = tuple(temp)

print(numbers)
```

Output:

```text
(10, 200, 30)
```

The original tuple was not modified directly; a new tuple was created.

---

# 28. Sorting a Tuple

Tuples do not have a `sort()` method.

Use the built-in `sorted()` function.

```python
numbers = (50, 10, 40, 20, 30)

result = sorted(numbers)

print(result)
```

Output:

```text
[10, 20, 30, 40, 50]
```

Notice that `sorted()` returns a **list**.

To get a tuple:

```python
result = tuple(sorted(numbers))

print(result)
```

Output:

```text
(10, 20, 30, 40, 50)
```

---

# 29. `min()`, `max()`, `sum()`

Built-in functions can work with numeric tuples.

```python
numbers = (10, 20, 30, 40)

print(min(numbers))
print(max(numbers))
print(sum(numbers))
```

Output:

```text
10
40
100
```

Average:

```python
average = sum(numbers) / len(numbers)

print(average)
```

Output:

```text
25.0
```

---

# 30. Tuple Comparison

Tuples can be compared.

```python
a = (1, 2, 3)
b = (1, 2, 3)

print(a == b)
```

Output:

```text
True
```

Example:

```python
a = (1, 2)
b = (1, 3)

print(a < b)
```

Output:

```text
True
```

Tuple comparisons are performed element by element.

---

# 31. Tuple as Function Return Value

Functions can return multiple values using a tuple.

```python
def calculate(a, b):
    return a + b, a - b

addition, subtraction = calculate(10, 5)

print(addition)
print(subtraction)
```

Output:

```text
15
5
```

This is a common practical use of tuples.

---

# 32. Tuple as Dictionary Key

Tuples containing hashable values can be used as dictionary keys.

```python
locations = {
    (26.9124, 75.7873): "Jaipur"
}

print(locations[(26.9124, 75.7873)])
```

Output:

```text
Jaipur
```

This is useful for coordinates and other fixed composite keys.

A list cannot be used as a dictionary key because lists are mutable.

---

# 33. Real-Life Example — Coordinates

```python
point = (26.9124, 75.7873)

latitude, longitude = point

print("Latitude:", latitude)
print("Longitude:", longitude)
```

Output:

```text
Latitude: 26.9124
Longitude: 75.7873
```

---

# 34. Real-Life Example — Student Record

```python
student = ("Gaurav", 40, "Python", 85)

name, age, course, marks = student

print("Name:", name)
print("Age:", age)
print("Course:", course)
print("Marks:", marks)
```

Output:

```text
Name: Gaurav
Age: 40
Course: Python
Marks: 85
```

If the record should be treated as fixed data, a tuple can be appropriate.

---

# 35. Real-Life Example — RGB Color

```python
red = (255, 0, 0)
green = (0, 255, 0)
blue = (0, 0, 255)

print(red)
print(green)
print(blue)
```

Each RGB value contains three fixed components.

---

# 36. Tuple vs List

| Feature | List | Tuple |
|---|---|---|
| Syntax | `[]` | `()` |
| Ordered | Yes | Yes |
| Mutable | Yes | No |
| Duplicate values | Allowed | Allowed |
| Indexing | Yes | Yes |
| Slicing | Yes | Yes |
| `append()` | Yes | No |
| `remove()` | Yes | No |
| `pop()` | Yes | No |
| `sort()` method | Yes | No |
| `count()` | Yes | Yes |
| `index()` | Yes | Yes |
| Can contain mixed types | Yes | Yes |
| Can be dictionary key | No | Yes, if hashable |
| Typical use | Changeable collection | Fixed collection |

---

# 37. Tuple vs String

| Feature | Tuple | String |
|---|---|---|
| Stores | Multiple values | Characters/text |
| Immutable | Yes | Yes |
| Indexing | Yes | Yes |
| Slicing | Yes | Yes |
| `len()` | Yes | Yes |
| `count()` | Yes | Yes |
| `index()` | Yes | Yes |
| `append()` | No | No |
| `split()` | No | Yes |
| `join()` | Used with strings | Yes |

---

# 38. List vs Tuple — Simple Rule

Use a **list** when:

```text
Data may change.
```

Example:

```python
shopping_cart = ["Laptop", "Mouse"]
shopping_cart.append("Keyboard")
```

Use a **tuple** when:

```text
Data should remain fixed.
```

Example:

```python
coordinates = (26.9124, 75.7873)
```

---

# 39. Common Mistakes

## Mistake 1 — Forgetting Comma in Single-Item Tuple

Wrong:

```python
value = (10)
```

This is an integer.

Correct:

```python
value = (10,)
```

---

## Mistake 2 — Trying to Modify Tuple

```python
numbers = (10, 20, 30)

numbers[0] = 100
```

This raises:

```text
TypeError
```

---

## Mistake 3 — Expecting `sort()` on Tuple

Wrong:

```python
numbers = (30, 10, 20)

numbers.sort()
```

Tuples do not have `sort()`.

Correct:

```python
numbers = (30, 10, 20)

result = tuple(sorted(numbers))

print(result)
```

Output:

```text
(10, 20, 30)
```

---

## Mistake 4 — Wrong Number of Unpacking Variables

```python
numbers = (10, 20, 30)

a, b = numbers
```

This raises:

```text
ValueError
```

because there are three values but only two variables.

---

# 40. Important Tuple Flow

```text
Create Tuple
    ↓
Index / Slice
    ↓
Read Data
    ↓
Search / Count
    ↓
Loop
    ↓
Unpack
    ↓
Use as Fixed Data
    ↓
Optional Conversion to List
```

---

# Quick Revision

| Concept | Meaning |
|---|---|
| Tuple | Ordered, immutable collection |
| `()` | Common tuple syntax |
| Single-item tuple | Requires a comma |
| Indexing | Access item by position |
| Negative indexing | Access from end |
| Slicing | Extract part of tuple |
| `len()` | Number of items |
| `count()` | Count occurrences |
| `index()` | Find first matching index |
| Packing | Put multiple values into tuple |
| Unpacking | Assign tuple values to variables |
| `*` unpacking | Collect remaining values |
| `tuple()` | Convert iterable to tuple |
| `list()` | Convert tuple to list |
| `sorted()` | Return sorted list |
| Immutable | Cannot change tuple elements directly |

---

# Key Points

- Tuples are ordered collections.
- Tuples are immutable.
- Tuples allow duplicate values.
- Tuples can contain different data types.
- Indexing starts from `0`.
- Negative indexing starts from `-1`.
- Slicing works like lists and strings.
- A one-item tuple requires a trailing comma.
- Tuple has two main methods: `count()` and `index()`.
- Tuples can be concatenated with `+`.
- Tuples can be repeated with `*`.
- Tuple packing stores multiple values together.
- Tuple unpacking assigns values to multiple variables.
- `*` can collect remaining unpacked values.
- Tuples can contain mutable objects such as lists.
- `sorted()` can sort tuple data but returns a list.
- Tuples are commonly used for fixed records and multiple return values.
- Hashable tuples can be used as dictionary keys.

# One-Line Definition

> **Tuple = An ordered and immutable collection used to store multiple values in a single variable.**
