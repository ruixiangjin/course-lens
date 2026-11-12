# Monash Study Agent

[English](#english) · [简体中文](#简体中文) · [MIT License](LICENSE)

## English

Monash Study Agent is a study assistant for Monash courses. It organises course materials downloaded from Ed and Moodle, lets you ask questions by course, and shows the sources retrieved during the conversation.

### Features

- **Course materials** · Browse resources by course. Extract searchable text from PDFs, Word documents, and PowerPoint slides.
- **Course chat** · Ask about your course materials and inspect the retrieved sources alongside the conversation.
- **Study memory** · Save and recall study notes and learning context by course.

### Getting started

Install Node.js 22.19 or later in the 22.x series, or Node.js 24 or later. You’ll also need pnpm and uv. From the repository root, run:

```sh
pnpm install
uv sync --project services/knowledge-service --python 3.12
cp config/sources.example.json config/sources.local.json
cp .env.example .env
```

Set your Ed and Moodle download paths in `config/sources.local.json` and add your `DEEPSEEK_API_KEY` to `.env`. Replace `FIT2109` below with the course you want to index.

```sh
pnpm scan
pnpm normalize -- course FIT2109
pnpm lightrag -- sync-course FIT2109
pnpm ui:setup
pnpm ui
```

Open the web interface and select your course to start a conversation. Course files, generated indexes, and study memory are stored on your device. Model requests use DeepSeek.

[Documentation](docs/README.md) · [Implementation reference](docs/PROJECT_CODEBASE_REFERENCE.md)

## 简体中文

Monash Study Agent 是一款面向 Monash 课程的学习助手。它整理从 Ed 和 Moodle 下载的课程资料，支持按课程提问，并在对话旁显示检索到的资料来源。

### 主要功能

- **课程资料** · 按课程浏览资料，从 PDF、Word 和 PowerPoint 文件中提取可检索的内容。
- **课程对话** · 围绕课程资料提问，在对话旁查看检索到的来源。
- **学习记忆** · 按课程保存和找回学习笔记及相关上下文。

### 快速开始

准备 Node.js 22.19 或更高的 22.x 版本，或 Node.js 24 及以上版本，同时安装 pnpm 和 uv。在仓库根目录运行：

```sh
pnpm install
uv sync --project services/knowledge-service --python 3.12
cp config/sources.example.json config/sources.local.json
cp .env.example .env
```

在 `config/sources.local.json` 里填写 Ed 和 Moodle 的下载目录，在 `.env` 里填入 `DEEPSEEK_API_KEY`。把下面的 `FIT2109` 换成你要建立索引的课程代码。

```sh
pnpm scan
pnpm normalize -- course FIT2109
pnpm lightrag -- sync-course FIT2109
pnpm ui:setup
pnpm ui
```

打开网页界面，选择课程后就可以开始提问。课程文件、生成的索引和学习记忆保存在你的设备上，模型请求使用 DeepSeek。

[项目文档](docs/README.md) · [实现参考](docs/PROJECT_CODEBASE_REFERENCE.md)

## License · 许可证

Monash Study Agent’s original code and documentation are available under the [MIT License](LICENSE). [DeepSeek Harness](vendor/deepseek-harness/LICENSE) and its [third-party components](vendor/deepseek-harness/THIRD_PARTY_NOTICES.md) retain their respective licenses.

Monash Study Agent 的原创代码和文档采用 [MIT 许可证](LICENSE)。[DeepSeek Harness](vendor/deepseek-harness/LICENSE) 及其[第三方组件](vendor/deepseek-harness/THIRD_PARTY_NOTICES.md)沿用各自的许可证。
