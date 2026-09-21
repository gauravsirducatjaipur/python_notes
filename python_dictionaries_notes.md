# Python Notes — Dictionaries

# 1. Dictionary

## What?

A **dictionary** is a mutable collection that stores data in **key-value pairs**.

Dictionaries are created using curly braces `{}`.

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "city": "Jaipur"
}

print(student)
```

Output:

```text
{'name': 'Gaurav', 'age': 40, 'city': 'Jaipur'}
```

Here:

```text
"name"  → key
"Gaurav" → value

"age"   → key
40      → value
```

---

## Why?

Dictionaries are useful when data needs to be stored with meaningful labels.

Instead of:

```python
student = ["Gaurav", 40, "Jaipur"]
```

we can write:

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "city": "Jaipur"
}
```

The second approach makes the meaning of each value clear.

Real-life examples:

- Student records
- Employee records
- Product information
- User profiles
- API/JSON data
- Configuration settings
- Database-like records

---

## When?

Use a dictionary when:

- Data has a key-value relationship.
- You need to access values using meaningful keys.
- Fast key-based lookup is required.
- A record contains different types of information.

---

## How?

Create a dictionary using:

```python
{
    key: value,
    key: value
}
```

Example:

```python
person = {
    "name": "Gaurav",
    "age": 40
}
```

---

# 2. Dictionary Keys and Values

A dictionary contains:

```text
Key → Value
```

Example:

```python
student = {
    "name": "Gaurav",
    "marks": 85
}
```

Here:

```text
name  → key
Gaurav → value

marks → key
85    → value
```

Keys identify the data, while values contain the actual data.

---

# 3. Creating a Dictionary

## Empty Dictionary

```python
data = {}

print(data)
```

Output:

```text
{}
```

Using `dict()`:

```python
data = dict()

print(data)
```

Output:

```text
{}
```

---

## Dictionary with Values

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "course": "Python"
}
```

---

# 4. Dictionary Rules

Important rules:

- Keys must be unique.
- Keys must be hashable.
- Values can be duplicated.
- Values can have different data types.
- Dictionaries are mutable.
- Modern Python dictionaries preserve insertion order.
- A dictionary is accessed by keys, not numeric indexes.

Example:

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "marks": 85
}
```

---

# 5. Duplicate Keys

Dictionary keys must be unique.

If the same key is written more than once, the later value replaces the earlier value.

```python
student = {
    "name": "Gaurav",
    "name": "Rahul"
}

print(student)
```

Output:

```text
{'name': 'Rahul'}
```

### Remember

```text
Duplicate key → last assigned value remains
```

---

# 6. Access Dictionary Values

Use the key inside square brackets.

```python
student = {
    "name": "Gaurav",
    "age": 40
}

print(student["name"])
print(student["age"])
```

Output:

```text
Gaurav
40
```

---

# 7. Access Using `get()`

`get()` is another way to access a value.

```python
student = {
    "name": "Gaurav",
    "age": 40
}

print(student.get("name"))
```

Output:

```text
Gaurav
```

---

# 8. `[]` vs `get()`

Consider:

```python
student = {
    "name": "Gaurav"
}
```

Using `[]`:

```python
print(student["age"])
```

This raises:

```text
KeyError
```

Using `get()`:

```python
print(student.get("age"))
```

Output:

```text
None
```

You can also provide a default value:

```python
print(student.get("age", 0))
```

Output:

```text
0
```

### Remember

```text
dict[key]       → KeyError if key is missing
dict.get(key)   → None if key is missing
dict.get(key, default) → default if key is missing
```

---

# 9. Add a New Key-Value Pair

A new item can be added by assigning a value to a new key.

```python
student = {
    "name": "Gaurav",
    "age": 40
}

student["city"] = "Jaipur"

print(student)
```

Result contains:

```text
name
age
city
```

---

# 10. Modify a Value

Assign a new value to an existing key.

```python
student = {
    "name": "Gaurav",
    "age": 40
}

student["age"] = 41

print(student)
```

The value of `age` is changed to `41`.

---

# 11. Add vs Modify

```python
student["city"] = "Jaipur"
```

If `"city"` does not exist:

```text
New key is added.
```

If `"city"` already exists:

```text
Existing value is replaced.
```

---

# 12. Check Key Existence

Use `in`.

```python
student = {
    "name": "Gaurav",
    "age": 40
}

print("name" in student)
print("city" in student)
```

Output:

```text
True
False
```

Use `not in`:

```python
print("city" not in student)
```

Output:

```text
True
```

> `in` on a dictionary checks **keys**, not values.

---

# 13. Check Value Existence

Use the `values()` view.

```python
student = {
    "name": "Gaurav",
    "age": 40
}

print("Gaurav" in student.values())
print(40 in student.values())
```

Output:

```text
True
True
```

---

# 14. Dictionary Length

Use `len()`.

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "city": "Jaipur"
}

print(len(student))
```

Output:

```text
3
```

It counts key-value pairs.

---

# 15. Get All Keys — `keys()`

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "city": "Jaipur"
}

print(student.keys())
```

It returns a dictionary view containing the keys.

Convert to a list if required:

```python
print(list(student.keys()))
```

Output:

```text
['name', 'age', 'city']
```

---

# 16. Get All Values — `values()`

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "city": "Jaipur"
}

print(student.values())
```

Convert to a list:

```python
print(list(student.values()))
```

Output:

```text
['Gaurav', 40, 'Jaipur']
```

---

# 17. Get Key-Value Pairs — `items()`

`items()` returns key-value pairs.

```python
student = {
    "name": "Gaurav",
    "age": 40
}

print(student.items())
```

Convert to a list:

```python
print(list(student.items()))
```

Output:

```text
[('name', 'Gaurav'), ('age', 40)]
```

Each pair behaves like a two-item tuple.

---

# 18. Loop Through Dictionary

## Loop Through Keys

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "city": "Jaipur"
}

for key in student:
    print(key)
```

Output:

```text
name
age
city
```

---

## Loop Through Values

```python
for value in student.values():
    print(value)
```

Output:

```text
Gaurav
40
Jaipur
```

---

## Loop Through Key and Value

Use `items()`.

```python
for key, value in student.items():
    print(key, value)
```

Output:

```text
name Gaurav
age 40
city Jaipur
```

---

# 19. Remove Item — `pop()`

`pop(key)` removes the specified key and returns its value.

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "city": "Jaipur"
}

result = student.pop("age")

print(result)
print(student)
```

Output:

```text
40
{'name': 'Gaurav', 'city': 'Jaipur'}
```

If the key does not exist, `KeyError` is raised unless a default is provided.

```python
student.pop("salary", None)
```

---

# 20. Remove Last Inserted Pair — `popitem()`

`popitem()` removes and returns the last inserted key-value pair.

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "city": "Jaipur"
}

result = student.popitem()

print(result)
print(student)
```

Output:

```text
('city', 'Jaipur')
{'name': 'Gaurav', 'age': 40}
```

---

# 21. Delete Using `del`

```python
student = {
    "name": "Gaurav",
    "age": 40,
    "city": "Jaipur"
}

del student["age"]

print(student)
```

The `age` key-value pair is removed.

You can also delete the complete dictionary variable:

```python
del student
```

After that, using `student` raises `NameError`.

---

# 22. Clear Dictionary — `clear()`

`clear()` removes all key-value pairs.

```python
student = {
    "name": "Gaurav",
    "age": 40
}

student.clear()

print(student)
```

Output:

```text
{}
```

The dictionary variable still exists.

---

# 23. Copy Dictionary — `copy()`

Use `copy()` to create a shallow copy.

```python
student = {
    "name": "Gaurav",
    "age": 40
}

new_student = student.copy()

print(new_student)
```

The copied dictionary is a separate top-level dictionary.

---

# 24. Assignment vs Copy

Consider:

```python
a = {
    "name": "Gaurav"
}

b = a

b["age"] = 40

print(a)
print(b)
```

Both dictionaries are affected because `a` and `b` refer to the same dictionary object.

Use `copy()`:

```python
a = {
    "name": "Gaurav"
}

b = a.copy()

b["age"] = 40

print(a)
print(b)
```

Now:

```text
a → {'name': 'Gaurav'}
b → {'name': 'Gaurav', 'age': 40}
```

---

# 25. Update Dictionary — `update()`

`update()` adds or modifies multiple key-value pairs.

```python
student = {
    "name": "Gaurav",
    "age": 40
}

student.update({
    "city": "Jaipur",
    "age": 41
})

print(student)
```

Result contains:

```text
name → Gaurav
age  → 41
city → Jaipur
```

Existing keys are updated and new keys are added.

---

# 26. Create Dictionary with `fromkeys()`

`fromkeys()` creates a dictionary from a sequence of keys.

```python
keys = ["name", "age", "city"]

student = dict.fromkeys(keys)

print(student)
```

Output:

```text
{'name': None, 'age': None, 'city': None}
```

Provide a default value:

```python
student = dict.fromkeys(keys, "Unknown")

print(student)
```

Output:

```text
{'name': 'Unknown', 'age': 'Unknown', 'city': 'Unknown'}
```

---

# 27. Nested Dictionary

A dictionary can contain another dictionary.

```python
students = {
    "student1": {
        "name": "Gaurav",
        "marks": 85
    },
    "student2": {
        "name": "Rahul",
        "marks": 78
    }
}
```

Access nested data:

```python
print(students["student1"]["name"])
```

Output:

```text
Gaurav
```

Another:

```python
print(students["student2"]["marks"])
```

Output:

```text
78
```

---

# 28. Dictionary Containing List

A dictionary value can be a list.

```python
student = {
    "name": "Gaurav",
    "skills": ["Python", "React", "SQL"]
}

print(student["skills"])
```

Output:

```text
['Python', 'React', 'SQL']
```

Access a list item:

```python
print(student["skills"][0])
```

Output:

```text
Python
```

---

# 29. List of Dictionaries

This is a very common real-world data structure.

```python
students = [
    {"name": "Gaurav", "marks": 85},
    {"name": "Rahul", "marks": 78},
    {"name": "Amit", "marks": 92}
]
```

Access:

```python
print(students[0]["name"])
```

Output:

```text
Gaurav
```

Loop:

```python
for student in students:
    print(student["name"], student["marks"])
```

Output:

```text
Gaurav 85
Rahul 78
Amit 92
```

This structure is very common in JSON and API responses.

---

# 30. Dictionary Comprehension

## What?

Dictionary comprehension is a compact way to create dictionaries.

### Syntax

```python
{key: value for item in iterable}
```

Example:

```python
squares = {
    i: i ** 2
    for i in range(1, 6)
}

print(squares)
```

Output:

```text
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

---

# 31. Dictionary Comprehension with Condition

```python
even_squares = {
    i: i ** 2
    for i in range(1, 11)
    if i % 2 == 0
}

print(even_squares)
```

Output:

```text
{2: 4, 4: 16, 6: 36, 8: 64, 10: 100}
```

---

# 32. Create Dictionary from Two Lists

Use `zip()`.

```python
keys = ["name", "age", "city"]
values = ["Gaurav", 40, "Jaipur"]

student = dict(zip(keys, values))

print(student)
```

Output:

```text
{'name': 'Gaurav', 'age': 40, 'city': 'Jaipur'}
```

---

# 33. Dictionary Keys Must Be Hashable

Dictionary keys must be hashable.

Valid examples:

```python
data = {
    "name": "Gaurav",
    1: "One",
    (10, 20): "Point"
}
```

Invalid:

```python
data = {
    [1, 2]: "Numbers"
}
```

This raises:

```text
TypeError: unhashable type: 'list'
```

Lists cannot be dictionary keys because lists are mutable.

---

# 34. Dictionary Values Can Be Almost Anything

Values can be:

```python
data = {
    "name": "Gaurav",
    "marks": 85,
    "skills": ["Python", "React"],
    "address": {
        "city": "Jaipur"
    },
    "active": True,
    "data": None
}
```

Values can be strings, numbers, lists, dictionaries, booleans, `None`, and more.

---

# 35. Dictionary Length

```python
data = {
    "name": "Gaurav",
    "age": 40,
    "city": "Jaipur"
}

print(len(data))
```

Output:

```text
3
```

It counts key-value pairs.

---

# 36. Dictionary Comparison

Dictionaries can be compared for equality.

```python
a = {
    "name": "Gaurav",
    "age": 40
}

b = {
    "age": 40,
    "name": "Gaurav"
}

print(a == b)
```

Output:

```text
True
```

For equality, key-value content matters; insertion order does not make these two dictionaries unequal.

---

# 37. `setdefault()`

## What?

`setdefault()` returns the value of a key.

If the key does not exist, it inserts the key with a default value.

```python
student = {
    "name": "Gaurav"
}

age = student.setdefault("age", 40)

print(age)
print(student)
```

Output:

```text
40
{'name': 'Gaurav', 'age': 40}
```

If the key already exists, its existing value is returned and is not replaced.

```python
student = {
    "age": 40
}

result = student.setdefault("age", 50)

print(result)
print(student["age"])
```

Output:

```text
40
40
```

---

# 38. Real-Life Example — Product

```python
product = {
    "id": 101,
    "title": "Laptop",
    "price": 55000,
    "category": "Electronics",
    "in_stock": True
}

print(product["title"])
print(product["price"])
```

Output:

```text
Laptop
55000
```

Modify price:

```python
product["price"] = 52000
```

Add brand:

```python
product["brand"] = "Dell"
```

---

# 39. Real-Life Example — Employee

```python
employee = {
    "id": 101,
    "name": "Gaurav",
    "department": "IT",
    "skills": ["Python", "React", "SQL"],
    "experience": 10
}

for key, value in employee.items():
    print(f"{key}: {value}")
```

This produces a readable employee record.

---

# 40. Real-Life Example — Student Marks

```python
marks = {
    "Gaurav": 85,
    "Rahul": 78,
    "Amit": 92
}

print(marks["Gaurav"])
```

Find students with marks above 80:

```python
for name, mark in marks.items():
    if mark > 80:
        print(name, mark)
```

Output:

```text
Gaurav 85
Amit 92
```

---

# 41. Dictionary Methods Quick Table

| Method | Purpose |
|---|---|
| `get()` | Safely access a value |
| `keys()` | Get all keys |
| `values()` | Get all values |
| `items()` | Get key-value pairs |
| `update()` | Add/modify multiple pairs |
| `pop()` | Remove specified key |
| `popitem()` | Remove last inserted pair |
| `clear()` | Remove all pairs |
| `copy()` | Create shallow copy |
| `setdefault()` | Get key or insert default |
| `fromkeys()` | Create dictionary from keys |

---

# 42. Dictionary vs List

| Feature | Dictionary | List |
|---|---|---|
| Stores | Key-value pairs | Values |
| Access | By key | By index |
| Mutable | Yes | Yes |
| Duplicate keys | No | Not applicable |
| Duplicate values | Allowed | Allowed |
| Syntax | `{key: value}` | `[]` |
| Ordered | Insertion order preserved | Yes |
| `append()` | No | Yes |
| `keys()` | Yes | No |
| `values()` | Yes | No |
| `items()` | Yes | No |

---

# 43. Dictionary vs Set

Both use `{}` for non-empty collections, but their structures are different.

Set:

```python
numbers = {10, 20, 30}
```

Dictionary:

```python
student = {
    "name": "Gaurav",
    "age": 40
}
```

### Easy Rule

```text
{1, 2, 3}                 → Set
{"name": "Gaurav"}        → Dictionary
{}                        → Empty dictionary
set()                     → Empty set
```

---

# 44. Dictionary vs Tuple

| Feature | Dictionary | Tuple |
|---|---|---|
| Structure | Key-value | Ordered values |
| Mutable | Yes | No |
| Access | By key | By index |
| Duplicate keys | No | Not applicable |
| Syntax | `{key: value}` | `()` |
| Use | Records/mappings | Fixed sequence |

---

# 45. Common Mistakes

## Mistake 1 — Accessing Missing Key

```python
student = {"name": "Gaurav"}

print(student["age"])
```

Raises:

```text
KeyError
```

Safer:

```python
print(student.get("age"))
```

---

## Mistake 2 — Confusing Key and Value Membership

```python
student = {
    "name": "Gaurav",
    "age": 40
}
```

This checks keys:

```python
print("name" in student)
```

This checks values:

```python
print("Gaurav" in student.values())
```

---

## Mistake 3 — Using a List as a Key

Wrong:

```python
data = {
    [1, 2]: "Numbers"
}
```

Lists are unhashable.

Use a tuple when appropriate:

```python
data = {
    (1, 2): "Numbers"
}
```

---

## Mistake 4 — Expecting `pop()` Without Argument

For dictionaries:

```python
student.pop()
```

This is incorrect because `dict.pop()` requires a key.

To remove the last inserted pair:

```python
student.popitem()
```

---

# 46. Important Dictionary Flow

```text
Create Dictionary
       ↓
Key → Value
       ↓
Access
       ↓
Add / Modify
       ↓
Search
       ↓
Loop
       ↓
Update
       ↓
Remove
       ↓
Nested Data
       ↓
Comprehension
```

---

# Quick Revision

| Concept | Meaning |
|---|---|
| Dictionary | Mutable key-value collection |
| Key | Identifier used to access a value |
| Value | Data associated with a key |
| `[]` | Access by key |
| `get()` | Safe key access |
| `keys()` | All keys |
| `values()` | All values |
| `items()` | Key-value pairs |
| `update()` | Add/modify multiple pairs |
| `pop()` | Remove specified key |
| `popitem()` | Remove last inserted pair |
| `del` | Delete key-value pair |
| `clear()` | Empty dictionary |
| `copy()` | Shallow copy |
| `setdefault()` | Get value or insert default |
| `fromkeys()` | Create dictionary from keys |
| Dictionary comprehension | Compact dictionary creation |
| Nested dictionary | Dictionary inside dictionary |

---

# Key Points

- A dictionary stores data as key-value pairs.
- Dictionary keys must be unique.
- Dictionary keys must be hashable.
- Values can be duplicated.
- Values can contain different data types.
- Dictionaries are mutable.
- Modern Python dictionaries preserve insertion order.
- Access dictionary data using keys.
- `get()` avoids `KeyError` for missing keys.
- `keys()` returns keys.
- `values()` returns values.
- `items()` returns key-value pairs.
- `update()` adds or modifies multiple values.
- `pop()` removes a specified key.
- `popitem()` removes the last inserted pair.
- `clear()` removes all pairs.
- `setdefault()` can insert a default value when a key is missing.
- Nested dictionaries are useful for structured data.
- A list of dictionaries is commonly used for JSON/API-like data.
- Dictionary comprehension provides a compact way to create dictionaries.
- Dictionary keys cannot be mutable objects such as lists.

# One-Line Definition

> **Dictionary = A mutable collection that stores data in unique key-value pairs for efficient key-based access.**
