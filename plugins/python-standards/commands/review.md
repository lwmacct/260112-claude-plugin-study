Review the selected Python code according to PEP 8 and Python best practices:

**Check for:**

1. **PEP 8 Compliance**
   - Maximum line length of 79 characters (or 99 for modern projects)
   - Import order: standard library, third-party, local
   - Two blank lines before functions/classes, one before methods
   - Spaces around operators (except after opening parenthesis)
   - No trailing whitespace

2. **Naming Conventions (PEP 8)**
   - `snake_case` for functions, variables, and module names
   - `PascalCase` (CapWords) for classes
   - `UPPER_CASE` for constants
   - `_leading_underscore` for "internal" use
   - `__dunder__` for magic methods only

3. **Type Hints (PEP 484)**
   - All public functions should have type hints
   - Use `typing` module for complex types (`List`, `Dict`, `Optional`, etc.)
   - Return type should always be specified
   - Use `from __future__ import annotations` for forward references

4. **Error Handling**
   - Catch specific exceptions, not bare `except:`
   - Use `finally` for cleanup code
   - Include error context in messages
   - Prefer exception chaining (`raise ... from e`)

5. **Code Organization**
   - One class per file (usually)
   - Keep functions focused and small (< 50 lines)
   - Use docstrings (Google, NumPy, or reStructuredText style)
   - Group related code together

6. **Pythonic Idioms**
   - Use list comprehensions instead of `map`/`filter` with lambda
   - Use `with` statements for resource management
   - Use `enumerate()` instead of manual index tracking
   - Use context managers (`@contextmanager` when appropriate)
   - Prefer dataclasses over `__init__` boilerplate
   - Use f-strings for formatting (Python 3.6+)

7. **Security Issues**
   - Avoid `eval()` and `exec()` on user input
   - Use `subprocess.run()` instead of `os.system()`
   - Sanitize input for SQL queries (use parameterized queries)
   - Check for hardcoded secrets/credentials

8. **Common Anti-patterns**
   - Using mutable default arguments (`def foo(x=[])`)
   - Not closing files/connections properly
   - Overusing `*` imports (`from module import *`)
   - Redundant parentheses in conditions

**Provide feedback in this format:**
```
❌ PEP8: [Violation description]
   Location: [file:line]
   Why: [Explanation of guideline]
   Fix: [Suggested fix with example]

⚠️ PEP 257: [Docstring issue]
   Location: [file:line]
   Fix: [Docstring example]

🔒 SECURITY: [Security concern]
   Location: [file:line]
   Why: [Explanation of risk]
   Fix: [Secure alternative]
```

Focus on PEP 8 violations first, then quality improvements.
