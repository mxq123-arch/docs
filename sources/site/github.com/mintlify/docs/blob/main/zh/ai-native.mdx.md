# Source: https://github.com/mintlify/docs/blob/main/zh/ai-native.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# ai-native.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/zh/ai-native.mdx)

History

70 lines (50 loc) · 4.16 KB

## FilesExpand file tree

 main

/

# ai-native.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

70 lines (50 loc) · 4.16 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/zh/ai-native.mdx)

Copy raw file

Download raw file

Edit and raw actions

<table><tbody><tr><th>title</th><td>AI 原生文档</td></tr><tr><th>sidebarTitle</th><td>AI 原生</td></tr><tr><th>description</th><td>了解 AI 原生功能如何通过助手、agent 和 MCP 服务器提升文档的阅读、创作和发现体验。</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">AI</div></th><th><div dir="auto">assistant</div></th><th><div dir="auto">agent</div></th><th><div dir="auto">llms.txt</div></th><th><div dir="auto">MCP</div></th><th><div dir="auto">llms-full.txt</div></th></tr></tbody></table></td></tr></tbody></table>

当你在 Mintlify 上托管文档时，内置的 AI 功能可帮助用户更快找到答案，并让你的团队更高效地维护内容。你的内容为这些 AI 原生功能提供了上下文，从而全面提升阅读、创作与检索文档的体验。

\## 什么让你的文档具备 AI 原生特性

\### 阅读

除了阅读单个页面，用户还可以在你的文档中与[AI 助手](https://github.com/mintlify/docs/blob/main/zh/assistant/index)聊天，及时获得问题的答案和相关内容的链接。AI 助手会基于你的文档提供准确信息，帮助用户更好地了解你的产品。你也可以通过[API](https://github.com/mintlify/docs/blob/main/zh/api/assistant/create-assistant-message-v2)将 AI 助手嵌入自定义应用，扩展用户访问你文档的触达渠道。

\### 写作

[agent](https://github.com/mintlify/docs/blob/main/zh/agent) 可帮助你撰写和维护文档。它会基于你的提示、拉取请求 (PR；亦称“合并请求”/Merge Request) 以及 Slack 讨论串，创建包含建议更改的拉取请求。将 agent 添加到你的 Slack 工作区，你的团队成员即可通过与 agent 对话协同维护文档。你也可以通过 [API](https://github.com/mintlify/docs/blob/main/zh/api/agent/v2/create-agent-job) 将 agent 嵌入自定义应用。

创建 [automations](https://github.com/mintlify/docs/blob/main/zh/automations/index)，让 agent 按预设计划或在推送到存储库时运行。每个自动化都为 agent 定义提示词以及触发运行的条件。

配置常用工具 (如 [Cursor](https://github.com/mintlify/docs/blob/main/zh/guides/cursor)、[Claude Code](https://github.com/mintlify/docs/blob/main/zh/guides/claude-code) 和 [Devin Desktop](https://github.com/mintlify/docs/blob/main/zh/guides/devin-desktop)) ，以对齐 Mintlify 架构、你的风格指南和最佳实践。

\### 发现

你的网站会自动针对 AI 工具和搜索引擎进行优化，帮助用户更容易找到你的文档。所有页面都会以 Markdown 而非 HTML 的形式发送给 AI 代理，这有助于这些工具更快处理你的内容并使用更少的 token。通过在 URL 末尾追加 `.md`，每个页面也都可以以 Markdown 形式查看。使用 [visibility](https://github.com/mintlify/docs/blob/main/zh/components/visibility) 组件为不同受众定制内容。

Mintlify 会为你的文档托管 `llms.txt` 和 `skill.md` 文件。这些行业标准文件帮助大语言模型在响应用户查询时高效返回相关信息，并为智能代理提供可用能力列表，从而让用户在使用你的产品时取得更好的效果。

教用户如何安装你的 \`skill.md\` 文件，让他们在使用 AI 工具操作你的产品时获得更好的结果。使用 \[\`Prompt\` 组件\](/zh/components/prompt)将安装提示直接嵌入到你的文档中：

```mdx
<Prompt description="Install the skill for your product." actions={["copy", "cursor"]}>
npx skills add https://your-docs-domain.com
</Prompt>
```

你的文档站点还会托管一个 MCP 服务器，使用户能够将你的文档直接连接到他们的 AI 工具，在他们需要的地方获取关于你产品的最新信息。

全文搜索和语义理解帮助用户和 AI 工具快速找到相关信息。搜索能够理解用户意图，而不仅仅是匹配关键词。如果用户遇到 404 错误，你的网站会推荐相关页面，帮助他们找到所需内容。无需任何配置。

\## 启用 AI 功能

选择以下任意卡片以了解更多信息。

配置 AI 助手以搜索外部网站，或在其无法回答问题时将用户引导至你的支持团队。 按计划或在发生 push 事件时自动获取文档更新。 为页面添加菜单，让用户可以向 AI 工具发起查询、连接到你的 MCP 服务器，并一键复制整页作为上下文。