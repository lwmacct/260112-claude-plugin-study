Check Python docstrings for completeness and style (PEP 257):

**Docstring Checks:**

1. **Presence Check**
   - All public modules, classes, functions, and methods should have docstrings
   - Docstrings should be the first statement in the definition
   - Use triple double quotes (`"""`), not single quotes

2. **Style Guide** (Choose one convention per project)
   - **Google Style** (Recommended for readability)
   - **NumPy Style** (Good for scientific code)
   - **reStructuredText** (Sphinx default)

3. **Google Style Examples**
   ```python
   def calculate_distance(point1: tuple[float, float],
                         point2: tuple[float, float]) -> float:
       """Calculate the Euclidean distance between two points.

       Args:
           point1: The first (x, y) coordinate pair.
           point2: The second (x, y) coordinate pair.

       Returns:
           The distance between the two points.

       Raises:
           ValueError: If either point is not a 2D coordinate.
       """
       ...
   ```

4. **One-Line Docstrings**
   ```python
   def foo() -> None:
       """Do something simple."""
       pass
   ```
   - Closing quotes on same line
   - Complete sentence with period
   - Imperative mood ("Do", not "Does")

5. **Module-Level Docstrings**
   ```python
   """
   This module provides utilities for data processing.

   It includes functions for:
   - Reading CSV files
   - Cleaning data
   - Exporting to various formats
   """
   ```

6. **Class Docstrings**
   ```python
   class DataProcessor:
       """Process and transform data.

       This class handles various data transformation operations
       including filtering, aggregation, and formatting.

       Attributes:
           data: The input dataset to process.
           config: Configuration options for processing.
       """
   ```

7. **Common Issues**
   - ❌ Missing docstring on public API
   - ❌ Inconsistent style within project
   - ❌ Not documenting parameters or return values
   - ❌ Missing Raises section for exceptions
   - ❌ Copy-pasted docstrings that don't match implementation

8. **What to Document**
   - **Functions**: What it does, parameters, return value, exceptions raised
   - **Classes**: Purpose and usage, important attributes
   - **Methods**: Behavior, parameters, return value
   - **Modules**: Purpose and main components

**Don't Document:**
- Private methods/functions (unless complex)
- Obvious implementation details
- Properties if they're simple getters/setters

**Output Format:**
```
🔴 MISSING: [Docstring required]
   Location: [file:line]
   Entity: [Function/Class/Module name]
   Fix: [Add docstring with example]

🟡 INCOMPLETE: [Docstring missing information]
   Location: [file:line]
   Missing: [What's missing - e.g., 'Args section', 'Returns', 'Raises']
   Fix: [Complete the docstring]

⚠️ INCONSISTENT: [Style mismatch]
   Location: [file:line]
   Issue: [Style inconsistency description]
   Fix: [Align with project convention]
```

Ensure all public APIs have clear, complete docstrings.
