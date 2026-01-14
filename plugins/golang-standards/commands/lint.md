Check the Go code for common linting issues and style problems:

**Static Analysis Checks:**

1. **Unused Code**
   - Unused variables, functions, or imports
   - Unused struct fields or method receivers

2. **Error Handling Issues**
   - Unchecked errors (must handle all errors)
   - Errors assigned but not checked

3. **Struct Tag Issues**
   - Duplicate or malformed struct tags
   - Standard tags like `json`, `yaml`, `db` should be correct

4. **Comment Quality**
   - Exported functions must have documentation comments
   - Comments should be complete sentences
   - Package comments should be present in doc.go

5. **Formatting**
   - Code must pass `gofmt`
   - Indentation should use tabs, not spaces
   - Line length typically under 100-120 characters

6. **Common Anti-patterns**
   - Using `time.Sleep` instead of proper synchronization
   - Empty `select` statements
   - Deferring in loops without wrapping in anonymous function
   - Comparing errors with `nil` incorrectly

7. **Concurrency Issues**
   - Data races in goroutines
   - Missing mutex protection for shared data
   - Channel operations that may block indefinitely

8. **Resource Management**
   - File handles not closed (use defer)
   - Goroutines that may leak
   - Connections not properly closed

**Output Format:**
```
🔴 SEVERE: [Issue that will cause bugs]
🟡 WARNING: [Style or minor issue]
💡 SUGGESTION: [Improvement opportunity]
   Location: [file:line-range]
   Code: [Relevant snippet]
   Fix: [How to fix]
```

Prioritize severe issues that affect correctness.
