# Python Learning Notes

This file brings together the main ideas covered in the Python learning notebooks, including strings, loops, classes, and exception handling.

## 1. Comments and readability

Comments help explain code and make it easier to understand later.

```python
# This comment explains the next line of code.
print("Hello, World!")
```

Good comments usually explain the purpose or reason behind a step, not just what the syntax does.

## 2. Strings

Strings are text values enclosed in quotes.

```python
Name = "The BodyGuard"
Name[0:5]   # 'The '
Name[::2]   # every second character
```

Useful string tools:

- `s[start:stop]` for slicing
- `split()` to split into parts
- `find(sub)` to search for a value

## 3. Lists

Lists are ordered and mutable collections.

```python
my_first_list = ['Hello World', 42, 3.14, True]
A = ['disco', 10, 1.2]
A[0] = 'Hello World!'
```

Important list operations:

- `append(x)` adds one element
- `extend(iterable)` adds multiple elements
- `pop()` removes the last element

## 4. Tuples

Tuples are immutable sequences.

```python
t = (1, 2, 3)
```

They are useful when the data should not change after creation.

## 5. Dictionaries

Dictionaries store data as key-value pairs.

```python
d = {'a': 1, 'b': 2}
```

Useful operations:

- `d[key]` access a value
- `d.get(key, default)` safe lookup
- `d[new_key] = value` add or update
- `del d[key]` remove a key

## 6. Sets

Sets store unique values.

```python
s = {1, 2, 3}
t = set([1, 2, 2, 3])  # {1, 2, 3}
```

Important notes:

- order is not guaranteed
- duplicates are removed automatically
- elements must be hashable

## 7. Expressions and variables

Python evaluates expressions in a predictable order.

```python
30 + 2 * 60   # 150
(30 + 2) * 60 # 1920
```

The parentheses change the order of operations, so they can change the final value.

## 8. Loops

Loops help repeat actions without writing the same code multiple times.

### For loops

```python
dates = [2020, 2021, 2022]
N = len(dates)
for i in range(N):
    print(dates[i])
```

This uses the index position to access each item in the list.

### Range

```python
for i in range(0, 8):
    print(i)
```

Python's `range(start, stop)` starts at the first value and stops before the last value.

### Enumerate

```python
squares = ['red', 'blue', 'green', 'yellow', 'purple']
for i, color in enumerate(squares):
    print(i, color)
```

This gives both the index and the current value in the loop.

### While loops

```python
count = 1
while count <= 5:
    print(count)
    count += 1
```

A `while` loop keeps running as long as the condition is true.

## 9. Exception handling

Exceptions are errors that happen while a program is running. Python can catch them with `try` and `except`.

```python
try:
    1 / 0
except Exception as e:
    print(type(e).__name__, "-", e)
```

Other examples from the notebook include:

- `NameError` from using an undefined variable
- `IndexError` when accessing an invalid list index
- `ZeroDivisionError` when dividing by zero

A full example with matching messages:

```python
a = 1

try:
    b = int(input("Enter a number: "))
    c = a / b
except ZeroDivisionError:
    print("Can't divide by Zero")
except ValueError:
    print("Please enter a valid number")
except:
    print("Some other error occurred")
else:
    print("The result is", c)
finally:
    print("This will always execute")
```

The `else` block runs only if no exception occurs. The `finally` block always runs.

## 10. Classes and objects

A class is a blueprint for creating objects.

```python
class Circle(object):
    def __init__(self, radius=3, color='blue'):
        self.radius = radius
        self.color = color

    def add_radius(self, r):
        self.radius += r
```

When we create an instance, we can store information inside it and call methods on it.

```python
RedCircle = Circle(10, 'red')
print(RedCircle.radius)
RedCircle.add_radius(7)
```

This example shows how objects can hold state and behave through methods.

## 11. Testing with pytest

Tests check whether the code behaves as expected.

```python
from src.hello_world import main


def test_main(capsys):
    main()
    captured = capsys.readouterr()
    assert captured.out.strip() == "Hello, World!"
```

This pattern captures printed output and compares it with the expected string.

## 12. Summary

The main ideas from the notebooks are:

- use comments to make code easier to read
- understand data types such as strings, lists, tuples, dictionaries, and sets
- repeat work with loops
- catch errors with `try` and `except`
- organize code with classes and objects
- verify behavior with tests

This is a solid beginner foundation for Python learning and practice.
