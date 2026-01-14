Check Python code for type hint completeness and correctness:

**Type Hint Checks:**

1. **Function Annotations**
   - All functions should have parameter type hints
   - Return type should always be specified (use `-> None` explicitly)
   - Use `typing` module for complex types

2. **Common Type Patterns**
   ```python
   # Basic types
   def process(name: str, count: int) -> bool: ...

   # Collections
   from typing import List, Dict, Set, Tuple
   def get_items() -> List[str]: ...
   def get_mapping() -> Dict[str, int]: ...

   # Optional values
   from typing import Optional
   def find_user(id: int) -> Optional[User]: ...

   # Union types
   from typing import Union
   def process(data: Union[str, bytes]) -> str: ...

   # Use pipe syntax (Python 3.10+)
   def process(data: str | bytes) -> str: ...
   ```

3. **Advanced Type Patterns**
   ```python
   # Callable
   from typing import Callable
   def apply(func: Callable[[int, int], int]) -> int: ...

   # TypeVar for generic functions
   from typing import TypeVar
   T = TypeVar('T')
   def first(items: List[T]) -> T: ...

   # Protocol for structural subtyping
   from typing import Protocol
   class Sized(Protocol):
       def __len__(self) -> int: ...
   ```

4. **Class Attributes**
   - Use class-level annotations for attributes
   - Consider `dataclasses` for data-heavy classes
   - Use `@property` with type hints

5. **Common Mistakes**
   ```python
   # ❌ Don't use Any when specific type is known
   def process(x: Any) -> Any: ...

   # ❌ Don't forget return type
   def process(x: int): ...

   # ❌ Don't use comments for types
   def process(x):  # type: int
       ...

   # ✅ Use proper type hints
   def process(x: int) -> int: ...
   ```

6. **Type Checking Tools**
   - Mention `mypy` for static type checking
   - Use `pyright` or `pyre` as alternatives
   - Enable strict mode for better coverage

**Output Format:**
```
🔴 MISSING: [Function/Class missing type hints]
   Location: [file:line]
   Fix: [Add proper type hints with example]

🟡 IMPRECISE: [Using Any or generic type]
   Location: [file:line]
   Why: [Specific type is better for documentation and checking]
   Fix: [More precise type hint]

💡 SUGGESTION: [Modern type pattern]
   Location: [file:line]
   Before: [Old pattern]
   After: [Modern alternative]
```

Check for missing type hints in all public functions and methods.
