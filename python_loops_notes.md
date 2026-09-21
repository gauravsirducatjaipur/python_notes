# Python Notes — Loops

# 1. Loop

## What?

A **loop** is used to execute a block of code repeatedly.

Instead of writing the same code multiple times, we can use a loop.

### Without Loop

```python
print("Hello")
print("Hello")
print("Hello")
print("Hello")
print("Hello")
```

### With Loop

```python
for i in range(5):
    print("Hello")
```

Output:

```text
Hello
Hello
Hello
Hello
Hello
```

---

## Why?

Loops are used when the same task needs to be performed repeatedly.

For example:

- Print numbers from 1 to 100
- Display all students
- Process products
- Calculate totals
- Read list items
- Repeat a task until a condition becomes false
- Process records from a dataset

---

## When?

Use a loop when you know that some code needs to execute repeatedly.

Examples:

```text
Repeat 10 times
Read every item from a list
Print numbers from 1 to 100
Keep asking until valid input is received
```

---

## How?

Python mainly provides two types of loops:

```text
1. for loop
2. while loop
```

Python also supports:

```text
nested loops
break
continue
pass
```

---

# 2. `for` Loop

## What?

A `for` loop is used to iterate over a sequence or other iterable object.

Examples of iterables:

```text
String
List
Tuple
Set
Dictionary
Range
```

## Why?

Use `for` when you want to process each item of a collection or repeat something for a known sequence of values.

## When?

Common situations:

- Loop through a list
- Loop through a string
- Repeat a fixed number of times
- Process dictionary keys/values
- Process records

## How?

### Syntax

```python
for variable in iterable:
    statement
```

### Example

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

---

# 3. `for` Loop with String

A string is iterable, so we can process each character.

```python
name = "Python"

for character in name:
    print(character)
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

# 4. `for` Loop with List

```python
fruits = ["Apple", "Banana", "Mango"]

for fruit in fruits:
    print(fruit)
```

Output:

```text
Apple
Banana
Mango
```

The loop takes one item at a time.

```text
Apple
   ↓
Banana
   ↓
Mango
```

---

# 5. `range()` Function

## What?

`range()` generates a sequence of numbers.

It is commonly used with `for` loops.

## Why?

It makes it easy to repeat a block a specific number of times or iterate over a sequence of integers.

## How?

### `range(stop)`

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

Important:

> The `stop` value is not included.

So:

```python
range(5)
```

means:

```text
0, 1, 2, 3, 4
```

---

# 6. `range(start, stop)`

```python
for i in range(1, 6):
    print(i)
```

Output:

```text
1
2
3
4
5
```

Here:

```text
start = 1
stop = 6
```

The stop value `6` is excluded.

---

# 7. `range(start, stop, step)`

```python
for i in range(1, 11, 2):
    print(i)
```

Output:

```text
1
3
5
7
9
```

Here:

```text
start = 1
stop = 11
step = 2
```

The loop increases by `2`.

### Decreasing Sequence

```python
for i in range(10, 0, -1):
    print(i)
```

Output:

```text
10
9
8
7
6
5
4
3
2
1
```

---

# 8. `while` Loop

## What?

A `while` loop repeatedly executes a block of code **as long as its condition is `True`**.

## Why?

Use `while` when repetition depends on a condition.

## When?

It is useful when the number of repetitions is not necessarily known in advance.

Examples:

- Keep asking for a password until it is correct
- Repeat until a user chooses Exit
- Continue while a condition remains true
- Process data until a condition changes

## How?

### Syntax

```python
while condition:
    statement
```

### Example

```python
i = 1

while i <= 5:
    print(i)
    i += 1
```

Output:

```text
1
2
3
4
5
```

---

# 9. How `while` Loop Works

Consider:

```python
i = 1

while i <= 3:
    print(i)
    i += 1
```

Flow:

```text
i = 1
   ↓
i <= 3 ?
   ↓ Yes
print(i)
   ↓
i += 1
   ↓
Check condition again
   ↓
...
   ↓
i <= 3 ? → False
   ↓
Loop ends
```

---

# 10. Infinite Loop

## What?

An **infinite loop** is a loop that never becomes `False`.

Example:

```python
while True:
    print("Hello")
```

This continues indefinitely unless the loop is stopped.

Another common mistake:

```python
i = 1

while i <= 5:
    print(i)
```

Here `i` never changes, so the condition remains `True`.

Correct:

```python
i = 1

while i <= 5:
    print(i)
    i += 1
```

---

# 11. `break`

## What?

`break` immediately terminates the loop.

## Why?

Use `break` when you want to stop the loop before it naturally finishes.

## When?

Examples:

- Stop searching after finding an item
- Exit a menu
- Stop when a specific condition occurs

## How?

```python
for i in range(1, 10):
    if i == 5:
        break

    print(i)
```

Output:

```text
1
2
3
4
```

When `i == 5`, `break` terminates the loop.

---

# 12. `continue`

## What?

`continue` skips the current iteration and moves to the next iteration.

## Why?

Use it when you want to skip specific values or cases but continue the loop.

## How?

```python
for i in range(1, 6):
    if i == 3:
        continue

    print(i)
```

Output:

```text
1
2
4
5
```

The iteration for `3` is skipped.

---

# 13. `pass`

## What?

`pass` is a placeholder statement that does nothing.

## Why?

It is useful when Python requires a statement syntactically, but you do not want to execute any code yet.

## Example

```python
for i in range(5):
    pass
```

Nothing is printed.

### Example

```python
for i in range(5):
    if i == 3:
        pass
    else:
        print(i)
```

Output:

```text
0
1
2
4
```

Important:

> `pass` does not skip the iteration.

For skipping an iteration, use `continue`.

---

# 14. `break` vs `continue` vs `pass`

| Statement | Purpose |
|---|---|
| `break` | Terminates the entire loop |
| `continue` | Skips current iteration |
| `pass` | Does nothing; placeholder |

### Easy Way to Remember

```text
break
↓
Stop the loop

continue
↓
Skip this iteration

pass
↓
Do nothing
```

---

# 15. Nested Loop

## What?

A **nested loop** means a loop inside another loop.

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

For every one iteration of the outer loop, the inner loop completes all its iterations.

---

# 16. Nested Loop Example — Pattern

```python
for i in range(1, 4):
    for j in range(1, 4):
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

# 17. Loop with `else`

Python allows `else` with loops.

## `for...else`

```python
for i in range(5):
    print(i)
else:
    print("Loop completed")
```

Output:

```text
0
1
2
3
4
Loop completed
```

The `else` block executes when the loop finishes normally.

---

# 18. `for...else` with `break`

If the loop is terminated by `break`, the loop's `else` block does not execute.

```python
for i in range(5):
    if i == 3:
        break

    print(i)
else:
    print("Loop completed")
```

Output:

```text
0
1
2
```

The `else` block is skipped because `break` terminated the loop.

---

# 19. `while...else`

`while` loops can also have an `else`.

```python
i = 1

while i <= 3:
    print(i)
    i += 1
else:
    print("Loop completed")
```

Output:

```text
1
2
3
Loop completed
```

If `break` terminates the loop, the `else` block does not run.

---

# 20. Loop Through a Dictionary

## Keys

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

## Values

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

## Keys and Values

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

# 21. Loop Through a Set

```python
numbers = {10, 20, 30}

for number in numbers:
    print(number)
```

The values are processed one at a time.

Remember:

> A set is unordered, so do not rely on a particular output order.

---

# 22. Loop Through a Tuple

```python
numbers = (10, 20, 30)

for number in numbers:
    print(number)
```

Output:

```text
10
20
30
```

---

# 23. `for` vs `while`

| Feature | `for` | `while` |
|---|---|---|
| Main use | Iterate over iterable | Repeat while condition is true |
| Common with | List, string, range, tuple, dict | Conditions |
| Number of iterations | Often known/sequence-based | Often condition-based |
| Example | `for x in items:` | `while x < 10:` |

### Easy Rule

```text
for
↓
"Har item ke liye"

while
↓
"Jab tak condition true hai"
```

---

# 24. Practical Example — Sum of Numbers

```python
total = 0

for i in range(1, 6):
    total += i

print(total)
```

Output:

```text
15
```

Calculation:

```text
1 + 2 + 3 + 4 + 5 = 15
```

---

# 25. Practical Example — Even Numbers

```python
for i in range(1, 11):
    if i % 2 == 0:
        print(i)
```

Output:

```text
2
4
6
8
10
```

---

# 26. Practical Example — Search in List

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

for fruit in fruits:
    if fruit == "Mango":
        print("Mango found")
        break
```

Output:

```text
Mango found
```

`break` stops the loop after finding the required item.

---

# 27. Practical Example — Skip Odd Numbers

```python
for i in range(1, 11):
    if i % 2 != 0:
        continue

    print(i)
```

Output:

```text
2
4
6
8
10
```

Here `continue` skips odd numbers.

---

# 28. Common Mistakes

## Mistake 1 — Forgetting Colon

Wrong:

```python
for i in range(5)
    print(i)
```

Correct:

```python
for i in range(5):
    print(i)
```

---

## Mistake 2 — Incorrect Indentation

Wrong:

```python
for i in range(5):
print(i)
```

Correct:

```python
for i in range(5):
    print(i)
```

---

## Mistake 3 — Infinite `while` Loop

Wrong:

```python
i = 1

while i <= 5:
    print(i)
```

Correct:

```python
i = 1

while i <= 5:
    print(i)
    i += 1
```

---

## Mistake 4 — Expecting `range(5)` to Include 5

```python
for i in range(5):
    print(i)
```

Output ends at:

```text
4
```

because the stop value is excluded.

---

# Quick Revision

## Loop Types

```text
for loop
while loop
```

## Loop Control Statements

```text
break
continue
pass
```

## Other Important Concepts

```text
range()
nested loops
loop else
```

---

# Key Points to Remember

- A loop executes code repeatedly.
- Python mainly has `for` and `while` loops.
- `for` is commonly used to iterate over an iterable.
- `while` runs as long as its condition is `True`.
- `range()` is commonly used with `for`.
- `range(stop)` starts from `0` and excludes `stop`.
- `break` terminates the loop.
- `continue` skips the current iteration.
- `pass` does nothing and acts as a placeholder.
- A nested loop is a loop inside another loop.
- `for...else` and `while...else` execute `else` when the loop completes normally.
- A loop's `else` does not execute when the loop exits through `break`.
- Indentation is mandatory in Python loops.
- Always make sure a `while` loop has a path toward becoming `False`, unless an intentional infinite loop is required.

# One-Line Definitions

> **Loop:** A programming structure used to execute code repeatedly.

> **`for` loop:** Iterates over an iterable.

> **`while` loop:** Repeats while a condition is `True`.

> **`break`:** Terminates the loop immediately.

> **`continue`:** Skips the current iteration and moves to the next one.

> **`pass`:** A placeholder statement that performs no action.

> **Nested loop:** A loop inside another loop.
