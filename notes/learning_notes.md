# Learning Notes

## Strings

- Slicing: `s[start:stop]` returns characters from `start` up to (but not including) `stop`.
	```python
	Name = "The BodyGuard"
	Name[0:5]  # 'The '
	Name[::2]  # every second character
	```

- Useful methods:
	- `split()` — splits a string into a list of words.
	- `find(sub)` — returns the starting index of `sub` or `-1` if not found.

## Lists

- Creation: lists can hold mixed types.
	```python
	my_first_list = ['Hello World', 42, 3.14, True]
	```

- Mutability: lists are mutable — assign by index to update a value.
	```python
	A = ['disco', 10, 1.2]
	A[0] = 'Hello World!'
	```

- `append()` vs `extend()`:
	- `append(x)` adds `x` as a single element.
	- `extend(iterable)` adds each element from `iterable` individually.
	```python
	L = ['Michael Jackson', 10.2]
	L.extend(['pop', 10])   # ['Michael Jackson', 10.2, 'pop', 10]
	L.append(['pop1', 11])  # last element is the list ['pop1', 11]
	```

- Slicing and nested lists: access nested elements with additional indices, use slice notation for sublists.

## Tuples

- Tuples are immutable ordered sequences, created with parentheses: `t = (1, 2, 3)`.

## Dictionaries

- Dictionaries store key-value pairs and are created with curly braces: `d = {'a': 1, 'b': 2}`.

- Key requirements:
	- Keys must be hashable (immutable types like strings, numbers, or tuples). Mutable types like lists cannot be used as keys.

- Common operations:
	- Access: `d[key]` returns the value for `key` (KeyError if missing).
	- Safe access: `d.get(key, default)` returns `default` when `key` is absent.
	- Add/update: `d[new_key] = value` sets or updates a mapping.
	- Delete: `del d[key]` removes the key-value pair.

- Useful views and methods:
	- `d.keys()` — view of all keys
	- `d.values()` — view of all values
	- `d.items()` — view of (key, value) pairs useful for iteration
	- `d.clear()` — remove all items
	- `d.pop(key[, default])` — remove and return value, or return default if provided

- Iteration patterns:
	- `for k in d:` iterates keys
	- `for v in d.values():` iterates values
	- `for k, v in d.items():` iterates both

- Comprehension example:
	```python
	squares = {n: n*n for n in range(6)}  # {0:0, 1:1, 2:4, ...}
	```

- Common pitfalls:
	- Using mutable objects as keys raises `TypeError`.
	- Modifying a dictionary while iterating its keys can lead to runtime errors — iterate over a static list like `list(d.keys())` when mutating.

## Sets

- A *set* is an unordered collection of unique, hashable elements. Use curly braces or the `set()` constructor.

- Creation examples:
	```python
	s = {1, 2, 3}
	t = set([1, 2, 2, 3])  # duplicates removed -> {1, 2, 3}
	```

- Common methods and operations:
	- `add(elem)`, `remove(elem)`, `discard(elem)` (no error if absent), `pop()`
	- `union(other)`, `intersection(other)`, `difference(other)`, `symmetric_difference(other)`
	- `issubset(other)`, `issuperset(other)`, `isdisjoint(other)`

- Membership test is efficient (average O(1)): `elem in s`.

- Set comprehensions:
	```python
	evens = {n for n in range(10) if n % 2 == 0}
	```

- Important notes:
	- Elements must be hashable; lists cannot be elements but tuples can.
	- Sets are unordered; do not rely on element order.
	- Use `frozenset` for an immutable, hashable set suitable as a dictionary key.


## Expressions and Variables

- Arithmetic operators: `+ - * / //` (floor division). Parentheses alter precedence.
	```python
	30 + 2 * 60   # 150
	(30 + 2) * 60 # 1920
	```

## Testing (pytest)

- Capturing stdout example pattern:
	```python
	from src.hello_world import main

	def test_main(capsys):
			main()
			captured = capsys.readouterr()
			assert captured.out.strip() == "Hello, World\\!"
	```

