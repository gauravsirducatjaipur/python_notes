# Python Notes — Functions

# 1. Function

## What?

A **function** is a reusable block of code designed to perform a specific task.

Instead of writing the same code repeatedly, we can write it once inside a function and call it whenever needed.

```python
def greet():
    print("Hello")

greet()
```

Output:

```text
Hello
```

Here:

```text
def    → keyword used to define a function
greet  → function name
()     → parameter list
:      → starts the function block
greet() → function call
```

## Why?

Functions are used to:

- Reuse code
- Avoid code duplication
- Make programs easier to understand
- Break large programs into smaller parts
- Make debugging easier
- Make code easier to maintain
- Create modular programs

## When?

Use a function when:

- A task needs to be performed multiple times.
- A program contains a logically separate task.
- You want to reuse code.
- You want to divide a large program into smaller modules.

## How?

Define a function using `def`.

```python
def function_name():
    # function body
```

Call it using:

```python
function_name()
```

---

# 2. Defining and Calling a Function

## Define Function

```python
def greet():
    print("Hello Python")
```

At this point, the function is defined but its code has not executed.

## Call Function

```python
greet()
```

Output:

```text
Hello Python
```

A function can be called multiple times:

```python
def greet():
    print("Hello Python")

greet()
greet()
```

Output:

```text
Hello Python
Hello Python
```

---

# 3. Function with Parameters

## What?

A **parameter** is a variable written in the function definition that receives a value when the function is called.

```python
def greet(name):
    print("Hello", name)

greet("Gaurav")
```

Output:

```text
Hello Gaurav
```

Here `name` is a parameter.

---

# 4. Argument

## What?

An **argument** is the actual value passed to a function when it is called.

```python
def greet(name):
    print("Hello", name)

greet("Gaurav")
```

Here:

```text
name     → parameter
"Gaurav" → argument
```

### Easy Difference

```text
Parameter → variable in function definition
Argument  → actual value passed during function call
```

---

# 5. Multiple Parameters

```python
def add(a, b):
    print(a + b)

add(10, 20)
```

Output:

```text
30
```

Here:

```text
a → 10
b → 20
```

---

# 6. Function with `return`

## What?

The `return` statement sends a value back from a function to the place where the function was called.

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

Output:

```text
30
```

## Why?

`return` is useful when the result needs to be:

- Stored in a variable
- Used in another calculation
- Passed to another function
- Printed later
- Used in a condition

Example:

```python
def square(number):
    return number * number

result = square(5)

print(result)
```

Output:

```text
25
```

---

# 7. `print()` vs `return`

## Using `print()`

```python
def add(a, b):
    print(a + b)

result = add(10, 20)

print(result)
```

Output:

```text
30
None
```

The function displays the result but does not return it.

## Using `return`

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

Output:

```text
30
```

### Remember

```text
print() → displays a value
return  → sends a value back from the function
```

---

# 8. Function Without `return`

If a function does not explicitly return a value, Python returns:

```python
None
```

Example:

```python
def greet():
    print("Hello")

result = greet()

print(result)
```

Output:

```text
Hello
None
```

---

# 9. Default Parameter

A parameter can have a default value.

```python
def greet(name="Guest"):
    print("Hello", name)

greet()
greet("Gaurav")
```

Output:

```text
Hello Guest
Hello Gaurav
```

If no argument is provided, the default value is used.

---

# 10. Positional Arguments

Arguments passed according to their position are called positional arguments.

```python
def student(name, age):
    print(name, age)

student("Gaurav", 40)
```

Here:

```text
"Gaurav" → name
40       → age
```

The order matters.

---

# 11. Keyword Arguments

Keyword arguments pass values using parameter names.

```python
def student(name, age):
    print(name, age)

student(age=40, name="Gaurav")
```

Output:

```text
Gaurav 40
```

The order does not matter when parameter names are specified.

---

# 12. Positional vs Keyword Arguments

| Type | Meaning | Example |
|---|---|---|
| Positional | Value matched by position | `student("Gaurav", 40)` |
| Keyword | Value matched by parameter name | `student(name="Gaurav", age=40)` |

Positional arguments must come before keyword arguments.

Correct:

```python
student("Gaurav", age=40)
```

Incorrect:

```python
student(name="Gaurav", 40)
```

---

# 13. Arbitrary Positional Arguments — `*args`

## What?

`*args` allows a function to receive any number of positional arguments.

```python
def add(*numbers):
    total = 0

    for number in numbers:
        total += number

    return total

print(add(10, 20))
print(add(10, 20, 30))
print(add(1, 2, 3, 4, 5))
```

Output:

```text
30
60
15
```

Inside the function, `numbers` behaves like a tuple.

```python
def show(*args):
    print(args)

show(10, 20, 30)
```

Output:

```text
(10, 20, 30)
```

---

# 14. Arbitrary Keyword Arguments — `**kwargs`

## What?

`**kwargs` allows a function to receive any number of keyword arguments.

```python
def student(**details):
    print(details)

student(name="Gaurav", age=40, city="Jaipur")
```

Output:

```text
{'name': 'Gaurav', 'age': 40, 'city': 'Jaipur'}
```

Inside the function, `details` behaves like a dictionary.

```python
def student(**details):
    print(details["name"])
    print(details["city"])

student(name="Gaurav", age=40, city="Jaipur")
```

Output:

```text
Gaurav
Jaipur
```

---

# 15. `*args` vs `**kwargs`

| Feature | `*args` | `**kwargs` |
|---|---|---|
| Accepts | Multiple positional arguments | Multiple keyword arguments |
| Inside function | Tuple | Dictionary |
| Example | `fun(10, 20, 30)` | `fun(a=10, b=20)` |

---

# 16. Local Variable in Function

A variable created inside a function is generally a local variable.

```python
def greet():
    name = "Gaurav"
    print(name)

greet()
```

Here `name` is local to the function.

It cannot normally be accessed outside:

```python
def greet():
    name = "Gaurav"

greet()

print(name)
```

This raises:

```text
NameError
```

---

# 17. Global Variable

A variable created outside a function is a global variable.

```python
name = "Gaurav"

def greet():
    print(name)

greet()
```

Output:

```text
Gaurav
```

The function can read the global variable.

---

# 18. `global` Keyword

If you want to modify a global variable inside a function, use `global`.

```python
x = 10

def change():
    global x
    x = 20

change()

print(x)
```

Output:

```text
20
```

Without `global`, an assignment such as `x = 20` inside the function creates a local variable instead.

---

# 19. Multiple Return Values

Python can return multiple values.

```python
def calculate(a, b):
    addition = a + b
    subtraction = a - b

    return addition, subtraction

result1, result2 = calculate(10, 5)

print(result1)
print(result2)
```

Output:

```text
15
5
```

Python returns the values together as a tuple.

---

# 20. Function Calling Another Function

A function can call another function.

```python
def add(a, b):
    return a + b

def show_result():
    result = add(10, 20)
    print(result)

show_result()
```

Output:

```text
30
```

---

# 21. Function with Conditions

Functions can contain conditional statements.

```python
def check_age(age):

    if age >= 18:
        return "Adult"
    else:
        return "Minor"

print(check_age(25))
print(check_age(15))
```

Output:

```text
Adult
Minor
```

---

# 22. Function with Loop

Functions can also contain loops.

```python
def print_numbers(n):

    for i in range(1, n + 1):
        print(i)

print_numbers(5)
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

# 23. Docstring

## What?

A **docstring** is a string used to document what a function does.

It is written immediately inside the function.

```python
def add(a, b):
    "Return the sum of two numbers."
    return a + b
```

You can access it using:

```python
print(add.__doc__)
```

Output:

```text
Return the sum of two numbers.
```

---

# 24. Built-in vs User-defined Functions

## Built-in Functions

Python already provides many functions:

```python
print()
len()
type()
int()
float()
str()
sum()
max()
min()
```

Example:

```python
numbers = [10, 20, 30]

print(len(numbers))
print(sum(numbers))
```

Output:

```text
3
60
```

## User-defined Functions

Functions created by the programmer:

```python
def greet():
    print("Hello")
```

---

# 25. Recursive Function

## What?

A function that calls itself is called a **recursive function**.

```python
def countdown(n):

    if n == 0:
        return

    print(n)
    countdown(n - 1)

countdown(5)
```

Output:

```text
5
4
3
2
1
```

A recursive function needs a **base condition** to stop recursion.

---

# 26. Function Naming

Use meaningful function names.

Good:

```python
calculate_total()
get_student()
check_login()
calculate_average()
```

Avoid unclear names such as:

```python
x()
abc()
fun1()
```

Python commonly uses `snake_case` for function names.

---

# 27. Function Anatomy

Consider:

```python
def calculate_total(price, quantity=1):
    total = price * quantity
    return total
```

Breakdown:

```text
def
↓
Function definition keyword

calculate_total
↓
Function name

price, quantity
↓
Parameters

quantity=1
↓
Default parameter

total = price * quantity
↓
Function body

return total
↓
Return statement
```

Call:

```python
result = calculate_total(500, 3)

print(result)
```

Output:

```text
1500
```

---

# 28. Common Function Errors

## Missing Parentheses During Call

```python
def greet():
    print("Hello")

greet()
```

Correct.

Writing:

```python
greet
```

refers to the function object; it does not call the function.

## Wrong Number of Arguments

```python
def add(a, b):
    return a + b

add(10)
```

This raises `TypeError` because `b` is missing.

## Local Variable Outside Function

```python
def test():
    x = 10

test()

print(x)
```

This raises `NameError` because `x` is local to `test()`.

---

# Quick Revision

| Concept | Meaning |
|---|---|
| Function | Reusable block of code |
| `def` | Defines a function |
| Function call | Executes a function |
| Parameter | Variable in function definition |
| Argument | Value passed during function call |
| `return` | Sends a value back |
| Default parameter | Parameter with a default value |
| Positional argument | Argument matched by position |
| Keyword argument | Argument matched by name |
| `*args` | Multiple positional arguments |
| `**kwargs` | Multiple keyword arguments |
| Local variable | Variable inside a function |
| Global variable | Variable outside functions |
| Docstring | Documentation for a function |
| Recursion | Function calling itself |

# Function Flow

```text
Define Function
      ↓
Call Function
      ↓
Arguments passed
      ↓
Parameters receive values
      ↓
Function body executes
      ↓
return value
      ↓
Result received
```

# Key Points to Remember

- A function is a reusable block of code.
- Use `def` to define a function.
- Defining a function does not execute its body.
- Call the function using `function_name()`.
- Parameters are variables in the function definition.
- Arguments are actual values passed to the function.
- `return` sends a result back to the caller.
- A function without an explicit `return` returns `None`.
- Default parameters provide fallback values.
- Positional arguments depend on position.
- Keyword arguments use parameter names.
- `*args` accepts multiple positional arguments.
- `**kwargs` accepts multiple keyword arguments.
- Variables created inside functions are generally local.
- Global variables are created outside functions.
- Use `global` when you need to assign to a global variable inside a function.
- Functions can contain conditions, loops, and calls to other functions.
- A recursive function calls itself and needs a stopping condition.

# One-Line Definition

> **Function = A reusable block of code designed to perform a specific task.**
