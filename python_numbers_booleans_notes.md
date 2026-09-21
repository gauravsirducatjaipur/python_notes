# Python Notes — Numbers and Booleans

# 1. Numbers

## What?

Python mein **Numbers** numeric values ko represent karne ke liye use hote hain.

Python ke main numeric data types hain:

```text
int
float
complex
```

Example:

```python
age = 40
price = 99.99
number = 2 + 3j
```

---

## Why?

Numbers ka use mathematical aur numerical operations ke liye hota hai.

For example:

- Age calculate karna
- Salary calculate karna
- Price calculate karna
- Percentage calculate karna
- Area aur volume calculate karna
- Counting karna
- Scientific calculations karna

Example:

```python
price = 500
quantity = 3

total = price * quantity

print(total)
```

Output:

```text
1500
```

---

## When?

Numbers ka use tab hota hai jab program mein numerical data ke saath kaam karna ho.

Examples:

```text
Age
Marks
Salary
Price
Quantity
Temperature
Distance
Percentage
```

---

## How?

Python mein numeric values ko directly variables mein store kar sakte hain.

```python
age = 40
marks = 85
price = 99.50
```

Python automatically appropriate numeric type identify karta hai.

---

# 2. Integer — `int`

## What?

`int` ka use **whole numbers** ko represent karne ke liye hota hai.

Integer mein decimal point nahi hota.

Examples:

```python
x = 10
y = -25
z = 0
```

## Why?

Whole-number values ko store aur calculate karne ke liye.

## When?

Jab value complete number ho:

```text
Age
Students count
Quantity
Roll number
Year
```

## How?

```python
age = 40
students = 50

print(age)
print(students)
```

Check the type:

```python
print(type(age))
```

Output:

```text
<class 'int'>
```

### Large Integers

Python integers ka size practically memory available hone tak grow kar sakta hai.

```python
number = 123456789012345678901234567890

print(number)
```

---

# 3. Float — `float`

## What?

`float` decimal/floating-point numbers ko represent karta hai.

Examples:

```python
price = 99.99
height = 5.7
percentage = 85.5
```

## Why?

Jab value mein decimal part ho.

## When?

Examples:

```text
Price
Height
Weight
Temperature
Percentage
Average
Distance
```

## How?

```python
price = 99.99

print(price)
print(type(price))
```

Output:

```text
99.99
<class 'float'>
```

### Float Arithmetic

```python
a = 10.5
b = 2.5

print(a + b)
print(a - b)
print(a * b)
print(a / b)
```

---

# 4. Complex — `complex`

## What?

Complex numbers mein **real part** aur **imaginary part** hota hai.

Python mein imaginary part ko `j` ke saath represent kiya jata hai.

```python
x = 2 + 3j
```

Here:

```text
2 → Real part
3j → Imaginary part
```

## Why?

Complex numbers mathematical, scientific aur engineering calculations mein useful hote hain.

## When?

Generally:

- Engineering
- Signal processing
- Scientific computing
- Advanced mathematics

## How?

```python
x = 2 + 3j

print(x)
print(type(x))
```

Output:

```text
(2+3j)
<class 'complex'>
```

### Access Real and Imaginary Parts

```python
x = 2 + 3j

print(x.real)
print(x.imag)
```

Output:

```text
2.0
3.0
```

---

# 5. Number Operations

Python numbers ke saath different arithmetic operations perform kar sakte hain.

```python
a = 10
b = 3

print(a + b)   # Addition
print(a - b)   # Subtraction
print(a * b)   # Multiplication
print(a / b)   # Division
print(a // b)  # Floor Division
print(a % b)   # Modulus
print(a ** b)  # Exponentiation
```

Output:

```text
13
7
30
3.3333333333333335
3
1
1000
```

---

# 6. Division and Floor Division

## `/` — Division

```python
print(10 / 3)
```

Output:

```text
3.3333333333333335
```

`/` normally returns a `float`.

## `//` — Floor Division

```python
print(10 // 3)
```

Output:

```text
3
```

It returns the floor of the result.

For negative values:

```python
print(-10 // 3)
```

Output:

```text
-4
```

Because floor means toward negative infinity.

---

# 7. Modulus `%`

## What?

`%` remainder return karta hai.

```python
print(10 % 3)
```

Output:

```text
1
```

## Why?

Modulus ka use commonly:

- Even/odd checking
- Divisibility
- Cyclic calculations
- Remainder finding

### Even/Odd Example

```python
number = 10

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Output:

```text
Even
```

---

# 8. Exponentiation `**`

`**` power calculate karne ke liye use hota hai.

```python
print(2 ** 3)
```

Output:

```text
8
```

Meaning:

```text
2 × 2 × 2 = 8
```

---

# 9. Type Conversion with Numbers

Numbers ko ek numeric type se doosre type mein convert kiya ja sakta hai.

### Integer to Float

```python
x = 10

y = float(x)

print(y)
```

Output:

```text
10.0
```

### Float to Integer

```python
x = 10.9

y = int(x)

print(y)
```

Output:

```text
10
```

`int()` decimal portion ko remove karta hai; rounding nahi karta.

### String to Number

```python
x = "100"

y = int(x)

print(y)
```

Output:

```text
100
```

---

# 10. Boolean

## What?

`bool` Python ka data type hai jo sirf do values represent karta hai:

```python
True
False
```

Example:

```python
is_logged_in = True
is_admin = False
```

## Why?

Boolean values ka use **decision making aur conditions** ke liye hota hai.

Example:

```python
age = 20

print(age >= 18)
```

Output:

```text
True
```

## When?

Booleans ka use commonly:

- `if` statements
- Login status
- Permission checking
- Validation
- Comparisons
- Flags
- Program state

## How?

Boolean values ko directly assign kar sakte hain:

```python
is_active = True
is_deleted = False
```

Check type:

```python
print(type(is_active))
```

Output:

```text
<class 'bool'>
```

---

# 11. Boolean from Comparison

Comparison operators ka result Boolean hota hai.

```python
x = 10
y = 5

print(x > y)
print(x < y)
print(x == y)
```

Output:

```text
True
False
False
```

### More Examples

```python
print(10 == 10)
print(10 != 5)
print(10 >= 10)
print(5 > 10)
```

Output:

```text
True
True
True
False
```

---

# 12. Boolean with `if`

Boolean conditions ka sabse common use `if` mein hota hai.

```python
age = 20

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Output:

```text
Adult
```

Yahan:

```python
age >= 18
```

ka result:

```python
True
```

hai.

---

# 13. Boolean Values as Numbers

Python mein:

```python
True
```

numeric context mein `1` ke equivalent behave karta hai.

Aur:

```python
False
```

`0` ke equivalent behave karta hai.

Example:

```python
print(True + True)
print(True + False)
print(False + False)
```

Output:

```text
2
1
0
```

### Important

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

# 14. `bool()` Function

## What?

`bool()` kisi value ko Boolean value mein convert karta hai.

## How?

```python
bool(value)
```

### Numbers

```python
print(bool(1))
print(bool(10))
print(bool(-5))
print(bool(0))
```

Output:

```text
True
True
True
False
```

Generally:

```text
0 → False
Non-zero → True
```

---

# 15. Boolean with Strings

```python
print(bool("Hello"))
print(bool("Python"))
print(bool(""))
```

Output:

```text
True
True
False
```

Generally:

```text
Non-empty string → True
Empty string → False
```

---

# 16. Boolean with Lists

```python
print(bool([1, 2, 3]))
print(bool([]))
```

Output:

```text
True
False
```

Generally:

```text
Non-empty collection → True
Empty collection → False
```

This applies to common empty containers such as:

```python
[]
()
{}
set()
```

---

# 17. Truthy and Falsy Values

## What?

Python mein kuch values conditions mein `True` ki tarah behave karti hain aur kuch `False` ki tarah.

Inhe commonly:

```text
Truthy
Falsy
```

values kaha jata hai.

### Common Falsy Values

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

### Examples

```python
if 0:
    print("True")
else:
    print("False")
```

Output:

```text
False
```

```python
if 100:
    print("True")
else:
    print("False")
```

Output:

```text
True
```

---

# 18. Boolean with Logical Operators

Boolean values ko logical operators ke saath combine kar sakte hain.

## `and`

Dono conditions true honi chahiye.

```python
age = 25

print(age >= 18 and age <= 60)
```

Output:

```text
True
```

## `or`

At least one condition true honi chahiye.

```python
age = 16

print(age < 18 or age > 60)
```

Output:

```text
True
```

## `not`

Boolean result ko reverse karta hai.

```python
is_logged_in = True

print(not is_logged_in)
```

Output:

```text
False
```

---

# 19. Boolean as a Flag

Boolean variables ko program state store karne ke liye use karna common hai.

```python
is_logged_in = True
is_admin = False
is_active = True
```

Example:

```python
is_logged_in = True

if is_logged_in:
    print("Welcome")
else:
    print("Please login")
```

Output:

```text
Welcome
```

---

# 20. Numbers vs Booleans

| Feature | Numbers | Boolean |
|---|---|---|
| Main types | `int`, `float`, `complex` | `bool` |
| Purpose | Numeric data | True/False decisions |
| Example | `10`, `10.5`, `2+3j` | `True`, `False` |
| Common use | Calculations | Conditions |
| `type()` | `<class 'int'>`, etc. | `<class 'bool'>` |

---

# 21. Important Difference: `True` and `1`

Python mein Boolean `True` numeric context mein `1` ke equivalent behave karta hai, but conceptually Boolean aur integer alag types hain.

```python
x = True
y = 1

print(type(x))
print(type(y))
```

Output:

```text
<class 'bool'>
<class 'int'>
```

---

# 22. Important Difference: `False` and `0`

Similarly:

```python
x = False
y = 0

print(type(x))
print(type(y))
```

Output:

```text
<class 'bool'>
<class 'int'>
```

So:

```text
False behaves like 0 in numeric contexts
True behaves like 1 in numeric contexts
```

But:

```text
False → bool
0     → int

True  → bool
1     → int
```

---

# 23. Real-World Example

## Student Result

```python
marks = 75

passed = marks >= 40

print(passed)

if passed:
    print("Student Passed")
else:
    print("Student Failed")
```

Output:

```text
True
Student Passed
```

Here:

```python
passed = marks >= 40
```

creates a Boolean value.

---

# 24. Real-World Example — Login

```python
username = "admin"
password = "1234"

is_valid = username == "admin" and password == "1234"

print(is_valid)

if is_valid:
    print("Login Successful")
else:
    print("Invalid Login")
```

Output:

```text
True
Login Successful
```

---

# Quick Revision

## Numbers

```text
int    → Whole numbers
float  → Decimal numbers
complex → Complex numbers
```

## Boolean

```text
bool → True / False
```

## Common Functions

| Function | Purpose | Example |
|---|---|---|
| `int()` | Convert to integer | `int(10.5)` |
| `float()` | Convert to float | `float(10)` |
| `complex()` | Create complex number | `complex(2, 3)` |
| `bool()` | Convert to Boolean | `bool(1)` |

## Important Values

```text
0        → False
0.0      → False
""       → False
[]       → False
()       → False
{}       → False
None     → False

Non-zero number → True
Non-empty string → True
Non-empty collection → True
```

# Key Points

- Python ke main numeric types `int`, `float`, aur `complex` hain.
- `int` whole numbers ke liye use hota hai.
- `float` decimal values ke liye use hota hai.
- `complex` real + imaginary values ke liye use hota hai.
- Arithmetic operators numbers ke saath calculations perform karte hain.
- `%` remainder return karta hai.
- `//` floor division perform karta hai.
- `**` exponentiation ke liye use hota hai.
- `bool` ki sirf do values hoti hain: `True` aur `False`.
- Comparison expressions ka result Boolean hota hai.
- `0` aur empty collections generally falsy hote hain.
- Non-zero numbers aur non-empty collections generally truthy hote hain.
- `True` numeric context mein `1` aur `False` `0` ki tarah behave karte hain.
- Boolean values ka major use decision making mein hota hai.

# One-Line Definitions

> **Number:** Numeric values ko represent karne wala data type/category.

> **Boolean:** A data type that represents either `True` or `False`.

> **Truthy:** A value that behaves like `True` in a Boolean context.

> **Falsy:** A value that behaves like `False` in a Boolean context.
