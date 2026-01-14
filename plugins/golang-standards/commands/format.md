Check and suggest formatting improvements for Go code according to Go conventions:

**Formatting Checks:**

1. **Standard Formatting**
   - Run `gofmt -s` to simplify code
   - Use tabs for indentation (not spaces)
   - No trailing whitespace
   - One blank line between top-level declarations
   - Opening braces on same line (not new line)

2. **Naming Conventions**
   - Package names: lowercase, short, descriptive
     - ✅ `httpserver`, `user`, `auth`
     - ❌ `httpServer`, `myPackage`, `v1`
   - Constants: PascalCase or UPPER_SNAKE_CASE
   - Variables: camelCase for local, PascalCase for exported
   - Interfaces: typically `-er` suffix (e.g., `Reader`, `Writer`)
   - Test functions: `Test<FunctionName>`

3. **Struct Field Ordering**
   - Exported fields before unexported
   - Group related fields together
   - Consider cache line alignment for performance-critical structs

4. **Function Organization**
   - Keep main logic early in file
   - Helper functions after main functions
   - Tests in separate `_test.go` file

5. **Import Ordering**
   - Standard library
   - Third-party packages
   - Local/internal packages
   - Separate with blank lines
   - Remove unused imports

6. **Comment Style**
   - Use `//` for all comments (not `/* */`)
   - Doc comments start with the name being documented
   - No blank line between comment and declaration
   - Package comments at top of file

7. **Common Patterns**
   - Use `var` keyword sparingly (let type inference work)
   - Prefer `:=` over `var` for local variables
   - Use raw string literals `` ` `` for regex and multi-line strings

**Example Fixes:**
```go
// ❌ Before
func (self *MyStruct) DoThing() {
    var x int = 5
    return x
}

// ✅ After
func (m *MyStruct) doThing() int {
    x := 5
    return x
}
```

Provide specific formatting suggestions with before/after examples.
