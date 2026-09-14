# Python Learning Journey

This repository contains my beginner Python notes, scripts, and learning files as I continue to build my understanding of the language.

## Project Structure

```text
Python Learning/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   ├── first_program.ipynb
│   ├── string_examples.ipynb      # String slicing, split, find, and help() examples
│   ├── types_example.ipynb        # Examples showing Python types: int, float, str
│   └── variable_expression.examples.ipynb  # Expressions, operator precedence, and variables
├── notes/
│   └── learning_notes.md
├── src/
│   ├── __init__.py
│   └── hello_world.py
├── tests/
│   └── test_hello_world.py
├── docs/
│   └── roadmap.md
└── .git/
```

## Purpose
The goal of this repository is to:
- learn Python fundamentals
- practice coding basics
- keep track of what I am learning
- organize my learning materials in a simple structure
- build confidence in writing small Python programs

## How to Run
```bash
python3 src/hello_world.py
```

## How to Test
```bash
pytest
```

## Current Focus
- Python syntax
- Comments and documentation
- Variables and values
- Output using print()
- Basic debugging and error understanding
- Git and GitHub basics

## Status
In progress - learning and practicing Python fundamentals.

## Portfolio Summary

- Short summary of contents: interactive notebooks demonstrating basic Python concepts (strings, lists, variables, expressions) and a small example script under `src/`.
- See `notes/learning_notes.md` for detailed concept notes and runnable snippets.
- How to run:
	```bash
	python3 src/hello_world.py
	python3 -m pytest -q
	```

## Sample Output

Run the example script:
```bash
python3 src/hello_world.py
```
Expected output:
```text
Hello, World\!
```

Run the tests:
```bash
python3 -m pytest -q
```
Example test output:
```text
.                                                                        [100%]
1 passed in 0.00s
```
