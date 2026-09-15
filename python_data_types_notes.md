# Python Notes — Data Types

## 1. Data Types

### What is a Data Type?

A **data type** tells Python what kind of value a variable contains.

For example:

```python
name = "Gaurav"
age = 25
price = 99.99
```

Here:

- `"Gaurav"` → `str` (string)
- `25` → `int` (integer)
- `99.99` → `float` (floating-point number)

Python automatically determines the data type when a value is assigned.

### Why Do We Need Data Types?

Different types of data behave differently.

For example:

```python
x = 10
y = 20

print(x + y)
```

**Output:**

```text
30
```

But:

```python
x = "10"
y = "20"

print(x + y)
```

**Output:**

```text
1020
```

The first example performs numerical addition, while the second joins two strings.

### When Are Data Types Used?

Data types are important whenever you:

- Store data in variables
- Perform calculations
- Work with text
- Store collections of values
- Check or validate data
- Convert data from one type to another

### How Does Python Determine the Type?

Python determines the type from the value assigned to the variable.

```python
x = 10
print(type(x))
```

**Output:**

```text
<class 'int'>
```

---

# 2. Built-in Data Types

Python provides several built-in data types.

## Main Built-in Data Types

| Category | Data Type | Example |
|---|---|---|
| Text | `str` | `"Hello"` |
| Numeric | `int` | `10` |
| Numeric | `float` | `10.5` |
| Numeric | `complex` | `2 + 3j` |
| Sequence | `list` | `[1, 2, 3]` |
| Sequence | `tuple` | `(1, 2, 3)` |
| Sequence | `range` | `range(5)` |
| Mapping | `dict` | `{"name": "Gaurav"}` |
| Set | `set` | `{1, 2, 3}` |
| Set | `frozenset` | `frozenset({1, 2, 3})` |
| Boolean | `bool` | `True` |
| Binary | `bytes` | `b"Hello"` |
| Binary | `bytearray` | `bytearray(5)` |
| Binary | `memoryview` | `memoryview(bytes(5))` |
| None | `NoneType` | `None` |

### 2.1 String — `str`

Used to store text.

```python
name = "Gaurav"
city = 'Jaipur'
```

---

### 2.2 Integer — `int`

Used for whole numbers, without a decimal point.

```python
age = 25
marks = 90
```

---

### 2.3 Float — `float`

Used for numbers containing a decimal point.

```python
price = 99.99
height = 5.8
```

---

### 2.4 Complex — `complex`

Used for complex numbers.

```python
x = 2 + 3j
```

Here:

- `2` → real part
- `3j` → imaginary part

---

### 2.5 List — `list`

A list stores multiple values and is **ordered and changeable (mutable)**.

```python
fruits = ["apple", "banana", "mango"]

print(fruits)
```

---

### 2.6 Tuple — `tuple`

A tuple stores multiple values and is **ordered but unchangeable (immutable)**.

```python
fruits = ("apple", "banana", "mango")
```

---

### 2.7 Range — `range`

Represents a sequence of numbers, commonly used with loops.

```python
numbers = range(5)

print(numbers)
```

The sequence represents:

```text
0, 1, 2, 3, 4
```

---

### 2.8 Dictionary — `dict`

Stores data in **key-value pairs**.

```python
student = {
    "name": "Gaurav",
    "age": 25
}
```

Here:

```text
"name" → "Gaurav"
"age"  → 25
```

---

### 2.9 Set — `set`

A set stores **unique values** and is unordered.

```python
numbers = {1, 2, 3, 3}

print(numbers)
```

The duplicate `3` is removed.

---

### 2.10 Frozenset — `frozenset`

A frozenset is an **immutable set**.

```python
numbers = frozenset({1, 2, 3})
```

Unlike a normal set, its elements cannot be changed.

---

### 2.11 Boolean — `bool`

Stores either:

```python
True
False
```

Example:

```python
is_logged_in = True
is_admin = False
```

---

### 2.12 Bytes — `bytes`

Used to store immutable binary data.

```python
data = b"Hello"
```

---

### 2.13 Bytearray — `bytearray`

Used to store mutable binary data.

```python
data = bytearray(5)
```

---

### 2.14 Memoryview — `memoryview`

Provides a way to access the internal data of binary objects without copying the data.

```python
data = memoryview(bytes(5))
```

---

### 2.15 NoneType — `None`

`None` represents the absence of a value.

```python
result = None
```

Its type is:

```python
print(type(result))
```

**Output:**

```text
<class 'NoneType'>
```

---

# 3. Get the Data Type

## What?

Python provides the `type()` function to find the data type of a value or variable.

## Why?

It is useful when you want to know what type of data you are working with.

## When?

Use `type()` when:

- Debugging a program
- Checking input data
- Understanding a variable's type
- Learning or testing Python code

## How?

### Syntax

```python
type(object)
```

### Example

```python
x = 10

print(type(x))
```

**Output:**

```text
<class 'int'>
```

### More Examples

```python
name = "Gaurav"
price = 99.99
is_active = True
numbers = [1, 2, 3]

print(type(name))
print(type(price))
print(type(is_active))
print(type(numbers))
```

**Output:**

```text
<class 'str'>
<class 'float'>
<class 'bool'>
<class 'list'>
```

---

# 4. Set the Data Type

## What?

Python allows you to create values of specific data types using built-in constructor functions.

## Why?

Sometimes you want to explicitly create a value as a particular type.

## How?

Common type constructors include:

```python
str()
int()
float()
complex()
list()
tuple()
range()
dict()
set()
frozenset()
bool()
bytes()
bytearray()
```

### Examples

```python
x = str("Hello")
y = int(10)
z = float(10.5)

print(type(x))
print(type(y))
print(type(z))
```

**Output:**

```text
<class 'str'>
<class 'int'>
<class 'float'>
```

### Creating Different Types

```python
a = list((1, 2, 3))
b = tuple([1, 2, 3])
c = set([1, 2, 3])
d = dict(name="Gaurav", age=25)

print(a)
print(b)
print(c)
print(d)
```

---

# 5. Type Casting

## What?

**Type casting** means converting a value from one data type to another.

Python provides built-in functions such as:

```python
int()
float()
str()
bool()
list()
tuple()
set()
```

## Why?

Type casting is needed when data is in one type but your program requires another type.

A very common example is user input.

```python
age = input("Enter your age: ")
```

`input()` returns a string, even if the user enters a number.

So:

```python
age = int(input("Enter your age: "))
```

converts the input from `str` to `int`.

## When?

Type casting is commonly used when:

- Taking input from users
- Performing calculations
- Converting API or file data
- Combining values of different types
- Processing data

## How?

### String to Integer

```python
x = "10"

y = int(x)

print(y)
print(type(y))
```

**Output:**

```text
10
<class 'int'>
```

---

### Integer to Float

```python
x = 10

y = float(x)

print(y)
```

**Output:**

```text
10.0
```

---

### Float to Integer

```python
x = 10.8

y = int(x)

print(y)
```

**Output:**

```text
10
```

`int()` removes the decimal portion; it does not round the number.

---

### Integer to String

```python
x = 100

y = str(x)

print(y)
print(type(y))
```

**Output:**

```text
100
<class 'str'>
```

---

### String to Float

```python
x = "99.99"

y = float(x)

print(y)
```

**Output:**

```text
99.99
```

---

### String to Boolean

```python
x = bool("Hello")

print(x)
```

**Output:**

```text
True
```

Important:

```python
bool("")
```

returns:

```text
False
```

while a non-empty string returns `True`.

---

# 6. Important Type Casting Examples

### Example 1 — User Input

```python
age = input("Enter your age: ")

print(type(age))
```

If the user enters:

```text
25
```

the type is still:

```text
<class 'str'>
```

To use it as a number:

```python
age = int(input("Enter your age: "))

print(type(age))
```

Now the type is:

```text
<class 'int'>
```

---

### Example 2 — Addition

Without type casting:

```python
a = input("Enter first number: ")
b = input("Enter second number: ")

print(a + b)
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

Because both values are strings.

With type casting:

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print(a + b)
```

Output:

```text
30
```

---

# 7. Implicit vs Explicit Type Conversion

## Implicit Type Conversion

Python automatically converts a value to another compatible type in some operations.

Example:

```python
x = 10
y = 2.5

z = x + y

print(z)
print(type(z))
```

**Output:**

```text
12.5
<class 'float'>
```

Python automatically converts the integer `10` to a float for the calculation.

---

## Explicit Type Conversion

When the programmer manually converts the type, it is called **explicit type conversion** or **type casting**.

```python
x = "10"

y = int(x)

print(y)
```

Here, the programmer explicitly converts `str` to `int`.

---

# Quick Revision

| Topic | Meaning | Example |
|---|---|---|
| Data Type | Defines the kind of data | `int`, `str`, `float` |
| Built-in Data Types | Types provided by Python | `list`, `dict`, `set`, etc. |
| `type()` | Gets the data type | `type(x)` |
| Type Constructor | Creates a specific type | `int(10)` |
| Type Casting | Converts one type into another | `int("10")` |
| Implicit Conversion | Python performs conversion automatically | `10 + 2.5` |
| Explicit Conversion | Programmer performs conversion | `int("10")` |

## Key Points to Remember

- Python is **dynamically typed**.
- Use `type()` to check the type of a value.
- Python has many built-in data types.
- `int()`, `float()`, `str()`, `bool()`, etc. are type constructors/conversion functions.
- **Type casting** means explicitly converting one data type into another.
- `input()` always returns a `str`.
- Use `int(input())` when you need integer input.
- `int(10.8)` gives `10`; it does not round to `11`.
- Implicit conversion is performed automatically by Python in compatible operations.
- Explicit conversion is performed manually by the programmer.
