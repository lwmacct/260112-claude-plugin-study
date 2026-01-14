# General Standards Plugin

通用开发规范检查插件，涵盖安全最佳实践、代码质量和清洁代码原则。

## 功能

### `/general-standards:security`
安全漏洞检查和最佳实践：
- 注入漏洞（SQL、命令、路径遍历、XSS）
- 认证和授权问题
- 密钥和敏感信息管理
- 输入验证
- 加密实践
- 依赖安全
- OWASP Top 10 检查

### `/general-standards:clean-code`
清洁代码原则检查：
- 有意义的命名
- 函数设计（小而专一）
- DRY 原则
- SOLID 原则
- 代码组织和重构
- 代码异味检测

## 使用示例

```bash
# 安全检查
/general-standards:security

# 代码质量检查
/general-standards:clean-code
```

## 适用范围

这些命令适用于所有编程语言，提供：
- 语言无关的安全最佳实践
- 通用的代码质量原则
- 跨语言的清洁代码规范

## 参考资源

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Clean Code by Robert C. Martin](https://www.oreilly.com/library/view/clean-code-a/9780136083238/)
- [The Twelve-Factor App](https://12factor.net/)

## 版本

1.0.0 - 初始版本
