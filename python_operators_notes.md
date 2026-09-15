# Python Notes — Operators

## 1. Operators

### What?

An **operator** is a symbol or keyword used to perform an operation on values or variables.

Example:

```python
a = 10
b = 5

print(a + b)
```

Here, `+` is an operator.

- `a` and `b` → operands
- `+` → operator
- `a + b` → expression

### Why?

Operators are used to:

- Perform calculations
- Compare values
- Combine conditions
- Assign values
- Check whether a value exists in a sequence
- Check object identity
- Perform bit-level operations

### When?

Whenever a Python program needs to **calculate, compare, assign, test, or manipulate values**, operators are used.

### How?

Python provides several categories of operators.

---

# 2. Types of Operators

Python has the following main types of operators:

1. Arithmetic Operators
2. Assignment Operators
3. Comparison Operators
4. Logical Operators
5. Identity Operators
6. Membership Operators
7. Bitwise Operators

---

# 3. Arithmetic Operators

### What?

Arithmetic operators are used to perform mathematical operations.

### Operators

| Operator | Name | Example |
|---|---|---|
| `+` | Addition | `10 + 5` |
| `-` | Subtraction | `10 - 5` |
| `*` | Multiplication | `10 * 5` |
| `/` | Division | `10 / 5` |
| `%` | Modulus | `10 % 3` |
| `**` | Exponentiation | `10 ** 2` |
| `//` | Floor Division | `10 // 3` |

### Example

```python
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a % b)
print(a ** b)
print(a // b)
```

**Output:**

```text
13
7
30
3.3333333333333335
1
1000
3
```

### Important

#### `/` — Division

```python
print(10 / 3)
```

Output:

```text
3.3333333333333335
```

`/` returns a floating-point result.

#### `//` — Floor Division

```python
print(10 // 3)
```

Output:

```text
3
```

Floor division returns the floor of the division result.

For negative numbers, "floor" means toward negative infinity:

```python
print(-10 // 3)
```

Output:

```text
-4
```

#### `%` — Modulus

Returns the remainder.

```python
print(10 % 3)
```

Output:

```text
1
```

#### `**` — Exponentiation

Used for powers.

```python
print(2 ** 3)
```

Output:

```text
8
```

---

# 4. Assignment Operators

### What?

Assignment operators are used to assign values to variables.

### Operators

| Operator | Example | Equivalent To |
|---|---|---|
| `=` | `x = 10` | `x = 10` |
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 5` | `x = x - 5` |
| `*=` | `x *= 5` | `x = x * 5` |
| `/=` | `x /= 5` | `x = x / 5` |
| `%=` | `x %= 5` | `x = x % 5` |
| `//=` | `x //= 5` | `x = x // 5` |
| `**=` | `x **= 5` | `x = x ** 5` |
| `&=` | `x &= 5` | `x = x & 5` |
| `|=` | `x |= 5` | `x = x | 5` |
| `^=` | `x ^= 5` | `x = x ^ 5` |
| `>>=` | `x >>= 5` | `x = x >> 5` |
| `<<=` | `x <<= 5` | `x = x << 5` |

### Example

```python
x = 10

x += 5
print(x)
```

**Output:**

```text
15
```

This:

```python
x += 5
```

is equivalent to:

```python
x = x + 5
```

### Example with Multiple Assignment

```python
a, b = 10, 20
```

Both variables receive their corresponding values.

---

# 5. Comparison Operators

### What?

Comparison operators compare two values.

The result is always a Boolean value:

```python
True
```

or

```python
False
```

### Operators

| Operator | Meaning | Example |
|---|---|---|
| `==` | Equal to | `5 == 5` |
| `!=` | Not equal to | `5 != 3` |
| `>` | Greater than | `5 > 3` |
| `<` | Less than | `3 < 5` |
| `>=` | Greater than or equal to | `5 >= 5` |
| `<=` | Less than or equal to | `3 <= 5` |

### Example

```python
a = 10
b = 5

print(a == b)
print(a != b)
print(a > b)
print(a < b)
print(a >= b)
print(a <= b)
```

**Output:**

```text
False
True
True
False
True
False
```

### Important: `=` vs `==`

These are different.

```python
x = 10
```

`=` means **assignment**.

```python
x == 10
```

`==` means **comparison**.

It checks whether `x` is equal to `10`.

---

# 6. Logical Operators

### What?

Logical operators are used to combine or modify conditions.

### Operators

| Operator | Meaning |
|---|---|
| `and` | True if both conditions are True |
| `or` | True if at least one condition is True |
| `not` | Reverses the Boolean result |

---

## `and`

Returns `True` only when both conditions are true.

```python
age = 25

print(age > 18 and age < 60)
```

**Output:**

```text
True
```

Example:

```python
print(True and True)
print(True and False)
print(False and True)
print(False and False)
```

**Output:**

```text
True
False
False
False
```

---

## `or`

Returns `True` if at least one condition is true.

```python
age = 16

print(age < 18 or age > 60)
```

**Output:**

```text
True
```

Example:

```python
print(True or True)
print(True or False)
print(False or True)
print(False or False)
```

**Output:**

```text
True
True
True
False
```

---

## `not`

Reverses the Boolean result.

```python
is_logged_in = True

print(not is_logged_in)
```

**Output:**

```text
False
```

---

# 7. Identity Operators

### What?

Identity operators check whether two variables refer to the **same object in memory**.

### Operators

| Operator | Meaning |
|---|---|
| `is` | Same object |
| `is not` | Not the same object |

### Example

```python
x = [1, 2, 3]
y = x

print(x is y)
```

**Output:**

```text
True
```

Both variables refer to the same list object.

### `is` vs `==`

This is important.

`==` checks whether values are equal.

`is` checks whether two references point to the same object.

Example:

```python
x = [1, 2, 3]
y = [1, 2, 3]

print(x == y)
print(x is y)
```

**Output:**

```text
True
False
```

The lists contain equal values, but they are different objects.

### When to Use `is`

A common and important use is checking for `None`:

```python
result = None

if result is None:
    print("No result")
```

---

# 8. Membership Operators

### What?

Membership operators check whether a value exists inside a sequence or collection.

### Operators

| Operator | Meaning |
|---|---|
| `in` | Value exists |
| `not in` | Value does not exist |

### Example with String

```python
text = "Python"

print("P" in text)
print("z" in text)
```

**Output:**

```text
True
False
```

### Example with List

```python
fruits = ["apple", "banana", "mango"]

print("apple" in fruits)
print("orange" not in fruits)
```

**Output:**

```text
True
True
```

### Dictionary Note

For a dictionary, `in` checks **keys** by default.

```python
student = {
    "name": "Gaurav",
    "age": 25
}

print("name" in student)
print("Gaurav" in student)
```

**Output:**

```text
True
False
```

---

# 9. Bitwise Operators

### What?

Bitwise operators work on the individual **bits** of integer values.

### Operators

| Operator | Name | Example |
|---|---|---|
| `&` | AND | `5 & 3` |
| `|` | OR | `5 | 3` |
| `^` | XOR | `5 ^ 3` |
| `~` | NOT | `~5` |
| `<<` | Left Shift | `5 << 1` |
| `>>` | Right Shift | `5 >> 1` |

### Example

```python
a = 5
b = 3

print(a & b)
print(a | b)
print(a ^ b)
print(~a)
print(a << 1)
print(a >> 1)
```

**Output:**

```text
1
7
6
-6
10
2
```

### Binary Example

`5` in binary:

```text
101
```

`3` in binary:

```text
011
```

#### AND — `&`

```text
101
011
---
001
```

Therefore:

```python
5 & 3
```

gives:

```text
1
```

#### OR — `|`

```text
101
011
---
111
```

Therefore:

```python
5 | 3
```

gives:

```text
7
```

#### XOR — `^`

XOR gives `1` when the two bits are different.

```text
101
011
---
110
```

Therefore:

```python
5 ^ 3
```

gives:

```text
6
```

---

# 10. Operator Precedence

### What?

**Operator precedence** determines the order in which Python evaluates operators in an expression.

### Example

```python
result = 10 + 5 * 2

print(result)
```

**Output:**

```text
20
```

Multiplication is performed before addition:

```text
10 + (5 * 2)
10 + 10
20
```

### Parentheses

Use parentheses when you want to explicitly control the order.

```python
result = (10 + 5) * 2

print(result)
```

**Output:**

```text
30
```

### Common Precedence Order

From higher to lower precedence:

```text
()
**
+x, -x, ~x
*, /, //, %
+, -
<<, >>
&
^
|
==, !=, >, <, >=, <=
is, is not
in, not in
not
and
or
```

When in doubt, use parentheses:

```python
result = (a + b) * c
```

---

# Quick Revision

| Operator Type | Operators | Main Purpose |
|---|---|---|
| Arithmetic | `+ - * / % ** //` | Mathematical operations |
| Assignment | `= += -= *= /= ...` | Assign/update values |
| Comparison | `== != > < >= <=` | Compare values |
| Logical | `and or not` | Combine conditions |
| Identity | `is`, `is not` | Compare object identity |
| Membership | `in`, `not in` | Check membership |
| Bitwise | `& \| ^ ~ << >>` | Work with bits |

# Important Differences

## `=` vs `==` vs `is`

```python
x = 10
```

→ Assignment

```python
x == 10
```

→ Value comparison

```python
x is y
```

→ Object identity comparison

---

## `==` vs `is`

Remember:

> `==` → **Are the values equal?**

> `is` → **Are they the same object?**

---

## `/` vs `//`

```python
10 / 3
```

→ `3.333...`

```python
10 // 3
```

→ `3`

---

## `and` vs `or`

```python
condition1 and condition2
```

→ Both conditions need to be true.

```python
condition1 or condition2
```

→ At least one condition needs to be true.

---

# Final Takeaway

Operators are the building blocks used to perform operations in Python.

The most important groups to remember are:

```text
Arithmetic
Assignment
Comparison
Logical
Identity
Membership
Bitwise
```

For everyday Python programming, focus especially on:

```python
+  -  *  /  //  %  **
=  +=  -=  *=
==  !=  >  <  >=  <=
and  or  not
is  is not
in  not in
```
