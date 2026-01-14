# Golang Standards Plugin

Golang 开发规范检查插件，帮助团队遵循 Go 官方惯用法和最佳实践。

## 功能

### `/golang-standards:review`
全面的 Go 代码审查，检查：
- 错误处理规范
- 命名约定（包名、导出/未导出标识符）
- Goroutine 和并发最佳实践
- 接口设计原则
- 代码结构和组织

### `/golang-standards:lint`
静态代码检查，发现：
- 未使用的代码
- 错误处理遗漏
- 结构体标签问题
- 并发安全问题
- 资源泄漏风险

### `/golang-standards:format`
格式化和风格检查：
- `gofmt` 标准格式
- 命名规范建议
- 导入排序
- 注释风格

## 使用示例

```bash
# 审查当前文件
/golang-standards:review

# 检查代码问题
/golang-standards:lint

# 格式化建议
/golang-standards:format
```

## 遵循的规范

- [Effective Go](https://go.dev/doc/effective_go)
- [Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments)
- [Go Common Mistakes](https://github.com/teivah/100-go-mistakes)

## 版本

1.0.0 - 初始版本
