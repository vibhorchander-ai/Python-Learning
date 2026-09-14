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

