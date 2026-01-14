Review the selected Go code according to Go official idioms and best practices:

**Check for:**

1. **Error Handling**
   - All errors must be checked (no bare returns, no ignored errors)
   - Error messages should be descriptive and include context
   - Avoid wrapping errors with `fmt.Errorf` without "%w" verb

2. **Naming Conventions**
   - Package names should be lowercase, single word, short
   - Exported names must use PascalCase (e.g., `MyFunction`)
   - Unexported names must use camelCase (e.g., `myVariable`)
   - Acronyms should keep consistent casing (e.g., `HTTPServer` not `HttpServer`)

3. **Goroutines and Concurrency**
   - Goroutines should have clear lifecycle management
   - Use `context.Context` for cancellation and timeouts
   - Avoid goroutine leaks (always handle `Done` channel or use `sync.WaitGroup`)
   - Use channels for communication, don't share memory by communicating

4. **Interface Design**
   - Interfaces should be small (ideally 1-2 methods)
   - Accept interfaces, return structs
   - Define interfaces where they are used, not in advance

5. **Code Structure**
   - Keep functions short and focused
   - Avoid deep nesting (prefer early returns)
   - Use `go fmt` standard formatting
   - Group related functions, organize by responsibility

6. **Pointers and Values**
   - Use value receivers for methods that don't modify the receiver
   - Use pointer receivers for methods that modify the receiver
   - Don't use pointers just to avoid copying (Go is efficient)

7. **Testing**
   - Table-driven tests for multiple cases
   - Use `t.Parallel()` for independent tests
   - Test file should be `_test.go` in same package

8. **Package Organization**
   - Avoid circular dependencies
   - Keep internal packages truly internal
   - Use `go mod` for dependency management

**Provide feedback in this format:**
```
❌ ISSUE: [Brief description]
   Location: [file:line]
   Why: [Explanation of Go guideline]
   Fix: [Suggested fix with example]
```

Focus on critical issues first, then style improvements. Be specific and actionable.
