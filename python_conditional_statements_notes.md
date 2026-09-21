# Python Notes — Conditional Statements

# 1. Conditional Statement

## What?

A **conditional statement** is used to make decisions in a Python program based on a condition.

The condition produces a Boolean result:

```python
True
```

or

```python
False
```

Python provides these commonly used conditional statements:

```text
if
if-else
if-elif-else
nested if
```

## Why?

Conditional statements are used when a program needs to execute different code depending on a situation.

Examples:

- Check whether a number is positive
- Check whether a person is eligible to vote
- Check whether a student passed
- Check login credentials
- Check age category
- Calculate grades

## When?

Use conditional statements whenever program execution depends on a condition.

## How?

A condition is written after `if` and followed by a colon `:`.

```python
if condition:
    statement
```

Python uses **indentation** to define the block.

---

# 2. `if` Statement

## What?

The `if` statement executes a block of code **only when its condition is `True`**.

## Why?

Use `if` when you want to perform an action only if a particular condition is satisfied.

## When?

Use `if` when there is only one action/path that needs to be checked.

## How?

### Syntax

```python
if condition:
    statement
```

### Example

```python
age = 20

if age >= 18:
    print("Eligible to vote")
```

Output:

```text
Eligible to vote
```

### Flow

```text
Condition
    ↓
 True?
  /   \
Yes    No
 ↓      ↓
Code   Skip
```

### Example — Positive Number

```python
number = 10

if number > 0:
    print("Positive number")
```

Output:

```text
Positive number
```

### If Condition is False

```python
number = -10

if number > 0:
    print("Positive number")

print("Program continues...")
```

Output:

```text
Program continues...
```

When the condition is `False`, the `if` block is skipped.

---

# 3. `if-else` Statement

## What?

`if-else` provides **two possible execution paths**.

- `if` block → condition is `True`
- `else` block → condition is `False`

## Why?

Use `if-else` when there are two alternatives.

For example:

```text
Pass / Fail
Adult / Minor
Even / Odd
Eligible / Not Eligible
```

## When?

Use `if-else` when exactly one of two blocks should execute.

## How?

### Syntax

```python
if condition:
    statement
else:
    statement
```

### Example

```python
age = 16

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Output:

```text
Minor
```

### Flow

```text
       Condition
           ↓
       True / False
        /       \
      True      False
       ↓          ↓
    if block   else block
```

---

## Example — Even or Odd

```python
number = 7

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Output:

```text
Odd
```

Here:

```python
number % 2 == 0
```

checks whether the remainder is `0`.

---

## Example — Pass or Fail

```python
marks = 65

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Pass
```

---

# 4. `if-elif-else` Statement

## What?

`if-elif-else` is used when there are **multiple conditions or multiple possible outcomes**.

`elif` means:

```text
else if
```

## Why?

It allows a program to select one option from multiple conditions.

## When?

Use `if-elif-else` when you have more than two possible outcomes.

Examples:

```text
Grade A
Grade B
Grade C
Grade D
Fail
```

## How?

### Syntax

```python
if condition1:
    statement
elif condition2:
    statement
elif condition3:
    statement
else:
    statement
```

Python checks conditions from **top to bottom**.

As soon as one condition is `True`, its block executes and the remaining `elif`/`else` blocks are skipped.

---

## Example — Grade System

```python
marks = 85

if marks >= 90:
    print("Grade A+")
elif marks >= 80:
    print("Grade A")
elif marks >= 70:
    print("Grade B")
elif marks >= 60:
    print("Grade C")
else:
    print("Fail")
```

Output:

```text
Grade A
```

### Flow

```text
marks >= 90 ?
      ↓ No
marks >= 80 ?
      ↓ Yes
   Grade A
```

---

## Important: Order of Conditions

The order of conditions matters.

Correct:

```python
marks = 95

if marks >= 90:
    print("A+")
elif marks >= 80:
    print("A")
elif marks >= 70:
    print("B")
```

Output:

```text
A+
```

If broader conditions are placed first:

```python
marks = 95

if marks >= 70:
    print("B")
elif marks >= 80:
    print("A")
elif marks >= 90:
    print("A+")
```

Output:

```text
B
```

Why?

Because `95 >= 70` is already `True`, so Python does not check the remaining `elif` conditions.

### Rule

> In `if-elif-else`, Python executes the **first condition that becomes `True`**.

---

# 5. Nested `if`

## What?

A **nested `if`** means placing one `if` statement inside another `if` statement.

```python
if condition1:
    if condition2:
        statement
```

## Why?

Nested `if` is useful when the second condition should be checked **only after the first condition is satisfied**.

## When?

Use nested `if` when there is a dependency between conditions.

For example:

```text
First check age
       ↓
If eligible
       ↓
Then check license
```

## How?

### Syntax

```python
if condition1:
    if condition2:
        statement
```

### Example

```python
age = 25
has_license = True

if age >= 18:
    if has_license:
        print("You can drive")
```

Output:

```text
You can drive
```

### Execution

First:

```python
age >= 18
```

is checked.

If it is `True`, then:

```python
has_license
```

is checked.

Only when both conditions are satisfied:

```text
You can drive
```

is printed.

---

# 6. Nested `if-else`

A nested `if` can also contain `else`.

```python
age = 25
has_license = False

if age >= 18:
    if has_license:
        print("You can drive")
    else:
        print("You need a driving license")
else:
    print("You are underage")
```

Output:

```text
You need a driving license
```

### Flow

```text
age >= 18?
   |
  Yes
   ↓
has_license?
  /      \
Yes      No
 ↓        ↓
Drive   Need license
```

---

# 7. Nested `if` with `elif`

Nested conditions can also contain `elif`.

```python
marks = 85
attendance = 80

if marks >= 40:
    if attendance >= 75:
        print("Eligible for result")
    elif attendance >= 60:
        print("Attendance is low")
    else:
        print("Attendance insufficient")
else:
    print("Student failed")
```

Output:

```text
Eligible for result
```

---

# 8. `if` vs `if-else` vs `if-elif-else` vs Nested `if`

| Statement | Use |
|---|---|
| `if` | One condition/action |
| `if-else` | Two alternatives |
| `if-elif-else` | Multiple alternatives |
| Nested `if` | Condition inside another condition |

### Easy Way to Remember

```text
if
↓
Only check one condition

if-else
↓
Choose between two paths

if-elif-else
↓
Choose between multiple paths

nested if
↓
Check a condition inside another condition
```

---

# 9. Multiple Conditions with `and`

Multiple conditions can be combined without nesting.

```python
age = 25
has_license = True

if age >= 18 and has_license:
    print("You can drive")
```

Output:

```text
You can drive
```

This can sometimes be simpler than:

```python
if age >= 18:
    if has_license:
        print("You can drive")
```

### Difference

Nested version:

```python
if age >= 18:
    if has_license:
        print("You can drive")
```

Combined version:

```python
if age >= 18 and has_license:
    print("You can drive")
```

Both can represent the same basic logic in this example.

---

# 10. Indentation in Conditional Statements

Python uses indentation to define a block.

Correct:

```python
age = 20

if age >= 18:
    print("Adult")
```

Nested example:

```python
if age >= 18:
    if has_license:
        print("Can drive")
```

The second `if` is inside the first `if` because it is indented further.

### Important

Do not use inconsistent indentation.

```python
if age >= 18:
print("Adult")
```

This causes an indentation error.

---

# 11. Conditions Can Contain Comparisons

Conditional statements commonly use comparison operators.

```python
x = 10

if x == 10:
    print("Equal")
```

Other examples:

```python
if x != 5:
    print("Not equal")

if x > 5:
    print("Greater")

if x < 20:
    print("Smaller")

if x >= 10:
    print("Greater or equal")

if x <= 10:
    print("Less or equal")
```

---

# 12. Conditions Can Use Logical Operators

## `and`

Both conditions must be `True`.

```python
age = 25

if age >= 18 and age <= 60:
    print("Eligible")
```

## `or`

At least one condition must be `True`.

```python
day = "Sunday"

if day == "Saturday" or day == "Sunday":
    print("Weekend")
```

## `not`

Reverses a Boolean condition.

```python
is_logged_in = False

if not is_logged_in:
    print("Please login")
```

---

# 13. Real-World Example — Login

```python
username = "admin"
password = "1234"

if username == "admin":
    if password == "1234":
        print("Login Successful")
    else:
        print("Wrong Password")
else:
    print("Invalid Username")
```

Output:

```text
Login Successful
```

This is a good example of a nested condition because the password is checked only after the username is correct.

---

# 14. Real-World Example — Shopping Discount

```python
amount = 6000
is_member = True

if is_member:
    if amount >= 5000:
        print("20% discount")
    else:
        print("10% discount")
else:
    print("No member discount")
```

Output:

```text
20% discount
```

---

# 15. Real-World Example — Student Grade

```python
marks = 76

if marks >= 90:
    print("A+")
elif marks >= 80:
    print("A")
elif marks >= 70:
    print("B")
elif marks >= 60:
    print("C")
elif marks >= 40:
    print("D")
else:
    print("Fail")
```

Output:

```text
B
```

---

# Quick Revision

## `if`

```python
if condition:
    statement
```

Used for a single condition.

## `if-else`

```python
if condition:
    statement
else:
    statement
```

Used for two alternatives.

## `if-elif-else`

```python
if condition1:
    statement
elif condition2:
    statement
else:
    statement
```

Used for multiple alternatives.

## Nested `if`

```python
if condition1:
    if condition2:
        statement
```

Used when one condition depends on another.

---

# Key Points to Remember

- Conditional statements are used for decision making.
- `if` executes code when its condition is `True`.
- `else` executes when the `if` condition is `False`.
- `elif` means `else if`.
- Multiple `elif` blocks can be used.
- Python checks `if`/`elif` conditions from top to bottom.
- Only the first matching `if`/`elif` block executes.
- `else` is optional.
- Nested `if` means an `if` inside another `if`.
- Indentation is mandatory in Python.
- Conditions commonly use comparison and logical operators.
- `and`, `or`, and `not` can be used to create complex conditions.

# One-Line Definitions

> **Conditional Statement:** A statement used to make decisions based on conditions.

> **`if`:** Executes a block when a condition is `True`.

> **`if-else`:** Selects one of two possible blocks.

> **`if-elif-else`:** Selects one block from multiple conditions.

> **Nested `if`:** An `if` statement placed inside another conditional block.
