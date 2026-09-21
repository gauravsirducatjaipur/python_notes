# Python Notes — Sets

# 1. Set

## What?

A **set** is an unordered, mutable collection of **unique elements**.

Sets are commonly created using curly braces `{}`.

```python
numbers = {10, 20, 30, 40}

print(numbers)
```

Output:

```text
{10, 20, 30, 40}
```

A set automatically removes duplicate values.

```python
numbers = {10, 20, 10, 30, 20}

print(numbers)
```

Output:

```text
{10, 20, 30}
```

> **Note:** Set display order should not be relied upon.

---

## Why?

Sets are useful when:

- Duplicate values need to be removed.
- Fast membership checking is required.
- Mathematical set operations are required.
- Unique values need to be stored.

Real-life examples:

```text
Unique student IDs
Unique email addresses
Unique skills
Unique product categories
Unique website visitors
Common items between two groups
```

---

## When?

Use a set when:

- Uniqueness is important.
- Order/indexing is not required.
- You need union, intersection, difference, or symmetric difference.
- You frequently check whether a value exists.

---

## How?

Create a set using `{}` or `set()`.

```python
numbers = {10, 20, 30}
```

For an empty set, use:

```python
numbers = set()
```

Do **not** use:

```python
numbers = {}
```

because `{}` creates an empty dictionary.

---

# 2. Creating a Set

## Set of Numbers

```python
numbers = {10, 20, 30, 40}
```

## Set of Strings

```python
languages = {"Python", "Java", "JavaScript"}
```

## Mixed Set

```python
data = {10, "Python", True, 25.5}
```

A set can contain different hashable data types.

---

# 3. Duplicate Values

Sets automatically keep only unique values.

```python
numbers = {1, 2, 2, 3, 3, 3}

print(numbers)
```

Output contains:

```text
{1, 2, 3}
```

The exact display order is not guaranteed.

---

# 4. Empty Set

This is an important concept.

Wrong:

```python
items = {}

print(type(items))
```

Output:

```text
<class 'dict'>
```

Correct:

```python
items = set()

print(type(items))
```

Output:

```text
<class 'set'>
```

### Remember

```text
{}       → empty dictionary
set()    → empty set
```

---

# 5. Set Does Not Support Indexing

Sets are unordered collections, so you cannot access an item using an index.

```python
numbers = {10, 20, 30}

print(numbers[0])
```

This raises:

```text
TypeError
```

You should use membership checking or iteration instead.

```python
if 20 in numbers:
    print("Found")
```

---

# 6. Set is Mutable

A set can be changed after creation.

```python
numbers = {10, 20, 30}

numbers.add(40)

print(numbers)
```

Output contains:

```text
{10, 20, 30, 40}
```

However, the elements themselves must be hashable.

---

# 7. Adding One Item — `add()`

`add()` adds one element to a set.

```python
skills = {"Python", "Java"}

skills.add("React")

print(skills)
```

The set now contains:

```text
Python
Java
React
```

If the value already exists, the set remains unchanged.

```python
numbers = {10, 20, 30}

numbers.add(20)

print(numbers)
```

The result still contains only one `20`.

---

# 8. Adding Multiple Items — `update()`

`update()` adds multiple elements from an iterable.

```python
numbers = {1, 2, 3}

numbers.update([4, 5, 6])

print(numbers)
```

The set contains:

```text
{1, 2, 3, 4, 5, 6}
```

You can update from another set:

```python
a = {1, 2}
b = {3, 4}

a.update(b)

print(a)
```

---

# 9. `add()` vs `update()`

| Method | Purpose |
|---|---|
| `add()` | Adds one element |
| `update()` | Adds multiple elements |

Example:

```python
numbers.add(10)
```

One element.

```python
numbers.update([10, 20, 30])
```

Multiple elements.

---

# 10. Remove Item — `remove()`

`remove()` deletes a specified element.

```python
numbers = {10, 20, 30}

numbers.remove(20)

print(numbers)
```

Output contains:

```text
{10, 30}
```

If the element does not exist, `remove()` raises `KeyError`.

```python
numbers.remove(100)
```

---

# 11. Remove Item — `discard()`

`discard()` also removes an element.

The important difference is that `discard()` does not raise an error if the element is missing.

```python
numbers = {10, 20, 30}

numbers.discard(20)

print(numbers)
```

If the value does not exist:

```python
numbers.discard(100)
```

No error is raised.

### `remove()` vs `discard()`

```text
remove()  → error if item does not exist
discard() → no error if item does not exist
```

---

# 12. `pop()`

`pop()` removes and returns an arbitrary element from a set.

```python
numbers = {10, 20, 30}

value = numbers.pop()

print(value)
print(numbers)
```

Because sets are unordered, do not assume which element will be removed.

> Do not use `set.pop()` when you need to remove a specific value.

---

# 13. Clear a Set — `clear()`

`clear()` removes all elements.

```python
numbers = {10, 20, 30}

numbers.clear()

print(numbers)
```

Output:

```text
set()
```

---

# 14. Set Length — `len()`

`len()` returns the number of unique elements.

```python
numbers = {10, 20, 30, 40}

print(len(numbers))
```

Output:

```text
4
```

Duplicates are not counted.

```python
numbers = {10, 10, 20, 20, 30}

print(len(numbers))
```

Output:

```text
3
```

---

# 15. Membership — `in`

Sets are especially useful for membership checking.

```python
skills = {"Python", "Java", "React"}

print("Python" in skills)
print("PHP" in skills)
```

Output:

```text
True
False
```

Use `not in`:

```python
print("PHP" not in skills)
```

Output:

```text
True
```

---

# 16. Set Union

## What?

Union combines all unique elements from two or more sets.

Use:

```python
|
```

or:

```python
union()
```

Example:

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)
```

Result contains:

```text
{1, 2, 3, 4, 5}
```

Using method:

```python
print(a.union(b))
```

---

# 17. Set Intersection

## What?

Intersection returns elements common to both sets.

Use:

```python
&
```

or:

```python
intersection()
```

Example:

```python
a = {1, 2, 3}
b = {2, 3, 4}

print(a & b)
```

Result:

```text
{2, 3}
```

Using method:

```python
print(a.intersection(b))
```

---

# 18. Set Difference

## What?

Difference returns elements present in the first set but not in the second.

Use:

```python
-
```

or:

```python
difference()
```

Example:

```python
a = {1, 2, 3}
b = {2, 3, 4}

print(a - b)
```

Result:

```text
{1}
```

Reverse direction:

```python
print(b - a)
```

Result:

```text
{4}
```

### Important

Set difference is **directional**.

```text
A - B ≠ B - A
```

---

# 19. Symmetric Difference

## What?

Symmetric difference returns elements that are in either set, but not in both.

Use:

```python
^
```

or:

```python
symmetric_difference()
```

Example:

```python
a = {1, 2, 3}
b = {2, 3, 4}

print(a ^ b)
```

Result:

```text
{1, 4}
```

Common elements `2` and `3` are removed.

---

# 20. Set Operations Summary

Given:

```python
A = {1, 2, 3}
B = {3, 4, 5}
```

| Operation | Operator | Result |
|---|---|---|
| Union | `A \| B` | `{1,2,3,4,5}` |
| Intersection | `A & B` | `{3}` |
| Difference | `A - B` | `{1,2}` |
| Reverse Difference | `B - A` | `{4,5}` |
| Symmetric Difference | `A ^ B` | `{1,2,4,5}` |

---

# 21. Union with Multiple Sets

```python
a = {1, 2}
b = {2, 3}
c = {3, 4}

result = a | b | c

print(result)
```

Result contains:

```text
{1, 2, 3, 4}
```

---

# 22. Intersection with Multiple Sets

```python
a = {1, 2, 3, 4}
b = {2, 3, 4, 5}
c = {3, 4, 5, 6}

result = a & b & c

print(result)
```

Result:

```text
{3, 4}
```

---

# 23. Subset — `issubset()`

## What?

A set is a subset if all its elements are present in another set.

```python
a = {1, 2}
b = {1, 2, 3, 4}

print(a.issubset(b))
```

Output:

```text
True
```

Operator:

```python
print(a <= b)
```

Output:

```text
True
```

---

# 24. Superset — `issuperset()`

A set is a superset if it contains all elements of another set.

```python
a = {1, 2, 3, 4}
b = {1, 2}

print(a.issuperset(b))
```

Output:

```text
True
```

Operator:

```python
print(a >= b)
```

Output:

```text
True
```

---

# 25. Disjoint Sets

## What?

Two sets are disjoint when they have no common elements.

```python
a = {1, 2, 3}
b = {4, 5, 6}

print(a.isdisjoint(b))
```

Output:

```text
True
```

If they have a common value:

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a.isdisjoint(b))
```

Output:

```text
False
```

---

# 26. Set Relationships

```text
Subset
A ⊆ B

Superset
B ⊇ A

Disjoint
A ∩ B = ∅
```

Python methods:

```python
issubset()
issuperset()
isdisjoint()
```

---

# 27. Set Assignment vs Copy

Consider:

```python
a = {1, 2, 3}
b = a

b.add(4)

print(a)
print(b)
```

Both refer to the same set object.

Use `copy()` when you need a separate shallow copy.

```python
a = {1, 2, 3}
b = a.copy()

b.add(4)

print(a)
print(b)
```

Output contains:

```text
a → {1, 2, 3}
b → {1, 2, 3, 4}
```

---

# 28. Copy a Set — `copy()`

```python
numbers = {10, 20, 30}

new_numbers = numbers.copy()

print(new_numbers)
```

The new set contains the same elements but is a separate set object.

---

# 29. Convert List to Set

This is one of the most useful applications of sets.

```python
numbers = [1, 2, 2, 3, 3, 4]

unique_numbers = set(numbers)

print(unique_numbers)
```

The result contains only unique values:

```text
{1, 2, 3, 4}
```

---

# 30. Remove Duplicates from a List

```python
numbers = [10, 20, 10, 30, 20, 40]

unique = list(set(numbers))

print(unique)
```

This removes duplicates.

> The resulting order should not be relied upon.

If order must be preserved, use a different approach, for example:

```python
numbers = [10, 20, 10, 30, 20, 40]

unique = list(dict.fromkeys(numbers))

print(unique)
```

Output:

```text
[10, 20, 30, 40]
```

---

# 31. Convert Set to List

```python
numbers = {10, 20, 30}

result = list(numbers)

print(result)
```

The list order is not guaranteed to follow the set's conceptual order.

---

# 32. Set with `for` Loop

```python
skills = {"Python", "Java", "React"}

for skill in skills:
    print(skill)
```

The elements can be produced in an order that should not be assumed.

---

# 33. Set Comprehension

## What?

Set comprehension is a compact way to create a set.

### Syntax

```python
{expression for item in iterable}
```

Example:

```python
numbers = {i for i in range(1, 6)}

print(numbers)
```

Result contains:

```text
{1, 2, 3, 4, 5}
```

---

# 34. Set Comprehension with Condition

```python
even_numbers = {
    i for i in range(1, 11)
    if i % 2 == 0
}

print(even_numbers)
```

Result contains:

```text
{2, 4, 6, 8, 10}
```

---

# 35. Set Comprehension for Unique Values

```python
numbers = [1, 2, 2, 3, 3, 4]

unique_squares = {number ** 2 for number in numbers}

print(unique_squares)
```

Result contains:

```text
{1, 4, 9, 16}
```

Duplicate squared results are automatically removed.

---

# 36. Frozen Set — `frozenset`

## What?

A `frozenset` is an **immutable set**.

```python
numbers = frozenset([10, 20, 30])

print(numbers)
```

It cannot be changed using methods such as `add()` or `remove()`.

```python
numbers.add(40)
```

This raises:

```text
AttributeError
```

---

## Why?

`frozenset` is useful when:

- Set data should not change.
- An immutable set is required.
- The set needs to be used as a dictionary key.
- The set needs to be an element of another set.

Example:

```python
permissions = frozenset({"read", "write"})

print(permissions)
```

---

# 37. Hashable Elements in a Set

Set elements must be **hashable**.

Common hashable values:

```python
numbers = {10, 20}
names = {"Gaurav", "Rahul"}
data = {(1, 2), (3, 4)}
```

A list cannot be directly stored as a set element:

```python
data = {[1, 2], [3, 4]}
```

This raises:

```text
TypeError: unhashable type: 'list'
```

A tuple of hashable values can be stored:

```python
data = {(1, 2), (3, 4)}

print(data)
```

---

# 38. Set vs List

| Feature | List | Set |
|---|---|---|
| Ordered | Yes | No guaranteed order |
| Mutable | Yes | Yes |
| Duplicates | Allowed | Not allowed |
| Indexing | Yes | No |
| Slicing | Yes | No |
| `append()` | Yes | No |
| `add()` | No | Yes |
| `remove()` | Yes | Yes |
| Mathematical operations | No | Yes |
| Membership checking | Yes | Very useful |
| Syntax | `[]` | `{}` |

---

# 39. Set vs Tuple

| Feature | Set | Tuple |
|---|---|---|
| Ordered | No guaranteed order | Yes |
| Mutable | Yes | No |
| Duplicates | No | Yes |
| Indexing | No | Yes |
| Slicing | No | Yes |
| `add()` | Yes | No |
| `count()` | No | Yes |
| `index()` | No | Yes |
| Set operations | Yes | No |
| Syntax | `{}` | `()` |

---

# 40. Set vs Dictionary

Important distinction:

```python
data = {}
```

This is a dictionary.

A set needs:

```python
data = set()
```

A non-empty set:

```python
data = {1, 2, 3}
```

A dictionary:

```python
data = {
    "name": "Gaurav",
    "age": 40
}
```

### Easy Rule

```text
{} → empty dictionary
{1, 2, 3} → set
{"name": "Gaurav"} → dictionary
set() → empty set
```

---

# 41. Real-Life Example — Unique Skills

```python
skills = [
    "Python",
    "React",
    "Python",
    "JavaScript",
    "React"
]

unique_skills = set(skills)

print(unique_skills)
```

Duplicates are removed.

---

# 42. Real-Life Example — Common Skills

```python
student1 = {"Python", "Java", "SQL"}
student2 = {"Python", "React", "SQL"}

common = student1 & student2

print(common)
```

Result:

```text
{'Python', 'SQL'}
```

---

# 43. Real-Life Example — All Skills

```python
student1 = {"Python", "Java", "SQL"}
student2 = {"Python", "React", "SQL"}

all_skills = student1 | student2

print(all_skills)
```

Result contains:

```text
Python
Java
SQL
React
```

---

# 44. Real-Life Example — Skills Only Student 1 Has

```python
student1 = {"Python", "Java", "SQL"}
student2 = {"Python", "React", "SQL"}

only_student1 = student1 - student2

print(only_student1)
```

Result:

```text
{'Java'}
```

---

# 45. Real-Life Example — Unique Visitors

```python
visitors = [
    "user101",
    "user102",
    "user101",
    "user103",
    "user102"
]

unique_visitors = set(visitors)

print(len(unique_visitors))
```

Output:

```text
3
```

---

# 46. Common Mistakes

## Mistake 1 — Using `{}` for Empty Set

Wrong:

```python
data = {}
```

This creates a dictionary.

Correct:

```python
data = set()
```

---

## Mistake 2 — Trying to Access by Index

Wrong:

```python
numbers = {10, 20, 30}

print(numbers[0])
```

Sets do not support indexing.

Correct:

```python
if 10 in numbers:
    print("Found")
```

---

## Mistake 3 — Expecting `pop()` to Remove a Specific Item

For sets:

```python
numbers.pop()
```

removes an arbitrary element.

To remove a specific value:

```python
numbers.remove(20)
```

or safely:

```python
numbers.discard(20)
```

---

## Mistake 4 — Putting a List Inside a Set

Wrong:

```python
data = {[1, 2], [3, 4]}
```

Lists are unhashable.

Use tuples if appropriate:

```python
data = {(1, 2), (3, 4)}
```

---

# 47. Important Set Flow

```text
Create Set
    ↓
Automatic Duplicate Removal
    ↓
Add / Update
    ↓
Remove / Discard
    ↓
Membership Checking
    ↓
Union / Intersection
    ↓
Difference
    ↓
Subset / Superset
    ↓
Comprehension
    ↓
Optional Conversion
```

---

# Quick Revision

| Concept | Meaning |
|---|---|
| Set | Mutable collection of unique elements |
| `{}` | Empty dictionary, not empty set |
| `set()` | Creates empty set |
| `add()` | Add one element |
| `update()` | Add multiple elements |
| `remove()` | Remove specific element; error if missing |
| `discard()` | Remove specific element; no error if missing |
| `pop()` | Remove arbitrary element |
| `clear()` | Remove all elements |
| `copy()` | Create shallow copy |
| `len()` | Number of unique elements |
| `in` | Membership checking |
| Union | Combine unique elements |
| Intersection | Common elements |
| Difference | Elements only in first set |
| Symmetric Difference | Elements in either set but not both |
| `issubset()` | Check subset |
| `issuperset()` | Check superset |
| `isdisjoint()` | Check no common elements |
| Set comprehension | Compact set creation |
| `frozenset()` | Immutable set |

---

# Key Points

- A set stores unique elements.
- Sets are mutable.
- Sets do not provide index-based access.
- Set iteration order should not be relied upon.
- Duplicate values are automatically removed.
- `{}` creates an empty dictionary.
- `set()` creates an empty set.
- `add()` adds one element.
- `update()` adds multiple elements.
- `remove()` raises an error if the item is missing.
- `discard()` does not raise an error if the item is missing.
- `pop()` removes an arbitrary element.
- `union()` combines unique elements.
- `intersection()` finds common elements.
- `difference()` finds elements unique to the first set.
- `symmetric_difference()` finds elements present in either set but not both.
- `issubset()` and `issuperset()` check set relationships.
- Sets are excellent for removing duplicates.
- Set elements must be hashable.
- `frozenset` is an immutable set.
- Set comprehension creates sets in a compact way.

# One-Line Definition

> **Set = An unordered collection of unique elements used for membership checking, duplicate removal, and mathematical set operations.**
