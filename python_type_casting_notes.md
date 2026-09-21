# Python Notes — Type Casting

## 1. Type Casting

### What?

**Type Casting** means converting a value from one data type into another data type.

```python
x = "100"
y = int(x)

print(y)
print(type(y))
```

Output:

```text
100
<class 'int'>
```

Here `"100"` is a string and `int()` converts it into an integer.

### Why?

Type casting is needed when the current data type is not suitable for an operation.

For example, `input()` always returns a string:

```python
age = input("Enter age: ")
```

If the user enters `25`, Python stores it as `"25"`.

For numerical calculations:

```python
age = int(input("Enter age: "))
```

### When?

Type casting is commonly used when:

- Taking input from users
- Performing calculations
- Converting file/API data
- Processing data
- Converting strings into numbers
- Converting between collection types

### How?

Python provides built-in conversion functions:

```python
int()
float()
str()
bool()
complex()
list()
tuple()
set()
dict()
```

---

# 2. Types of Type Conversion

There are two broad types:

1. **Implicit Type Conversion**
2. **Explicit Type Conversion / Type Casting**

---

# 3. Implicit Type Conversion

### What?

Python automatically converts a value to a compatible type in some operations.

### Example

```python
x = 10
y = 2.5

result = x + y

print(result)
print(type(result))
```

Output:

```text
12.5
<class 'float'>
```

Python automatically handles:

```text
int + float → float
```

The programmer does not explicitly call a conversion function.

---

# 4. Explicit Type Conversion / Type Casting

### What?

Explicit conversion means the programmer manually converts a value.

### Example

```python
x = "100"
y = int(x)

print(y)
print(type(y))
```

Output:

```text
100
<class 'int'>
```

---

# 5. `int()` — Convert to Integer

### String to Integer

```python
x = "25"
y = int(x)

print(y)
print(type(y))
```

Output:

```text
25
<class 'int'>
```

### Float to Integer

```python
x = 25.9
y = int(x)

print(y)
```

Output:

```text
25
```

`int()` removes the fractional part; it does not round.

### Boolean to Integer

```python
print(int(True))
print(int(False))
```

Output:

```text
1
0
```

---

# 6. `float()` — Convert to Float

### Integer to Float

```python
x = 10
y = float(x)

print(y)
print(type(y))
```

Output:

```text
10.0
<class 'float'>
```

### String to Float

```python
x = "99.99"
y = float(x)

print(y)
```

Output:

```text
99.99
```

---

# 7. `str()` — Convert to String

```python
x = 100
y = str(x)

print(y)
print(type(y))
```

Output:

```text
100
<class 'str'>
```

Useful for combining numbers with text:

```python
age = 25

print("My age is " + str(age))
```

Output:

```text
My age is 25
```

---

# 8. `bool()` — Convert to Boolean

`bool()` converts a value into:

```python
True
```

or:

```python
False
```

### Examples

```python
print(bool(1))
print(bool(0))
```

Output:

```text
True
False
```

### Strings

```python
print(bool("Hello"))
print(bool(""))
```

Output:

```text
True
False
```

### Lists

```python
print(bool([1, 2, 3]))
print(bool([]))
```

Output:

```text
True
False
```

Common falsy values include:

```python
False
None
0
0.0
""
[]
()
{}
set()
```

---

# 9. `complex()` — Convert to Complex

```python
x = complex(2, 3)

print(x)
```

Output:

```text
(2+3j)
```

You can also convert a suitable string:

```python
x = complex("2+3j")

print(x)
```

Output:

```text
(2+3j)
```

---

# 10. Collection Type Casting

## List to Tuple

```python
numbers = [1, 2, 3]

result = tuple(numbers)

print(result)
```

Output:

```text
(1, 2, 3)
```

## Tuple to List

```python
numbers = (1, 2, 3)

result = list(numbers)

print(result)
```

Output:

```text
[1, 2, 3]
```

## List to Set

```python
numbers = [1, 2, 2, 3, 3]

result = set(numbers)

print(result)
```

Possible output:

```text
{1, 2, 3}
```

A set stores unique values.

## String to List

```python
text = "Python"

result = list(text)

print(result)
```

Output:

```text
['P', 'y', 't', 'h', 'o', 'n']
```

## String to Tuple

```python
text = "Python"

result = tuple(text)

print(result)
```

Output:

```text
('P', 'y', 't', 'h', 'o', 'n')
```

---

# 11. Type Casting with `input()`

This is one of the most important practical uses.

## Without Type Casting

```python
num1 = input("Enter first number: ")
num2 = input("Enter second number: ")

print(num1 + num2)
```

If the user enters:

```text
10
20
```

Output:

```text
1020
```

Because `input()` returns strings:

```text
"10" + "20" → "1020"
```

## With Type Casting

```python
num1 = int(input("Enter first number: "))
num2 = int(input("Enter second number: "))

print(num1 + num2)
```

Output:

```text
30
```

Now:

```text
"10" → 10
"20" → 20
```

---

# 12. Invalid Type Casting

Not every value can be converted into every type.

```python
x = "hello"
y = int(x)
```

This raises:

```text
ValueError
```

because `"hello"` is not a valid integer representation.

Another example:

```python
x = "10.5"
y = int(x)
```

This also raises `ValueError`.

Instead:

```python
x = "10.5"
y = int(float(x))

print(y)
```

Output:

```text
10
```

---

# 13. Type Casting vs Type Checking

These are different concepts.

## Type Checking

Use:

```python
type()
```

Example:

```python
x = "100"

print(type(x))
```

Output:

```text
<class 'str'>
```

## Type Casting

Use conversion functions:

```python
int()
float()
str()
bool()
```

Example:

```python
x = "100"
x = int(x)

print(type(x))
```

Output:

```text
<class 'int'>
```

### Remember

```text
type() → tells/checks the type

int(), float(), str(), bool() → convert the type
```

---

# 14. Common Type Conversion Table

| Original | Conversion | Result |
|---|---|---|
| `"10"` | `int("10")` | `10` |
| `"10.5"` | `float("10.5")` | `10.5` |
| `10` | `float(10)` | `10.0` |
| `10` | `str(10)` | `"10"` |
| `1` | `bool(1)` | `True` |
| `0` | `bool(0)` | `False` |
| `[1, 2]` | `tuple([1, 2])` | `(1, 2)` |
| `(1, 2)` | `list((1, 2))` | `[1, 2]` |
| `[1, 2, 2]` | `set([1, 2, 2])` | `{1, 2}` |

---

# 15. Real-World Example

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
salary = float(input("Enter your salary: "))

print("Name:", name)
print("Age:", age)
print("Salary:", salary)

print(type(name))
print(type(age))
print(type(salary))
```

If the user enters:

```text
Gaurav
40
50000.50
```

Output:

```text
Name: Gaurav
Age: 40
Salary: 50000.5

<class 'str'>
<class 'int'>
<class 'float'>
```

---

# Quick Revision

| Function | Purpose | Example |
|---|---|---|
| `int()` | Convert to integer | `int("10")` |
| `float()` | Convert to float | `float("10.5")` |
| `str()` | Convert to string | `str(100)` |
| `bool()` | Convert to Boolean | `bool(1)` |
| `complex()` | Create complex number | `complex(2, 3)` |
| `list()` | Convert to list | `list((1, 2))` |
| `tuple()` | Convert to tuple | `tuple([1, 2])` |
| `set()` | Convert to set | `set([1, 2, 2])` |
| `type()` | Check data type | `type(10)` |

# Key Points

- **Type Casting = converting one data type into another.**
- `input()` always returns a `str`.
- Use `int()` for integer conversion.
- Use `float()` for floating-point conversion.
- Use `str()` for string conversion.
- Use `bool()` for Boolean conversion.
- `int(10.9)` gives `10`; it does not round.
- Invalid conversions can raise `ValueError`.
- `type()` checks a type; it does not convert a type.
- Explicit conversion is performed by the programmer.
- Implicit conversion is performed automatically by Python in certain operations.

## One-Line Definition

> **Type Casting is the process of converting a value from one data type to another data type.**
