# Python Notes — Lists

# 1. List

## What?

A **list** is an ordered and changeable collection used to store multiple values in a single variable.

Lists are created using square brackets `[]`.

```python
numbers = [10, 20, 30, 40]

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

A list can contain:

- Numbers
- Strings
- Boolean values
- Other lists
- Mixed data types

Example:

```python
data = [10, "Python", True, 25.5]
```

---

## Why?

Lists are useful when:

- Multiple values need to be stored together.
- Data needs to be processed using loops.
- Items need to be added or removed.
- Data needs to be sorted or modified.
- We need an ordered collection.

Real-life examples:

```text
Student names
Product prices
Employee records
Shopping items
Marks
Course names
```

---

## When?

Use a list when:

- Order matters.
- Duplicate values are allowed.
- Values may need to be changed.
- Items may need to be added or deleted.

---

## How?

Create a list using `[]`.

```python
students = ["Gaurav", "Rahul", "Amit"]
```

---

# 2. Creating a List

## Empty List

```python
items = []

print(items)
```

Output:

```text
[]
```

## List of Numbers

```python
numbers = [10, 20, 30, 40]
```

## List of Strings

```python
languages = ["Python", "Java", "JavaScript"]
```

## Mixed List

```python
data = [10, "Python", True, 25.5]
```

---

# 3. List Indexing

## What?

Each item in a list has an index.

Python uses **zero-based indexing**.

```python
languages = ["Python", "Java", "C++", "JavaScript"]
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

# 4. Negative Indexing

Negative indexing starts from the last item.

```python
languages = ["Python", "Java", "C++", "JavaScript"]
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

# 5. List Slicing

## What?

Slicing extracts a portion of a list.

### Syntax

```python
list[start:stop]
```

The `stop` index is excluded.

Example:

```python
numbers = [10, 20, 30, 40, 50]

print(numbers[1:4])
```

Output:

```text
[20, 30, 40]
```

---

# 6. Slicing with Step

### Syntax

```python
list[start:stop:step]
```

Example:

```python
numbers = [10, 20, 30, 40, 50, 60]

print(numbers[0:6:2])
```

Output:

```text
[10, 30, 50]
```

---

# 7. Common List Slicing

```python
numbers = [10, 20, 30, 40, 50]
```

### First 3 Items

```python
print(numbers[:3])
```

Output:

```text
[10, 20, 30]
```

### From Index 2

```python
print(numbers[2:])
```

Output:

```text
[30, 40, 50]
```

### Complete List

```python
print(numbers[:])
```

### Reverse List

```python
print(numbers[::-1])
```

Output:

```text
[50, 40, 30, 20, 10]
```

---

# 8. Lists are Mutable

## What?

A list is **mutable**, meaning its existing items can be changed.

```python
numbers = [10, 20, 30]

numbers[1] = 200

print(numbers)
```

Output:

```text
[10, 200, 30]
```

This is an important difference between a list and a string.

```text
String → Immutable
List   → Mutable
```

---

# 9. List Length — `len()`

`len()` returns the number of items in a list.

```python
students = ["Gaurav", "Rahul", "Amit"]

print(len(students))
```

Output:

```text
3
```

---

# 10. Adding Items — `append()`

## What?

`append()` adds one item at the end of a list.

```python
students = ["Gaurav", "Rahul"]

students.append("Amit")

print(students)
```

Output:

```text
['Gaurav', 'Rahul', 'Amit']
```

### Important

`append()` adds exactly **one item**.

```python
numbers = [1, 2, 3]

numbers.append(4)
```

Result:

```text
[1, 2, 3, 4]
```

---

# 11. Adding Multiple Items — `extend()`

`extend()` adds items from another iterable.

```python
numbers = [1, 2, 3]

numbers.extend([4, 5, 6])

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5, 6]
```

### `append()` vs `extend()`

```python
numbers = [1, 2, 3]

numbers.append([4, 5])
print(numbers)
```

Output:

```text
[1, 2, 3, [4, 5]]
```

Using `extend()`:

```python
numbers = [1, 2, 3]

numbers.extend([4, 5])
print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5]
```

### Remember

```text
append() → adds one item
extend() → adds multiple items
```

---

# 12. Insert Item — `insert()`

`insert()` adds an item at a specific index.

### Syntax

```python
list.insert(index, value)
```

Example:

```python
numbers = [10, 20, 40]

numbers.insert(2, 30)

print(numbers)
```

Output:

```text
[10, 20, 30, 40]
```

---

# 13. Remove Item — `remove()`

`remove()` removes the first matching value.

```python
numbers = [10, 20, 30, 20]

numbers.remove(20)

print(numbers)
```

Output:

```text
[10, 30, 20]
```

Only the first matching `20` is removed.

If the value does not exist, `remove()` raises `ValueError`.

---

# 14. Remove Item by Index — `pop()`

`pop()` removes and returns an item.

## Without Index

```python
numbers = [10, 20, 30]

result = numbers.pop()

print(result)
print(numbers)
```

Output:

```text
30
[10, 20]
```

The last item is removed.

## With Index

```python
numbers = [10, 20, 30]

result = numbers.pop(1)

print(result)
print(numbers)
```

Output:

```text
20
[10, 30]
```

---

# 15. Delete Using `del`

`del` can delete an item by index.

```python
numbers = [10, 20, 30]

del numbers[1]

print(numbers)
```

Output:

```text
[10, 30]
```

It can also delete a slice:

```python
numbers = [10, 20, 30, 40, 50]

del numbers[1:4]

print(numbers)
```

Output:

```text
[10, 50]
```

---

# 16. Clear a List — `clear()`

`clear()` removes all items.

```python
numbers = [10, 20, 30]

numbers.clear()

print(numbers)
```

Output:

```text
[]
```

### Difference

```text
clear() → removes all items but keeps the list
del     → can delete items or the entire variable
```

---

# 17. Copy a List — `copy()`

Use `copy()` to create a shallow copy.

```python
numbers = [10, 20, 30]

new_numbers = numbers.copy()

print(new_numbers)
```

Output:

```text
[10, 20, 30]
```

---

# 18. Why Direct Assignment Can Be Confusing

Consider:

```python
a = [10, 20, 30]
b = a

b.append(40)

print(a)
print(b)
```

Output:

```text
[10, 20, 30, 40]
[10, 20, 30, 40]
```

Both names refer to the same list object.

Use `copy()` when an independent shallow copy is required:

```python
a = [10, 20, 30]
b = a.copy()

b.append(40)

print(a)
print(b)
```

Output:

```text
[10, 20, 30]
[10, 20, 30, 40]
```

---

# 19. Searching in a List — `in`

Use `in` to check whether an item exists.

```python
languages = ["Python", "Java", "C++"]

print("Python" in languages)
print("PHP" in languages)
```

Output:

```text
True
False
```

Use `not in`:

```python
print("PHP" not in languages)
```

Output:

```text
True
```

---

# 20. Find Position — `index()`

`index()` returns the position of the first matching item.

```python
languages = ["Python", "Java", "C++"]

print(languages.index("Java"))
```

Output:

```text
1
```

If the item does not exist, `ValueError` is raised.

---

# 21. Count Items — `count()`

`count()` returns how many times a value occurs.

```python
numbers = [1, 2, 1, 3, 1, 2]

print(numbers.count(1))
print(numbers.count(2))
```

Output:

```text
3
2
```

---

# 22. Sorting a List — `sort()`

`sort()` changes the original list.

## Ascending

```python
numbers = [50, 10, 40, 20, 30]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30, 40, 50]
```

## Descending

```python
numbers.sort(reverse=True)

print(numbers)
```

Output:

```text
[50, 40, 30, 20, 10]
```

---

# 23. `sorted()` Function

`sorted()` returns a new sorted list and does not modify the original list.

```python
numbers = [50, 10, 40, 20, 30]

new_numbers = sorted(numbers)

print(numbers)
print(new_numbers)
```

Output:

```text
[50, 10, 40, 20, 30]
[10, 20, 30, 40, 50]
```

### Difference

```text
sort()   → modifies original list
sorted() → returns a new sorted list
```

---

# 24. Reverse a List — `reverse()`

`reverse()` reverses the original list.

```python
numbers = [10, 20, 30, 40]

numbers.reverse()

print(numbers)
```

Output:

```text
[40, 30, 20, 10]
```

Another option:

```python
numbers = [10, 20, 30, 40]

print(numbers[::-1])
```

The slicing approach returns a new list.

---

# 25. Minimum, Maximum and Sum

Python provides useful built-in functions.

```python
numbers = [10, 20, 30, 40]

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

# 26. Iterating Through a List

Use a `for` loop to process each item.

```python
languages = ["Python", "Java", "JavaScript"]

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

# 27. List with `range()`

```python
numbers = [10, 20, 30, 40]

for i in range(len(numbers)):
    print(numbers[i])
```

Output:

```text
10
20
30
40
```

Usually, direct iteration is simpler:

```python
for number in numbers:
    print(number)
```

---

# 28. `enumerate()`

Use `enumerate()` when both index and value are needed.

```python
students = ["Gaurav", "Rahul", "Amit"]

for index, name in enumerate(students):
    print(index, name)
```

Output:

```text
0 Gaurav
1 Rahul
2 Amit
```

Start from another number:

```python
for index, name in enumerate(students, start=1):
    print(index, name)
```

Output:

```text
1 Gaurav
2 Rahul
3 Amit
```

---

# 29. Nested Lists

A list can contain other lists.

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matrix)
```

Access an item:

```python
print(matrix[1][2])
```

Output:

```text
6
```

Here:

```text
matrix[1]    → [4, 5, 6]
matrix[1][2] → 6
```

---

# 30. Nested List with Loop

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]

for row in matrix:
    for value in row:
        print(value)
```

Output:

```text
1
2
3
4
5
6
```

---

# 31. List Comprehension

## What?

List comprehension is a compact way to create a list.

### Normal Approach

```python
numbers = []

for i in range(1, 6):
    numbers.append(i)

print(numbers)
```

### List Comprehension

```python
numbers = [i for i in range(1, 6)]

print(numbers)
```

Output:

```text
[1, 2, 3, 4, 5]
```

### Basic Syntax

```python
[expression for item in iterable]
```

---

# 32. List Comprehension with Condition

Create only even numbers:

```python
even_numbers = [i for i in range(1, 11) if i % 2 == 0]

print(even_numbers)
```

Output:

```text
[2, 4, 6, 8, 10]
```

### Syntax

```python
[expression for item in iterable if condition]
```

---

# 33. List Comprehension with `if-else`

```python
result = [
    "Even" if i % 2 == 0 else "Odd"
    for i in range(1, 6)
]

print(result)
```

Output:

```text
['Odd', 'Even', 'Odd', 'Even', 'Odd']
```

---

# 34. Modify Values with List Comprehension

```python
numbers = [1, 2, 3, 4, 5]

squares = [number ** 2 for number in numbers]

print(squares)
```

Output:

```text
[1, 4, 9, 16, 25]
```

---

# 35. Filtering a List

```python
numbers = [10, 15, 20, 25, 30]

result = [number for number in numbers if number >= 20]

print(result)
```

Output:

```text
[20, 25, 30]
```

---

# 36. List of Strings

```python
names = ["gaurav", "rahul", "amit"]

names = [name.title() for name in names]

print(names)
```

Output:

```text
['Gaurav', 'Rahul', 'Amit']
```

---

# 37. Combining Lists

Use `+` to concatenate lists.

```python
a = [1, 2, 3]
b = [4, 5, 6]

result = a + b

print(result)
```

Output:

```text
[1, 2, 3, 4, 5, 6]
```

---

# 38. Repeating Lists

Use `*` to repeat a list.

```python
numbers = [1, 2]

print(numbers * 3)
```

Output:

```text
[1, 2, 1, 2, 1, 2]
```

---

# 39. Unpacking a List

List values can be assigned to multiple variables.

```python
numbers = [10, 20, 30]

a, b, c = numbers

print(a)
print(b)
print(c)
```

Output:

```text
10
20
30
```

The number of variables must normally match the number of values.

---

# 40. Extended Unpacking

The `*` operator can collect remaining values.

```python
numbers = [10, 20, 30, 40, 50]

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

---

# 41. List of Different Data Types

A list can contain different data types.

```python
data = [
    10,
    25.5,
    "Python",
    True,
    None
]

print(data)
```

Output:

```text
[10, 25.5, 'Python', True, None]
```

Python lists are not restricted to one data type.

---

# 42. List with Functions

Lists can be passed to functions.

```python
def calculate_total(numbers):
    return sum(numbers)

values = [10, 20, 30]

print(calculate_total(values))
```

Output:

```text
60
```

---

# 43. List of Dictionaries

A common real-world structure is a list containing dictionaries.

```python
students = [
    {"name": "Gaurav", "marks": 85},
    {"name": "Rahul", "marks": 78},
    {"name": "Amit", "marks": 92}
]

print(students[0]["name"])
```

Output:

```text
Gaurav
```

This structure is commonly used for JSON-like data.

---

# 44. Real-Life Example — Shopping Cart

```python
cart = ["Laptop", "Mouse", "Keyboard"]

cart.append("Monitor")

print(cart)
```

Output:

```text
['Laptop', 'Mouse', 'Keyboard', 'Monitor']
```

Remove an item:

```python
cart.remove("Mouse")

print(cart)
```

Output:

```text
['Laptop', 'Keyboard', 'Monitor']
```

---

# 45. Real-Life Example — Student Marks

```python
marks = [85, 72, 90, 65, 88]

print("Total:", sum(marks))
print("Highest:", max(marks))
print("Lowest:", min(marks))
print("Average:", sum(marks) / len(marks))
```

Output:

```text
Total: 400
Highest: 90
Lowest: 65
Average: 80.0
```

---

# 46. List Methods Quick Table

| Method | Purpose |
|---|---|
| `append()` | Add one item at end |
| `extend()` | Add multiple items |
| `insert()` | Add item at specific index |
| `remove()` | Remove first matching value |
| `pop()` | Remove and return item |
| `clear()` | Remove all items |
| `copy()` | Create shallow copy |
| `index()` | Find first matching index |
| `count()` | Count occurrences |
| `sort()` | Sort original list |
| `reverse()` | Reverse original list |

---

# 47. List vs String

| Feature | List | String |
|---|---|---|
| Collection | Multiple values | Sequence of characters |
| Mutable | Yes | No |
| Syntax | `[]` | Quotes |
| Indexing | Yes | Yes |
| Slicing | Yes | Yes |
| `len()` | Yes | Yes |
| `append()` | Yes | No |
| `replace()` | No | Yes |
| `split()` | No | Yes |
| `join()` | Used with strings | Yes |

Example:

```python
text = "Python"
items = ["Python", "Java"]
```

---

# 48. Common Mistakes

## Mistake 1 — Invalid Index

```python
numbers = [10, 20, 30]

print(numbers[5])
```

This raises:

```text
IndexError
```

## Mistake 2 — Confusing `append()` and `extend()`

```python
numbers = [1, 2]

numbers.append([3, 4])

print(numbers)
```

Output:

```text
[1, 2, [3, 4]]
```

If you want separate items:

```python
numbers = [1, 2]

numbers.extend([3, 4])

print(numbers)
```

Output:

```text
[1, 2, 3, 4]
```

## Mistake 3 — Removing a Missing Value

```python
numbers = [1, 2, 3]

numbers.remove(10)
```

This raises:

```text
ValueError
```

Safer:

```python
if 10 in numbers:
    numbers.remove(10)
```

---

# 49. Important List Flow

```text
Create List
    ↓
Access Items
    ↓
Index / Slice
    ↓
Add Items
    ↓
Modify Items
    ↓
Remove Items
    ↓
Search / Count
    ↓
Sort / Reverse
    ↓
Loop / Process
    ↓
List Comprehension
```

---

# Quick Revision

| Concept | Meaning |
|---|---|
| List | Ordered, mutable collection |
| `[]` | List syntax |
| Indexing | Access item by position |
| Negative indexing | Access from end |
| Slicing | Extract part of list |
| `len()` | Number of items |
| `append()` | Add one item |
| `extend()` | Add multiple items |
| `insert()` | Add at specific index |
| `remove()` | Remove by value |
| `pop()` | Remove by index and return item |
| `del` | Delete item/slice |
| `clear()` | Empty list |
| `copy()` | Create shallow copy |
| `index()` | Find item position |
| `count()` | Count occurrences |
| `sort()` | Sort original list |
| `sorted()` | Return sorted list |
| `reverse()` | Reverse original list |
| `enumerate()` | Get index and value |
| List comprehension | Compact list creation |

# Key Points

- Lists are ordered collections.
- Lists are mutable.
- Lists allow duplicate values.
- Lists can contain different data types.
- Indexing starts from `0`.
- Negative indexing starts from `-1`.
- Slicing uses `[start:stop:step]`.
- `append()` adds one item.
- `extend()` adds multiple items.
- `insert()` adds at a specific position.
- `remove()` removes by value.
- `pop()` removes and returns an item.
- `sort()` modifies the original list.
- `sorted()` returns a new sorted list.
- `copy()` creates a shallow copy.
- `enumerate()` is useful when both index and value are needed.
- List comprehension provides a compact way to create lists.
- Nested lists are useful for matrix and table-like data.
- A list can contain dictionaries and other lists.

# One-Line Definition

> **List = An ordered and mutable collection used to store multiple values in a single variable.**
