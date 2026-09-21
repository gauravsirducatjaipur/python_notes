# Python Notes — Nested Loop

# 1. Nested Loop

## What?

A **nested loop** is a loop placed inside another loop.

In simple words:

> **Loop ke andar ek aur loop = Nested Loop**

Example:

```python
for i in range(3):
    for j in range(3):
        print(i, j)
```

Here:

```text
Outer loop → for i
Inner loop → for j
```

The inner loop runs completely for every iteration of the outer loop.

---

## Why?

Nested loops are useful when data or a problem has **multiple levels**.

Common examples:

- Rows and columns
- Matrix operations
- Tables
- Patterns
- 2D lists
- Comparing every item with every other item
- Processing nested data
- Grid-based problems

For example, a classroom can be represented as:

```text
Row 1 → Seat 1, Seat 2, Seat 3
Row 2 → Seat 1, Seat 2, Seat 3
Row 3 → Seat 1, Seat 2, Seat 3
```

This naturally requires two loops.

---

## When?

Use nested loops when you need to repeat one process **inside another repeated process**.

Examples:

```text
For every row:
    process every column

For every student:
    process every subject

For every product:
    compare with every other product
```

---

## How?

Basic syntax:

```python
for outer_variable in outer_sequence:

    for inner_variable in inner_sequence:
        statement
```

Example:

```python
for i in range(3):
    for j in range(3):
        print(i, j)
```

Output:

```text
0 0
0 1
0 2
1 0
1 1
1 2
2 0
2 1
2 2
```

---

# 2. Outer Loop and Inner Loop

Consider:

```python
for i in range(3):
    for j in range(3):
        print(i, j)
```

There are two loops.

### Outer Loop

```python
for i in range(3):
```

Controls the outer repetition.

### Inner Loop

```python
for j in range(3):
```

Runs completely for every iteration of the outer loop.

---

# 3. How Nested Loop Executes

Consider:

```python
for i in range(2):
    for j in range(3):
        print(i, j)
```

### Step-by-Step

### Outer loop: `i = 0`

Inner loop runs:

```text
j = 0 → 0 0
j = 1 → 0 1
j = 2 → 0 2
```

### Outer loop: `i = 1`

Inner loop runs again:

```text
j = 0 → 1 0
j = 1 → 1 1
j = 2 → 1 2
```

Final output:

```text
0 0
0 1
0 2
1 0
1 1
1 2
```

### Important Rule

> **For every one iteration of the outer loop, the inner loop completes all of its iterations.**

---

# 4. Nested Loop Flow

Example:

```python
for i in range(3):
    for j in range(2):
        print(i, j)
```

Flow:

```text
Outer Loop
    ↓
i = 0
    ↓
Inner Loop
j = 0
j = 1
    ↓
Inner Loop Ends
    ↓
i = 1
    ↓
Inner Loop
j = 0
j = 1
    ↓
Inner Loop Ends
    ↓
i = 2
    ↓
Inner Loop
j = 0
j = 1
    ↓
Inner Loop Ends
    ↓
Outer Loop Ends
```

---

# 5. Nested `for` Loop

The most common form of nested loop is a `for` loop inside another `for` loop.

```python
for i in range(3):
    for j in range(3):
        print(i, j)
```

Output:

```text
0 0
0 1
0 2
1 0
1 1
1 2
2 0
2 1
2 2
```

---

# 6. Nested `while` Loop

A `while` loop can also be nested.

```python
i = 1

while i <= 3:
    j = 1

    while j <= 3:
        print(i, j)
        j += 1

    i += 1
```

Output:

```text
1 1
1 2
1 3
2 1
2 2
2 3
3 1
3 2
3 3
```

Important:

> The inner `while` loop must update its control variable to avoid an infinite loop.

---

# 7. Nested `for` + `while`

Different loop types can also be nested.

Example:

```python
for i in range(3):
    j = 1

    while j <= 2:
        print(i, j)
        j += 1
```

Output:

```text
0 1
0 2
1 1
1 2
2 1
2 2
```

You can also put a `for` loop inside a `while` loop.

---

# 8. Nested Loop with List

Consider a list containing multiple lists:

```python
numbers = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
```

This is a **2D list**.

To access every element:

```python
for row in numbers:
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
7
8
9
```

Here:

```text
Outer loop → each row
Inner loop → each value inside the row
```

---

# 9. Nested Loop with Rows and Columns

```python
matrix = [
    [10, 20, 30],
    [40, 50, 60],
    [70, 80, 90]
]

for row in matrix:
    for value in row:
        print(value, end=" ")
    print()
```

Output:

```text
10 20 30
40 50 60
70 80 90
```

This is one of the most important practical uses of nested loops.

---

# 10. Pattern Printing

Nested loops are commonly used for pattern programs.

## Square Pattern

```python
for i in range(3):
    for j in range(3):
        print("*", end=" ")
    print()
```

Output:

```text
* * *
* * *
* * *
```

### How It Works

Outer loop:

```python
for i in range(3):
```

controls the **rows**.

Inner loop:

```python
for j in range(3):
```

controls the **columns**.

So:

```text
3 rows × 3 columns
```

---

# 11. Increasing Star Pattern

```python
for i in range(1, 5):
    for j in range(i):
        print("*", end=" ")
    print()
```

Output:

```text
*
* *
* * *
* * * *
```

### Logic

When:

```text
i = 1 → 1 star
i = 2 → 2 stars
i = 3 → 3 stars
i = 4 → 4 stars
```

The outer loop controls rows.

The inner loop controls the number of stars in each row.

---

# 12. Decreasing Star Pattern

```python
for i in range(4, 0, -1):
    for j in range(i):
        print("*", end=" ")
    print()
```

Output:

```text
* * * *
* * *
* *
*
```

---

# 13. Number Pattern

```python
for i in range(1, 5):
    for j in range(1, i + 1):
        print(j, end=" ")
    print()
```

Output:

```text
1
1 2
1 2 3
1 2 3 4
```

---

# 14. Same Number Pattern

```python
for i in range(1, 5):
    for j in range(i):
        print(i, end=" ")
    print()
```

Output:

```text
1
2 2
3 3 3
4 4 4 4
```

---

# 15. Multiplication Table Using Nested Loop

We can generate multiple multiplication tables.

```python
for i in range(2, 5):
    print("Table of", i)

    for j in range(1, 11):
        print(i, "x", j, "=", i * j)

    print()
```

Output:

```text
Table of 2
2 x 1 = 2
2 x 2 = 4
...
2 x 10 = 20

Table of 3
3 x 1 = 3
...
3 x 10 = 30

Table of 4
4 x 1 = 4
...
4 x 10 = 40
```

Here:

```text
Outer loop → table number
Inner loop → multiplication from 1 to 10
```

---

# 16. `break` in Nested Loop

`break` affects the **nearest loop** in which it appears.

Example:

```python
for i in range(3):
    for j in range(3):
        if j == 1:
            break

        print(i, j)
```

Output:

```text
0 0
1 0
2 0
```

When `j == 1`, the inner loop stops.

The outer loop continues.

### Important

```text
break inside inner loop
        ↓
Stops inner loop
        ↓
Outer loop continues
```

---

# 17. `continue` in Nested Loop

`continue` skips the current iteration of the **nearest loop**.

```python
for i in range(3):
    for j in range(3):
        if j == 1:
            continue

        print(i, j)
```

Output:

```text
0 0
0 2
1 0
1 2
2 0
2 2
```

Only the inner-loop iteration where `j == 1` is skipped.

---

# 18. Nested Loop with Conditions

Nested loops can contain conditional statements.

```python
for i in range(1, 4):
    for j in range(1, 4):

        if i == j:
            print("Same", i, j)
```

Output:

```text
Same 1 1
Same 2 2
Same 3 3
```

---

# 19. Comparing Every Item with Every Item

Nested loops can compare every element with every other element.

```python
numbers = [1, 2, 3]

for x in numbers:
    for y in numbers:
        print(x, y)
```

Output:

```text
1 1
1 2
1 3
2 1
2 2
2 3
3 1
3 2
3 3
```

This concept is useful in:

- Pair generation
- Comparisons
- Searching
- Algorithms
- Data processing

---

# 20. Nested Loop and Number of Iterations

Suppose:

```python
for i in range(3):
    for j in range(4):
        print(i, j)
```

Outer loop runs:

```text
3 times
```

Inner loop runs:

```text
4 times for every outer iteration
```

Total:

```text
3 × 4 = 12
```

So the inner statement executes **12 times**.

---

# 21. Three Nested Loops

Loops can technically be nested more than two levels.

Example:

```python
for i in range(2):
    for j in range(2):
        for k in range(2):
            print(i, j, k)
```

Output:

```text
0 0 0
0 0 1
0 1 0
0 1 1
1 0 0
1 0 1
1 1 0
1 1 1
```

Total iterations:

```text
2 × 2 × 2 = 8
```

However, too many nested loops can make code difficult to understand and may be inefficient.

---

# 22. Nested Loop vs Single Loop

### Single Loop

```python
numbers = [1, 2, 3]

for number in numbers:
    print(number)
```

Used when one level of iteration is enough.

### Nested Loop

```python
numbers = [
    [1, 2],
    [3, 4]
]

for row in numbers:
    for number in row:
        print(number)
```

Used when data has multiple levels.

---

# 23. Real-World Example — Students and Subjects

Suppose we have students and subjects:

```python
students = ["Gaurav", "Rahul", "Amit"]
subjects = ["Python", "JavaScript", "SQL"]
```

We can process every student with every subject:

```python
for student in students:
    for subject in subjects:
        print(student, "->", subject)
```

Output:

```text
Gaurav -> Python
Gaurav -> JavaScript
Gaurav -> SQL
Rahul -> Python
Rahul -> JavaScript
Rahul -> SQL
Amit -> Python
Amit -> JavaScript
Amit -> SQL
```

---

# 24. Real-World Example — Seating Arrangement

Suppose there are 3 rows and 4 seats per row:

```python
for row in range(1, 4):
    for seat in range(1, 5):
        print("Row", row, "Seat", seat)
```

Output:

```text
Row 1 Seat 1
Row 1 Seat 2
Row 1 Seat 3
Row 1 Seat 4
Row 2 Seat 1
Row 2 Seat 2
Row 2 Seat 3
Row 2 Seat 4
Row 3 Seat 1
Row 3 Seat 2
Row 3 Seat 3
Row 3 Seat 4
```

Total seats:

```text
3 × 4 = 12
```

---

# 25. Common Mistakes

## Mistake 1 — Wrong Indentation

Wrong:

```python
for i in range(3):
for j in range(3):
    print(i, j)
```

Correct:

```python
for i in range(3):
    for j in range(3):
        print(i, j)
```

---

## Mistake 2 — Forgetting `print()` for New Line

Pattern:

```python
for i in range(3):
    for j in range(3):
        print("*", end=" ")
```

Output:

```text
* * * * * * * * *
```

To create rows:

```python
for i in range(3):
    for j in range(3):
        print("*", end=" ")
    print()
```

Output:

```text
* * *
* * *
* * *
```

---

## Mistake 3 — Infinite Nested `while`

Wrong:

```python
i = 1

while i <= 3:
    j = 1

    while j <= 3:
        print(i, j)
```

`j` never changes, so the inner loop becomes infinite.

Correct:

```python
i = 1

while i <= 3:
    j = 1

    while j <= 3:
        print(i, j)
        j += 1

    i += 1
```

---

# 26. Important Concept — Outer vs Inner Loop

Remember this simple rule:

```text
Outer Loop
    ↓
Controls larger/repeated groups

Inner Loop
    ↓
Processes each item inside that group
```

For a matrix:

```text
Outer loop → Rows
Inner loop → Columns
```

For a multiplication table:

```text
Outer loop → Table number
Inner loop → Multipliers
```

For a pattern:

```text
Outer loop → Rows
Inner loop → Characters/numbers in each row
```

---

# Quick Revision

| Concept | Meaning |
|---|---|
| Nested Loop | Loop inside another loop |
| Outer Loop | Controls outer repetition |
| Inner Loop | Runs completely for each outer iteration |
| Nested `for` | `for` inside `for` |
| Nested `while` | `while` inside `while` |
| `break` | Stops nearest loop |
| `continue` | Skips current iteration of nearest loop |
| 2D List | Common use of nested loops |
| Pattern Printing | Common practice of nested loops |

# Important Formula

If:

```python
for i in range(m):
    for j in range(n):
        statement
```

Then approximately:

```text
Total executions = m × n
```

Example:

```python
for i in range(5):
    for j in range(4):
        print(i, j)
```

Total:

```text
5 × 4 = 20
```

---

# Key Points to Remember

- A nested loop is a loop inside another loop.
- The outer loop controls the larger repetition.
- The inner loop completes all its iterations for every outer iteration.
- Nested loops are commonly used for rows/columns and 2D data.
- They are heavily used in pattern-printing programs.
- `break` inside the inner loop normally stops only the inner loop.
- `continue` inside the inner loop normally affects only the current inner iteration.
- Indentation is essential.
- Too many nested loops can make code complex and inefficient.
- For `m × n` loops, the inner statement executes approximately `m × n` times.

# One-Line Definition

> **Nested Loop = A loop placed inside another loop, where the inner loop executes completely for each iteration of the outer loop.**
