# 内存工具 (`save_memory`)

本文档介绍 Gemini CLI 的 `save_memory` 工具。

## 描述

使用 `save_memory` 在您的 Gemini CLI 会话中保存和调用信息。使用 `save_memory`，您可以指示 CLI 在会话之间记住关键细节，从而提供个性化和有针对性的帮助。

### 参数

`save_memory` 接受一个参数：

- `fact` (字符串, 必需): 要记住的具体事实或信息。这应该是一个用自然语言编写的清晰、独立的陈述。

## 如何将 `save_memory` 与 Gemini CLI 结合使用

该工具会将提供的 `fact` 附加到位于用户主目录 (`~/.gemini/GEMINI.md`) 中的一个特殊 `GEMINI.md` 文件中。该文件可以配置为使用不同的名称。

添加后，这些事实会存储在 `## Gemini Added Memories` 部分下。该文件会在后续会话中作为上下文加载，从而允许 CLI 调用已保存的信息。

用法:

```
save_memory(fact="在此处输入您的事实。")
```

### `save_memory` 示例

记住用户偏好：

```
save_memory(fact="我偏好的编程语言是 Python。")
```

存储项目特定细节：

```
save_memory(fact="我目前正在处理的项目名为 'gemini-cli'。")
```

## 重要说明

- **一般用法：** 此工具应用于简洁、重要的事实。它不用于存储大量数据或对话历史记录。
- **内存文件：** 内存文件是一个纯文本 Markdown 文件，因此如果需要，您可以手动查看和编辑它。