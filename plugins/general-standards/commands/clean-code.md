Review code for clean code principles, readability, and maintainability:

**Clean Code Principles (based on Robert C. Martin's Clean Code):**

1. **Meaningful Names**
   - Use intention-revealing names
   - Avoid disinformation (`dataList` unless it's a List)
   - Make meaningful distinctions
   - Use pronounceable names
   - Use searchable names
   - Avoid single-letter names except in loops
   - ❌ `d`, `lst`, `tmp`
   - ✅ `daysSinceLastLogin`, `userList`, `tempBuffer`

2. **Functions Should Be Small**
   - Prefer functions < 20 lines
   - Do one thing well
   - One level of abstraction per function
   - Avoid more than 3 arguments (use objects for more)
   - No flag arguments (boolean = function doing two things)
   - Have no side effects or make them explicit

3. **Comments**
   - ❌ Don't comment bad code - rewrite it
   - ✅ Explain "why", not "what"
   - ❌ Redundant comments that repeat the code
   - ✅ Javadoc/docstrings for public APIs
   - ❌ Commented-out code (delete it, git has history)
   - ✅ TODO/FIXME with context and owner

4. **Error Handling**
   - Don't return null (use exceptions, Maybe/Either types)
   - Don't pass null (use empty collections, default values)
   - Prefer exceptions over error codes
   - Provide context with error messages
   - Don't ignore or silently catch errors

5. **DRY (Don't Repeat Yourself)**
   - Extract repeated code into functions
   - Use composition over inheritance
   - Follow the "Rule of Three" (refactor on third occurrence)
   - ❌ Copy-paste code
   - ✅ Well-named helper functions

6. **SOLID Principles**
   - **S**ingle Responsibility: One reason to change
   - **O**pen/Closed: Open for extension, closed for modification
   - **L**iskov Substitution: Subtypes must be substitutable
   - **I**nterface Segregation: Many specific interfaces > one general
   - **D**ependency Inversion: Depend on abstractions, not concretions

7. **Object and Data Structure**
   - Keep data private (encapsulation)
   - Use immutable data structures where possible
   - Prefer composition over inheritance
   - Law of Demeter: Don't talk to strangers
   - ❌ `user.getAddress().getStreet().getName()`
   - ✅ `user.getStreetName()`

8. **Code Organization**
   - Related code should be close together
   - Vertical distance: concepts used close together
   - Horizontal distance: keep lines short, readable
   - Use blank lines to separate logical groups
   - One class per file (usually)
   - Keep public API clean, internal implementation hidden

9. **Testing**
   - Write tests first (TDD) or at least with the code
   - Test one thing per test
   - Use descriptive test names
   - Arrange-Act-Assert pattern
   - Test edge cases and error conditions
   - Keep tests fast and independent

10. **Refactoring Smells**
    - Long methods (> 50 lines)
    - Large classes (> 300 lines)
    - Long parameter lists (> 3-4)
    - Feature envy (methods more interested in other classes)
    - Data clumps (group related data)
    - Primitive obsession (use small classes/objects)
    - Switch statements (consider polymorphism)

**Code Smell Detection:**
```
🔴 SMELL: [Code smell type]
   Location: [file:line]
   Issue: [Description of the problem]
   Impact: [Why it's bad]
   Refactoring: [Specific refactoring suggestion with example]
```

**Example Refactorings:**

```python
# ❌ Before: Long method with multiple responsibilities
def process_user(user):
    # validate
    if not user.email:
        return False
    # save
    db.save(user)
    # send email
    email.send(user.email)
    return True

# ✅ After: Single Responsibility
def validate_user(user):
    return bool(user.email)

def save_user(user):
    db.save(user)

def send_welcome_email(user):
    email.send(user.email)

def process_user(user):
    if not validate_user(user):
        return False
    save_user(user)
    send_welcome_email(user)
    return True
```

**Output Format:**
```
🔴 VIOLATION: [Clean Code principle violated]
   Location: [file:line]
   Principle: [Which principle]
   Issue: [What's wrong]
   Refactor: [How to fix with example]

💡 SUGGESTION: [Improvement opportunity]
   Location: [file:line]
   Current: [Current approach]
   Better: [Better alternative]

⭐ GOOD: [Highlight good practices]
   Location: [file:line]
   What: [What was done well]
```

Focus on the most impactful issues first (duplication, long functions, poor naming).
