# 🎓 Claude Code 插件开发学习项目

> 从理论到实践，掌握 Claude Code 插件开发和 Marketplace 配置

[![Claude Code](https://img.shields.io/badge/Claude_Code-1.0.33+-blue.svg)](https://code.claude.com)
[![Marketplace](https://img.shields.io/badge/Marketplace-v2.0.0-orange.svg)](plugins/)

## 📚 项目简介

这是一个 Claude Code 插件学习和实战项目，包含：

- ✅ 3 个生产就绪的开发规范检查插件
- ✅ 多插件 Marketplace 配置示例
- ✅ 完整的插件元数据和命令定义

**项目特色：**

1. **多插件架构** - 展示如何构建和管理插件市场
2. **实战导向** - 包含 Go/Python/通用规范检查，可直接使用
3. **生产就绪** - 完整的 Marketplace 配置，可直接发布

## 🚀 快速开始

### 1. 安装插件市场

```bash
# 从 GitHub 仓库安装
/plugin marketplace add lwmacct/260112-cc-plugins-study

# 或本地测试
/plugin marketplace add .
```

### 2. 安装所需插件

```bash
# Golang 开发规范
/plugin install golang-standards@cc-plugins-study

# Python 开发规范
/plugin install python-standards@cc-plugins-study

# 通用开发规范
/plugin install general-standards@cc-plugins-study
```

### 3. 使用插件

```bash
# Go 项目
/golang-standards:review

# Python 项目
/python-standards:review

# 所有项目
/general-standards:security
/general-standards:clean-code
```

## 📦 可用插件

### 📦 golang-standards

Golang 开发规范检查：遵循 Go 官方惯用法和最佳实践

**命令：**

- `/golang-standards:review` - Go 代码审查（错误处理、命名、并发、接口设计）
- `/golang-standards:lint` - 静态代码检查（未使用代码、错误处理、资源泄漏）
- `/golang-standards:format` - 格式和风格检查（gofmt、命名规范、导入排序）

**参考标准：**

- [Effective Go](https://go.dev/doc/effective_go)
- [Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments)

### 🐍 python-standards

Python 开发规范检查：遵循 PEP 8、PEP 257 和最佳实践

**命令：**

- `/python-standards:review` - Python 代码审查（PEP 8、命名、Pythonic 惯用法）
- `/python-standards:type-check` - 类型提示检查（参数注解、返回类型、typing 模块）
- `/python-standards:docstring` - 文档字符串检查（Google/NumPy 风格、完整性）

**参考标准：**

- [PEP 8 - Style Guide](https://peps.python.org/pep-0008/)
- [PEP 257 - Docstring Conventions](https://peps.python.org/pep-0257/)
- [PEP 484 - Type Hints](https://peps.python.org/pep-0484/)

### 🔧 general-standards

通用开发规范检查：安全最佳实践和代码质量

**命令：**

- `/general-standards:security` - 安全漏洞检查（OWASP Top 10、注入漏洞、密钥管理）
- `/general-standards:clean-code` - 清洁代码原则（命名、函数设计、DRY、SOLID）

**参考标准：**

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Clean Code by Robert C. Martin](https://www.oreilly.com/library/view/clean-code-a/9780136083238/)

## 📖 学习路径

### 🎯 快速上手

1. **查看插件配置** - 了解插件结构

   - 查看 `.claude-plugin/marketplace.json` 了解市场配置
   - 查看各插件的 `plugin.json` 了解插件元数据
   - 查看 `commands/*.md` 了解命令定义

2. **本地测试** - 动手实践

   ```bash
   # 本地安装市场
   /plugin marketplace add .

   # 安装插件
   /plugin install golang-standards@cc-plugins-study

   # 测试命令
   /golang-standards:review
   ```

3. **发布到 GitHub** - 分享给团队
   ```bash
   git push origin main
   /plugin marketplace add lwmacct/260112-cc-plugins-study
   ```

## 📁 项目结构

```
.
├── .claude-plugin/
│   └── marketplace.json              # 🏪 市场清单 (v2.0.0)
│
├── plugins/                          # 🎁 插件根目录
│   ├── golang-standards/             # Go 开发规范插件
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json          # 插件元数据
│   │   ├── commands/                # 命令定义
│   │   │   ├── review.md
│   │   │   ├── lint.md
│   │   │   └── format.md
│   │   └── README.md
│   │
│   ├── python-standards/             # Python 开发规范插件
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── commands/
│   │   │   ├── review.md
│   │   │   ├── type-check.md
│   │   │   └── docstring.md
│   │   └── README.md
│   │
│   └── general-standards/            # 通用开发规范插件
│       ├── .claude-plugin/
│       │   └── plugin.json
│       └── commands/
│           ├── security.md
│           └── clean-code.md
│
├── .pre-commit-config.yaml           # Pre-commit 配置
├── Taskfile.yml                      # Task 自动化配置
└── README.md                         # 本文档
```

## 🎓 学习内容

### 核心概念

- **命名空间隔离** - 防止命令冲突
- **清单驱动** - plugin.json 定义元数据
- **多态扩展** - 六种扩展类型
- **多插件架构** - Marketplace 管理多个插件

### 六大扩展类型

| 类型         | 用途       | 示例                       |
| ------------ | ---------- | -------------------------- |
| **Commands** | 斜杠命令   | `/golang-standards:review` |
| **Agents**   | 自定义代理 | 代码审查专家               |
| **Skills**   | 代理技能   | Git 助手                   |
| **Hooks**    | 事件钩子   | 文件保存后格式化           |
| **MCP**      | 外部工具   | 数据库集成                 |
| **LSP**      | 代码智能   | 语言服务                   |

### 三种 Marketplace 安装方式

```bash
# 1. GitHub 简写（推荐）
/plugin marketplace add owner/repo

# 2. Git URL
/plugin marketplace add https://github.com/user/repo.git

# 3. 本地路径（测试）
/plugin marketplace add ./path/to/marketplace
```

## 📊 项目统计

- 📁 **插件数量**: 3 个
- 📄 **命令总数**: 8 个
- 📦 **Marketplace**: v2.0.0

## 🎯 使用场景

### 个人开发

```bash
# 本地测试
/plugin marketplace add .
/plugin install golang-standards@cc-plugins-study

# 日常使用
/golang-standards:review      # 审查 Go 代码
/python-standards:review      # 审查 Python 代码
/general-standards:clean-code # 检查代码质量
```

### 团队协作

```bash
# 1. 提交到 GitHub
git push origin main

# 2. 团队成员安装
/plugin marketplace add lwmacct/260112-cc-plugins-study
/plugin install golang-standards@cc-plugins-study
```

### 代码审查工作流

```bash
# Go 项目 PR 前
/golang-standards:review      # 全面审查
/golang-standards:lint        # 静态检查
/golang-standards:format      # 格式检查

# Python 项目代码评审
/python-standards:review      # PEP 8 检查
/python-standards:type-check  # 类型完整性
/python-standards:docstring   # 文档质量

# 通用检查（所有语言）
/general-standards:security   # 安全检查
/general-standards:clean-code # 代码质量
```

## 🔧 常用命令

```bash
# 市场管理
/plugin marketplace add .                    # 添加本地市场
/plugin marketplace add owner/repo           # 添加 GitHub 市场
/plugin marketplace list                     # 查看市场列表

# 插件管理
/plugin install <plugin-name>@<marketplace>  # 安装插件
/plugin list                                 # 查看已安装插件
/help                                        # 查看可用命令

# 配置验证
jq . .claude-plugin/marketplace.json         # 验证 JSON 格式
```

## 💡 最佳实践

### 开发流程

1. **本地开发** - 创建插件目录和命令定义
2. **本地测试** - 使用 `/plugin marketplace add .` 测试
3. **推送 GitHub** - 提交代码到仓库
4. **团队使用** - 通过 GitHub 地址分发

### 插件开发规范

- ✅ JSON 文件格式正确（使用 `jq` 验证）
- ✅ 命令描述清晰，包含使用示例
- ✅ 每个插件有独立 README
- ✅ 提供参考标准链接

## 📚 参考资源

### 官方文档

- [Plugins](https://code.claude.com/docs/en/plugins.md) - 插件系统完整指南
- [Plugins Reference](https://code.claude.com/docs/en/plugins-reference.md) - 插件技术规范和架构
- [Plugin Marketplaces](https://code.claude.com/docs/en/plugin-marketplaces.md) - Marketplace 配置和发布
- [Discover & Install](https://code.claude.com/docs/en/discover-plugins.md) - 插件发现和安装

### 项目文档

- [golang-standards README](plugins/golang-standards/README.md) - Go 插件说明
- [python-standards README](plugins/python-standards/README.md) - Python 插件说明
- [marketplace.json](.claude-plugin/marketplace.json) - 市场配置文件

## 🤝 贡献

欢迎贡献！可以：

- 📖 修正文档错误
- 💡 添加新的规范检查插件
- 🎁 创建其他类型的插件（Agents、Hooks、Skills 等）
- 🧪 添加测试脚本和示例代码
- 🌍 提供多语言支持

## 📝 许可证

MIT License

## 👤 作者

Claude Code 学习项目

## 🔗 相关链接

- **GitHub**: https://github.com/lwmacct/260112-cc-plugins-study
- **Claude Code**: https://code.claude.com
- **官方插件文档**: https://code.claude.com/docs/en/plugins

---

<div align="center">

**🌟 如果这个项目对你有帮助，请给个 Star！**

Made with ❤️ by Claude Code

</div>
