# Python Exception Handling Notes

## WWH Model: What → Why → When → How

---

# 1. Exception Handling

## What is Exception Handling?

Exception Handling is the process of handling **runtime errors** in a Python program so that the program does not terminate unexpectedly.

### Example

```python
a = 10
b = 0

print(a / b)
```

Output:

```text
ZeroDivisionError: division by zero
```

Without exception handling, the program stops.

---

## Why use Exception Handling?

Exception handling is used to:

- Prevent sudden program termination
- Handle runtime errors gracefully
- Show user-friendly error messages
- Continue program execution when possible
- Handle invalid user input
- Handle file/database/network errors
- Make applications more reliable

---

## When should we use Exception Handling?

Use exception handling when an operation can fail at runtime.

Examples:

- User enters invalid input
- Division by zero
- File does not exist
- Dictionary key is missing
- List index is invalid
- Invalid type conversion
- Database/API operation fails

---

# 2. Error vs Exception

## What?

An **error** is a problem in a program.

An **exception** is an event raised during program execution that can usually be handled.

### Example

```python
print(10 / 0)
```

Python raises:

```text
ZeroDivisionError
```

---

# 3. Common Python Exceptions

| Exception | Meaning |
|---|---|
| `ZeroDivisionError` | Division by zero |
| `ValueError` | Invalid value |
| `TypeError` | Invalid operation between incompatible types |
| `NameError` | Variable/name does not exist |
| `IndexError` | Invalid list/tuple index |
| `KeyError` | Dictionary key does not exist |
| `FileNotFoundError` | File does not exist |
| `AttributeError` | Object does not have the requested attribute |
| `ImportError` | Import-related problem |
| `ModuleNotFoundError` | Module cannot be found |

---

# 4. try and except

## What?

`try` contains code that may generate an exception.

`except` handles the exception.

## Syntax

```python
try:
    # risky code
except:
    # error handling code
```

## Example

```python
try:
    print(10 / 0)
except:
    print("Something went wrong")
```

Output:

```text
Something went wrong
```

---

# 5. Handling a Specific Exception

## What?

Instead of catching every exception, we can catch a specific exception.

## Example

```python
try:
    print(10 / 0)
except ZeroDivisionError:
    print("Cannot divide by zero")
```

Output:

```text
Cannot divide by zero
```

### Why is this better?

It makes the program more predictable and easier to debug.

---

# 6. Multiple except Blocks

## What?

We can use multiple `except` blocks to handle different exceptions differently.

## Example

```python
try:
    number = int(input("Enter number: "))
    result = 10 / number
    print(result)

except ValueError:
    print("Please enter a valid number")

except ZeroDivisionError:
    print("Number cannot be zero")
```

### Possible outputs

If user enters:

```text
abc
```

Output:

```text
Please enter a valid number
```

If user enters:

```text
0
```

Output:

```text
Number cannot be zero
```

---

# 7. try-except with User Input

## Example

```python
try:
    age = int(input("Enter your age: "))
    print("Age:", age)

except ValueError:
    print("Invalid age")
```

### Input

```text
25
```

Output:

```text
Age: 25
```

### Input

```text
abc
```

Output:

```text
Invalid age
```

---

# 8. else with Exception Handling

## What?

The `else` block executes **only when no exception occurs** in the `try` block.

## Syntax

```python
try:
    # risky code
except:
    # error
else:
    # success
```

## Example

```python
try:
    a = int(input("Enter number: "))
    print(100 / a)

except ValueError:
    print("Invalid number")

except ZeroDivisionError:
    print("Cannot divide by zero")

else:
    print("Operation successful")
```

### Input

```text
20
```

Output:

```text
5.0
Operation successful
```

---

# 9. finally

## What?

`finally` executes **whether an exception occurs or not**.

## Syntax

```python
try:
    # code
except:
    # error handling
finally:
    # always executes
```

## Example

```python
try:
    print(10 / 2)

except ZeroDivisionError:
    print("Cannot divide by zero")

finally:
    print("This always executes")
```

Output:

```text
5.0
This always executes
```

### Example with an error

```python
try:
    print(10 / 0)

except ZeroDivisionError:
    print("Cannot divide by zero")

finally:
    print("Program finished")
```

Output:

```text
Cannot divide by zero
Program finished
```

---

# 10. Complete try-except-else-finally

## Syntax

```python
try:
    # risky code

except SomeException:
    # handle exception

else:
    # executes when no exception occurs

finally:
    # always executes
```

## Example

```python
try:
    num = int(input("Enter number: "))
    result = 100 / num

except ValueError:
    print("Invalid input")

except ZeroDivisionError:
    print("Cannot divide by zero")

else:
    print("Result:", result)

finally:
    print("Execution completed")
```

---

# 11. Catching Exception Object

## What?

We can store the exception object using `as`.

## Syntax

```python
except Exception as e:
```

## Example

```python
try:
    print(10 / 0)

except Exception as e:
    print("Error:", e)
```

Output:

```text
Error: division by zero
```

### Another example

```python
try:
    number = int("hello")

except Exception as e:
    print("Error:", e)
```

Output:

```text
Error: invalid literal for int() with base 10: 'hello'
```

---

# 12. Exception Hierarchy

Python exceptions are organized in a hierarchy.

A simplified structure:

```text
BaseException
    |
    +-- Exception
          |
          +-- ArithmeticError
          |      |
          |      +-- ZeroDivisionError
          |
          +-- LookupError
          |      |
          |      +-- IndexError
          |      +-- KeyError
          |
          +-- ValueError
          +-- TypeError
          +-- OSError
                 |
                 +-- FileNotFoundError
```

Most application-level exceptions should be handled through `Exception` or a specific subclass.

---

# 13. Generic Exception Handling

## Example

```python
try:
    a = int(input("Enter number: "))
    print(100 / a)

except Exception as e:
    print("Error:", e)
```

This can catch many normal runtime exceptions.

### Important

Prefer a **specific exception** when you know what can go wrong.

Better:

```python
except ValueError:
```

Instead of unnecessarily using:

```python
except Exception:
```

---

# 14. raise Keyword

## What?

`raise` is used to **manually generate an exception**.

## Syntax

```python
raise Exception("message")
```

## Example

```python
age = 15

if age < 18:
    raise ValueError("Age must be 18 or above")
```

Output:

```text
ValueError: Age must be 18 or above
```

---

# 15. raise with try-except

```python
try:
    age = int(input("Enter age: "))

    if age < 18:
        raise ValueError("Age must be 18 or above")

    print("Eligible")

except ValueError as e:
    print("Error:", e)
```

### Input

```text
15
```

Output:

```text
Error: Age must be 18 or above
```

---

# 16. Custom Exception

## What?

We can create our own exception class by inheriting from `Exception`.

## Example

```python
class AgeError(Exception):
    pass
```

Use it:

```python
age = 15

try:
    if age < 18:
        raise AgeError("Age must be 18 or above")

except AgeError as e:
    print(e)
```

Output:

```text
Age must be 18 or above
```

---

# 17. Custom Exception with Function

```python
class InsufficientBalanceError(Exception):
    pass


def withdraw(balance, amount):

    if amount > balance:
        raise InsufficientBalanceError("Insufficient balance")

    return balance - amount


try:
    balance = withdraw(5000, 7000)
    print("Remaining balance:", balance)

except InsufficientBalanceError as e:
    print("Error:", e)
```

Output:

```text
Error: Insufficient balance
```

---

# 18. Nested Exception Handling

## What?

An `try-except` block can exist inside another `try-except` block.

## Example

```python
try:

    try:
        number = int(input("Enter number: "))
        print(100 / number)

    except ValueError:
        print("Invalid number")

except ZeroDivisionError:
    print("Cannot divide by zero")
```

---

# 19. Exception Handling inside a Function

```python
def divide(a, b):

    try:
        return a / b

    except ZeroDivisionError:
        return "Cannot divide by zero"


print(divide(10, 2))
print(divide(10, 0))
```

Output:

```text
5.0
Cannot divide by zero
```

---

# 20. Exception Handling with Loops

## Example

```python
while True:

    try:
        number = int(input("Enter number: "))
        print("You entered:", number)
        break

    except ValueError:
        print("Invalid input. Try again.")
```

This is useful for repeatedly asking the user until valid input is provided.

---

# 21. Exception Handling with Lists

```python
numbers = [10, 20, 30]

try:
    print(numbers[5])

except IndexError:
    print("Index does not exist")
```

Output:

```text
Index does not exist
```

---

# 22. Exception Handling with Dictionary

```python
student = {
    "name": "Rahul",
    "age": 22
}

try:
    print(student["marks"])

except KeyError:
    print("Marks key does not exist")
```

Output:

```text
Marks key does not exist
```

---

# 23. Exception Handling with File

```python
try:
    file = open("data.txt", "r")
    data = file.read()
    print(data)

except FileNotFoundError:
    print("File not found")
```

Output if the file does not exist:

```text
File not found
```

### Better approach

Use `with open()` so the file is automatically closed:

```python
try:
    with open("data.txt", "r") as file:
        data = file.read()
        print(data)

except FileNotFoundError:
    print("File not found")
```

---

# 24. Common Exception Examples

## ZeroDivisionError

```python
try:
    print(10 / 0)
except ZeroDivisionError:
    print("Cannot divide by zero")
```

---

## ValueError

```python
try:
    age = int("abc")
except ValueError:
    print("Invalid value")
```

---

## TypeError

```python
try:
    print(10 + "20")
except TypeError:
    print("Cannot add integer and string")
```

---

## IndexError

```python
try:
    numbers = [10, 20]
    print(numbers[5])
except IndexError:
    print("Invalid index")
```

---

## KeyError

```python
try:
    data = {"name": "Rahul"}
    print(data["age"])
except KeyError:
    print("Key does not exist")
```

---

## FileNotFoundError

```python
try:
    open("abc.txt")
except FileNotFoundError:
    print("File does not exist")
```

---

# 25. Common Mistake: Bare except

### Possible

```python
try:
    print(10 / 0)
except:
    print("Error")
```

### Better

```python
try:
    print(10 / 0)
except ZeroDivisionError:
    print("Cannot divide by zero")
```

Specific exceptions make debugging easier.

---

# 26. Common Mistake: Catching Everything

Avoid unnecessarily doing:

```python
try:
    # large amount of code
except Exception:
    print("Something went wrong")
```

Prefer:

```python
try:
    number = int(input("Enter number: "))

except ValueError:
    print("Invalid number")
```

Keep the `try` block as small as practical.

---

# 27. Common Mistake: Empty except

Avoid:

```python
try:
    risky_operation()

except:
    pass
```

This silently ignores the error.

It can make debugging very difficult.

---

# 28. try vs if

Not every condition needs exception handling.

### Use `if` for expected conditions

```python
age = 20

if age >= 18:
    print("Adult")
```

### Use exception handling for exceptional runtime failures

```python
try:
    number = int(input("Enter number: "))
except ValueError:
    print("Invalid input")
```

---

# 29. Exception Handling Flow

```text
            try
              |
              v
       Exception occurs?
          /        \
        Yes         No
         |           |
         v           v
      except       else
         \           /
          \         /
           v       v
             finally
                |
                v
             Continue
```

---

# 30. Real-Life Example: Login

```python
correct_password = "python123"

try:
    password = input("Enter password: ")

    if password != correct_password:
        raise ValueError("Incorrect password")

    print("Login successful")

except ValueError as e:
    print("Login failed:", e)

finally:
    print("Login process completed")
```

---

# 31. Real-Life Example: ATM Withdrawal

```python
class InsufficientBalanceError(Exception):
    pass


balance = 10000

try:
    amount = int(input("Enter withdrawal amount: "))

    if amount <= 0:
        raise ValueError("Amount must be greater than zero")

    if amount > balance:
        raise InsufficientBalanceError("Insufficient balance")

    balance -= amount

except ValueError as e:
    print("Invalid amount:", e)

except InsufficientBalanceError as e:
    print("Transaction failed:", e)

else:
    print("Withdrawal successful")
    print("Remaining balance:", balance)

finally:
    print("Thank you for using ATM")
```

---

# 32. Real-Life Example: Student Marks

```python
try:
    marks = int(input("Enter marks: "))

    if marks < 0 or marks > 100:
        raise ValueError("Marks must be between 0 and 100")

    print("Valid marks:", marks)

except ValueError as e:
    print("Error:", e)
```

---

# 33. Exception Handling Best Practices

1. Catch specific exceptions.
2. Keep `try` blocks small.
3. Use meaningful error messages.
4. Use `finally` for cleanup operations.
5. Use `raise` when validation should generate an exception.
6. Create custom exceptions for application-specific errors.
7. Do not silently ignore exceptions.
8. Do not use exception handling as a replacement for normal program logic.
9. Preserve useful error information while debugging.
10. Validate user input properly.

---

# 34. Quick Revision

| Keyword | Purpose |
|---|---|
| `try` | Code that may cause an exception |
| `except` | Handles an exception |
| `else` | Runs when no exception occurs |
| `finally` | Runs whether exception occurs or not |
| `raise` | Manually raises an exception |
| `Exception` | Base class for most application exceptions |

---

# 35. Exception Handling Syntax Cheat Sheet

### Basic

```python
try:
    # code
except:
    # error handling
```

### Specific exception

```python
try:
    # code
except ValueError:
    # handle error
```

### Exception object

```python
try:
    # code
except Exception as e:
    print(e)
```

### Multiple exceptions

```python
try:
    # code
except ValueError:
    # handle ValueError
except ZeroDivisionError:
    # handle ZeroDivisionError
```

### else

```python
try:
    # code
except:
    # error
else:
    # success
```

### finally

```python
try:
    # code
except:
    # error
finally:
    # always executes
```

### Raise

```python
raise ValueError("Invalid value")
```

### Custom exception

```python
class MyError(Exception):
    pass
```

---

# 36. One-Line Definitions

- **Exception:** Runtime event that interrupts normal program execution.
- **Exception Handling:** Technique used to handle runtime exceptions gracefully.
- **try:** Contains code that may raise an exception.
- **except:** Handles an exception.
- **else:** Executes when the `try` block completes without an exception.
- **finally:** Executes regardless of whether an exception occurred.
- **raise:** Manually generates an exception.
- **Custom Exception:** User-defined exception class created by inheriting from `Exception`.

---

# 37. Final Example

```python
class InsufficientBalanceError(Exception):
    pass


def withdraw(balance, amount):

    if amount <= 0:
        raise ValueError("Amount must be greater than zero")

    if amount > balance:
        raise InsufficientBalanceError("Insufficient balance")

    return balance - amount


try:

    balance = 10000
    amount = int(input("Enter withdrawal amount: "))

    balance = withdraw(balance, amount)

except ValueError as e:
    print("Invalid input:", e)

except InsufficientBalanceError as e:
    print("Transaction failed:", e)

else:
    print("Transaction successful")
    print("Remaining balance:", balance)

finally:
    print("Transaction process completed")
```

This example combines:

- `try`
- Multiple `except`
- `else`
- `finally`
- `raise`
- Custom exception
- Function
- Input validation
