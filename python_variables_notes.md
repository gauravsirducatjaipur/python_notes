# Python Notes — Variables

## 1. Variables

### What is a Variable?

A **variable** is a name used to store a value in memory.

In Python, you do not need to declare the variable type explicitly. Python automatically determines the data type from the assigned value.

### Syntax

```python
variable_name = value
```

### Example

```python
name = "Gaurav"
age = 25
price = 99.99
```

Here:

- `name` stores a string.
- `age` stores an integer.
- `price` stores a floating-point number.

### Changing a Variable's Value

A variable's value can be changed during program execution.

```python
age = 25
age = 26

print(age)
```

**Output:**

```text
26
```

---

## 2. Variable Naming

A variable name is an identifier used to refer to a value.

### Rules for Naming Variables

1. A variable name can contain **letters**, **digits**, and **underscore (`_`)**.

```python
name = "Gaurav"
age2 = 25
student_name = "Rahul"
```

2. A variable name **cannot start with a digit**.

```python
2name = "Gaurav"      # ❌ Invalid
name2 = "Gaurav"      # ✅ Valid
```

3. A variable name **cannot contain spaces**.

```python
student name = "Rahul"     # ❌ Invalid
student_name = "Rahul"     # ✅ Valid
```

4. Python variable names are **case-sensitive**.

```python
name = "Gaurav"
Name = "Rahul"

print(name)
print(Name)
```

`name` and `Name` are treated as two different variables.

5. A variable name **cannot be a Python keyword**.

```python
class = "Python"     # ❌ Invalid
```

For example, `if`, `else`, `for`, `while`, `class`, `def`, `return`, etc. are Python keywords.

6. Variable names should be meaningful and readable.

```python
student_name = "Gaurav"
student_age = 25
```

This is better than:

```python
x = "Gaurav"
y = 25
```

### Recommended Naming Style

Python commonly uses **snake_case** for variable names.

```python
first_name = "Gaurav"
last_name = "Agrawal"
total_price = 500
student_count = 50
```

---

## 3. Assign Multiple Values to Variables

Python allows you to assign values to multiple variables in a single statement.

### Assign Different Values to Different Variables

```python
name, age, city = "Gaurav", 25, "Jaipur"

print(name)
print(age)
print(city)
```

**Output:**

```text
Gaurav
25
Jaipur
```

The values are assigned according to their position:

```text
name  → "Gaurav"
age   → 25
city  → "Jaipur"
```

### Assign the Same Value to Multiple Variables

You can assign the same value to multiple variables.

```python
x = y = z = 10

print(x)
print(y)
print(z)
```

**Output:**

```text
10
10
10
```

### Important

When assigning multiple different values, the number of variables and values should match.

```python
a, b, c = 10, 20, 30     # ✅
```

But:

```python
a, b = 10, 20, 30        # ❌ ValueError
```

---

# 4. Local Variable

### What is a Local Variable?

A **local variable** is a variable created inside a function.

It can normally be accessed only within that function.

### Example

```python
def greet():
    name = "Gaurav"
    print(name)

greet()
```

Here, `name` is a **local variable** because it is created inside `greet()`.

### Local Variable Cannot Normally Be Accessed Outside the Function

```python
def greet():
    name = "Gaurav"

greet()

print(name)    # ❌ NameError
```

`name` exists only in the local scope of `greet()`.

### Example with Different Local Variables

```python
def student():
    name = "Gaurav"
    age = 25

    print(name)
    print(age)

student()
```

Both `name` and `age` are local variables.

---

# 5. Global Variable

### What is a Global Variable?

A **global variable** is a variable created outside all functions.

It can be accessed from different parts of the program, including inside functions.

### Example

```python
name = "Gaurav"

def greet():
    print(name)

greet()
```

Here, `name` is a global variable.

### Global Variable and Local Variable with Same Name

If a local variable and a global variable have the same name, Python uses the **local variable inside the function**.

```python
name = "Gaurav"

def greet():
    name = "Rahul"
    print(name)

greet()
print(name)
```

**Output:**

```text
Rahul
Gaurav
```

Inside `greet()`, Python uses the local `name`.

Outside the function, Python uses the global `name`.

---

## 6. `global` Keyword

By default, if you assign a value to a variable inside a function, Python treats that variable as local.

To modify a global variable from inside a function, use the `global` keyword.

### Example

```python
x = 10

def change():
    global x
    x = 20

change()

print(x)
```

**Output:**

```text
20
```

Without `global`:

```python
x = 10

def change():
    x = 20

change()

print(x)
```

**Output:**

```text
10
```

Here, `x = 20` creates/updates a **local variable**, not the global `x`.

---

# Quick Revision

| Topic | Meaning | Example |
|---|---|---|
| Variable | Name that refers to a value | `age = 25` |
| Variable Naming | Rules for creating variable names | `student_name` |
| Multiple Assignment | Assign multiple values at once | `a, b = 10, 20` |
| Local Variable | Variable defined inside a function | `def fun(): x = 10` |
| Global Variable | Variable defined outside functions | `x = 10` |
| `global` | Allows a function to modify a global variable | `global x` |

## Key Points to Remember

- Python variables are created when a value is assigned.
- Python is **dynamically typed**.
- Variable names are **case-sensitive**.
- A variable name cannot start with a number.
- Use `snake_case` for readable Python variable names.
- Multiple variables can be assigned in one statement.
- A **local variable** belongs to a function's local scope.
- A **global variable** is defined outside functions.
- Use the `global` keyword when you need to modify a global variable from inside a function.
