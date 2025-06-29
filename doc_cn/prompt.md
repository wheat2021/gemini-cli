# 提升 Gemini CLI 翻译任务效率的提示词

为了更高效、准确地完成文档翻译任务，请在未来的请求中考虑以下指导原则：

## 任务目标

将 `docs` 目录下的所有 Markdown 文档 (`.md` 文件) 翻译成中文，并将其保存到 `doc_cn` 目录下。

## 翻译要求

1.  **翻译质量：** 确保翻译内容准确、流畅，并符合中文阅读习惯，保持用户友好性。
2.  **链接处理：**
    *   **关键：** 必须保留 Markdown 文件中的所有相对链接。
    *   **路径调整：** 翻译后的文档中的相对链接应自动调整，以正确指向 `doc_cn` 目录下对应的翻译文件。例如，如果 `docs/cli/configuration.md` 中有一个链接 `../telemetry.md`，翻译后在 `doc_cn/cli/configuration.md` 中，该链接应指向 `../telemetry.md`（即 `doc_cn/telemetry.md`）。
3.  **目录结构：** 保持与 `docs` 目录完全相同的子目录结构。例如，`docs/cli/commands.md` 翻译后应位于 `doc_cn/cli/commands.md`。

## 工具使用和效率提升

1.  **绝对路径使用规范：**
    *   当向 `read_file`、`write_file` 或其他需要绝对路径的工具提供文件路径时，**请勿**在路径字符串外部添加额外的引号。例如，使用 `absolute_path="D:\path\to\file.md"` 而不是 `absolute_path="\"D:\\path\\to\\file.md\\""`。
2.  **错误处理与重试：**
    *   如果工具调用失败，请仔细检查错误信息，并根据错误原因调整参数或策略，然后进行重试。
3.  **批量处理（酌情）：**
    *   对于大量相似的文件操作（例如读取、翻译、写入），如果可能且工具支持，可以考虑批量处理文件列表，以减少重复的工具调用开销。

## 示例

假设 `docs` 目录结构如下：

```
docs/
├── index.md
└── cli/
    ├── commands.md
    └── configuration.md
```

翻译后 `doc_cn` 目录结构应为：

```
doc_cn/
├── index.md
└── cli/
    ├── commands.md
    └── configuration.md
```

并且 `doc_cn/cli/commands.md` 中的 `../configuration.md` 链接应指向 `doc_cn/cli/configuration.md`。

遵循这些指导原则将有助于我更准确、高效地完成您的任务。
