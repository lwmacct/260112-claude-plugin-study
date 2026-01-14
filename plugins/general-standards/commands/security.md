Review code for security vulnerabilities and follow secure coding best practices:

**Security Checks:**

1. **Injection Vulnerabilities**
   - SQL Injection: Use parameterized queries, never concatenate strings
   - Command Injection: Avoid `eval()`, `exec()`, `system()` with user input
   - Path Traversal: Validate and sanitize file paths
   - XSS: Sanitize user input before rendering in HTML/JS
   - LDAP/NoSQL Injection: Use safe query constructors

2. **Authentication & Authorization**
   - Never store plaintext passwords
   - Use strong password hashing (bcrypt, argon2, scrypt)
   - Implement proper session management
   - Check authorization on every request
   - Use HTTPS/TLS for all communications

3. **Secrets Management**
   - ❌ Hardcoded API keys, tokens, passwords
   - ❌ Secrets in configuration files committed to git
   - ✅ Use environment variables or secret managers
   - ✅ Rotate credentials regularly
   - ✅ Use .gitignore for sensitive files

4. **Input Validation**
   - Validate all input (type, length, format, range)
   - Use allowlists (not blocklists) where possible
   - Sanitize output as well as input
   - Implement rate limiting for APIs

5. **Cryptography**
   - ❌ Don't roll your own crypto
   - ✅ Use well-vetted libraries (OpenSSL, libsodium)
   - Use authenticated encryption (AES-GCM, ChaCha20-Poly1305)
   - Don't use deprecated algorithms (MD5, SHA1, RC4)
   - Use constant-time comparison for secrets

6. **Error Handling**
   - Don't expose sensitive information in error messages
   - Don't leak stack traces to users
   - Log security events appropriately
   - Implement proper logging without exposing secrets

7. **Dependencies**
   - Keep dependencies up to date
   - Scan for known vulnerabilities (Snyk, Dependabot, npm audit)
   - Review third-party code before integrating
   - Use lockfiles (package-lock.json, go.sum, requirements.txt)

8. **Common Vulnerabilities (OWASP Top 10)**
   - Broken Access Control
   - Cryptographic Failures
   - Injection
   - Insecure Design
   - Security Misconfiguration
   - Vulnerable and Outdated Components
   - Identification and Authentication Failures
   - Software and Data Integrity Failures
   - Security Logging and Monitoring Failures
   - Server-Side Request Forgery (SSRF)

9. **Language-Specific Issues**

   **Go:**
   - Check for `http.DefaultClient` usage (should configure timeouts)
   - Validate input to `os.Open`, `ioutil.ReadFile`
   - Use `filepath.Join` and `filepath.Clean` for paths

   **Python:**
   - Avoid `pickle` with untrusted data
   - Use `subprocess.run()` instead of `os.system()`
   - Be careful with `yaml.load()` (use `safe_load()`)

   **JavaScript/TypeScript:**
   - Avoid `eval()` and `Function()` constructor
   - Use `textContent` instead of `innerHTML` when possible
   - Validate and sanitize input

**Output Format:**
```
🚨 CRITICAL: [Severe security issue]
   Location: [file:line]
   Risk: [What can happen]
   Fix: [Secure implementation with example]

⚠️ WARNING: [Potential security concern]
   Location: [file:line]
   Why: [Explanation of risk]
   Fix: [Better approach]

💡 BEST PRACTICE: [Security recommendation]
   Context: [Where to apply]
   Suggestion: [What to do]
```

Prioritize critical vulnerabilities that could lead to:
- Remote code execution
- Data breaches
- Authentication bypass
- Privilege escalation

Reference: [OWASP Top 10](https://owasp.org/www-project-top-ten/)
