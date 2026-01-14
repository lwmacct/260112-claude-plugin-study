# Python Standards Plugin

Python 开发规范检查插件，帮助团队遵循 PEP 8、PEP 257 和 Python 最佳实践。

## 功能

### `/python-standards:review`
全面的 Python 代码审查，检查：
- PEP 8 代码风格规范
- 命名约定（snake_case、PascalCase、UPPER_CASE）
- Pythonic 惯用法
- 安全最佳实践
- 常见反模式

### `/python-standards:type-check`
类型提示检查：
- 函数参数和返回值类型注解
- 使用 typing 模块的复杂类型
- 现代 Python 3.10+ 类型语法（`|` 联合类型）
- 泛型和 TypeVar 使用

### `/python-standards:docstring`
文档字符串检查（PEP 257）：
- Google/NumPy/reStructuredText 风格
- 完整的参数、返回值、异常说明
- 模块、类、函数文档完整性

## 使用示例

```bash
# 审查 Python 代码风格
/python-standards:review

# 检查类型提示
/python-standards:type-check

# 检查文档字符串
/python-standards:docstring
```

## 遵循的规范

- [PEP 8 - Style Guide](https://peps.python.org/pep-0008/)
- [PEP 257 - Docstring Conventions](https://peps.python.org/pep-0257/)
- [PEP 484 - Type Hints](https://peps.python.org/pep-0484/)
- [The Python Style Guide](https://google.github.io/styleguide/pyguide.html)

## 版本

1.0.0 - 初始版本
