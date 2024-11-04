# Accretion Linux Coding Style Guide

## Table of Contents

1. Introduction
2. General Guidelines
3. C/C++ Style Guide
4. Python Style Guide
5. Shell Script Style Guide
6. Commit Message Guidelines
7. Documentation Style
8. Naming Conventions
9. Error Handling
10. Testing Guidelines

## 1. Introduction

This document outlines the coding standards and best practices for contributing to Accretion Linux. Adhering to these guidelines ensures consistency across the project and makes the codebase more maintainable.

## 2. General Guidelines

- Use UTF-8 encoding for all source files.
- Use spaces for indentation, not tabs.
- Keep lines to a maximum of 80 characters where possible.
- Remove trailing whitespace from all lines.
- End files with a single newline character.

## 3. C/C++ Style Guide

- Follow the [Linux kernel coding style](https://www.kernel.org/doc/html/latest/process/coding-style.html) for C code.
- For C++ code, follow the [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html) with the following exceptions:
  - Use 4 spaces for indentation instead of 2.
  - Prefer `nullptr` to `NULL` or `0`.

Example:

```c
#include <stdio.h>

int main(void)
{
    if (condition) {
        do_something();
    } else {
        do_something_else();
    }
    return 0;
}
```

## 4. Python Style Guide

Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) with these additional guidelines:

- Use 4 spaces for indentation.
- Use double quotes for strings unless single quotes avoid backslashes.
- Use f-strings for string formatting when possible.

Example:

```python
def example_function(arg1, arg2):
    """Docstring for function."""
    if arg1 == arg2:
        return True
    return False

class ExampleClass:
    """Docstring for class."""

    def __init__(self, value):
        self.value = value

    def get_value(self):
        return f"The value is {self.value}"
```

## 5. Shell Script Style Guide

- Follow the [Google Shell Style Guide](https://google.github.io/styleguide/shellguide.html).
- Use `#!/bin/bash` for bash scripts, `#!/bin/sh` for POSIX sh scripts.
- Use 4 spaces for indentation.

Example:

```bash
#!/bin/bash

if [ "$1" = "test" ]; then
    echo "Running test"
    run_tests
else
    echo "Usage: $0 test"
    exit 1
fi
```

## 6. Commit Message Guidelines

- Use the present tense ("Add feature" not "Added feature").
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...").
- Limit the first line to 72 characters or less.
- Reference issues and pull requests liberally after the first line.

Example:

```
Add support for IPv6 in network manager

- Implement IPv6 address configuration
- Update network tests for IPv6 support
- Update documentation

Fixes #123
```

## 7. Documentation Style

- Use Markdown for documentation files.
- Keep lines in documentation files to a maximum of 80 characters.
- Use code blocks with language specification for code examples.

## 8. Naming Conventions

- Use snake_case for C function and variable names.
- Use PascalCase for C++ class names, camelCase for method names.
- Use snake_case for Python function, method, and variable names.
- Use PascalCase for Python class names.
- Use UPPER_CASE for constants in all languages.

## 9. Error Handling

- Always check return values and handle potential errors.
- Use exceptions for exceptional conditions in C++ and Python.
- Provide meaningful error messages.

## 10. Testing Guidelines

- Write unit tests for all new functionality.
- Aim for at least 80% code coverage in unit tests.
- Write integration tests for complex interactions between components.
- Ensure all tests pass before submitting a pull request.

Remember, while coding style is important, readability and maintainability are paramount. Use your best judgment, and don't hesitate to ask for guidance on the project's communication channels.

