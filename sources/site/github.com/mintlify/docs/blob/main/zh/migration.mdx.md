# Source: https://github.com/mintlify/docs/blob/main/zh/migration.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# migration.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/zh/migration.mdx)

History

216 lines (151 loc) · 25 KB

 main

/

# migration.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

216 lines (151 loc) · 25 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/zh/migration.mdx)

Copy raw file

Download raw file

Edit and raw actions

<table><tbody><tr><th>title</th><td>迁移到 Mintlify</td></tr><tr><th>description</th><td>从 Docusaurus、ReadMe、GitBook 或其他平台将文档迁移到 Mintlify，提供逐步说明和 CLI 工具支持。</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">migration</div></th><th><div dir="auto">Docusaurus</div></th><th><div dir="auto">ReadMe</div></th><th><div dir="auto">import</div></th></tr></tbody></table></td></tr></tbody></table>

本指南将帮助你将现有文档迁移至 Mintlify。对受支持的平台，可选择自动迁移；若希望对流程拥有完全掌控，则可选择手动迁移。

\## 选择迁移路径

- 如果当前使用 Docusaurus 或 ReadMe -> **自动化迁移**
- 如果有公开的 GitHub 存储库 -> **自动生成的迁移**
- 如果从其他任意平台迁移 -> **手动迁移**

使用 \[@mintlify/scraping 包\]([https://www.npmjs.com/package/@mintlify/scraping)迁移您的文档。该包会抓取您的内容并转换为](https://www.npmjs.com/package/@mintlify/scraping)迁移您的文档。该包会抓取您的内容并转换为) Mintlify 组件格式。

```
### 支持的平台

<Columns cols="3">
  <Card
    title="Docusaurus"
    icon={<svg className="h-6 w-6" width="36" height="36" viewBox="0 -19 256 256" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" preserveAspectRatio="xMidYMid">
```

} horizontal />

```
  <Card
    title="ReadMe"
    icon={<svg fill="#177fc4" className="h-6 w-6" width="36" height="36" viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg">
```

} horizontal />

````
如果你的文档托管在其他平台上，请参阅手动迁移步骤。

### 安装爬虫工具

安装 `@mintlify/scraping` 包即可开始使用。

```bash
npm install @mintlify/scraping@latest -g
```

### 抓取页面和部分

迁移工具会自动检测您的文档平台并转换内容。处理后的文件默认保存在本地的 `./docs` 文件夹中。

对于大型文档站点，建议分批迁移较小的部分，而不是一次性迁移整个站点。

**迁移整个部分：**

```bash
mintlify-scrape section https://your-docs-site.com/docs
```

**迁移单个页面：**

```bash
mintlify-scrape page https://your-docs-site.com/docs/getting-started
```

**过滤特定路径：**

使用 `--filter` (或 `-f`) 选项仅抓取匹配特定路径前缀的 URL。

```bash
mintlify-scrape section https://your-docs-site.com --filter=/docs
```

过滤器匹配指定路径及其所有嵌套路径。例如，`--filter=/docs` 匹配 `/docs`、`/docs/getting-started`、`/docs/api/reference` 等。

**迁移 OpenAPI 规范：**

```bash
mintlify-scrape openapi-file [openApiFilename]
```

### 将准备好的内容添加到您的 Mintlify 项目

抓取现有文档平台后,您就可以在 Mintlify 上构建文档了。

确认所有页面已完成抓取后，将这些文件添加到您在入门流程中创建的文档存储库。这通常是 GitHub 存储库。
````

Mintlify 可以为任何公开的 GitHub 存储库生成一个完整的文档站点，无论其中是否已经包含文档，还是只有代码。

````
在任何公开存储库的 URL 中，将 `github.com` 替换为 `mintlify.com`：

```text
https://mintlify.com/github-owner/repository-name
```

Mintlify 会分析您的存储库并生成一个完整的文档站点，供您进一步自定义。
````

从任意平台迁移你的文档，并对整个流程保持完全掌控。

````
### 内容迁移

要将内容迁移到 Mintlify，你需要：

* 一个有效的 `docs.json`，用于站点设置和导航。参见 [全局设置](/zh/organize/settings) 和 [导航](/zh/organize/navigation) 了解更多信息。
* 每个文档页面对应一个 Markdown 文件 (`.md` 或 `.mdx`) 。推荐使用 MDX 格式。参见 [页面](/zh/organize/pages) 了解更多信息。
* (可选) 为你的 API 端点页面准备一份 OpenAPI 规范。参见 [OpenAPI 设置](/zh/api-playground/openapi-setup) 了解更多信息。

1. 如果你的内容已经是 Markdown 格式，将这些内容复制到你的 Mintlify 项目中。否则，将内容转换为 MDX 格式。
2. 创建 `docs.json`，并在其中引用你的 Markdown 页面路径。
3. 如果你有 OpenAPI 规范，将其添加到 `docs.json` 中，并配置 API 操作台。你还可以使用 [`@mintlify/scraping`](https://www.npmjs.com/package/@mintlify/scraping) 包根据规范生成 MDX 页面：

```bash
npx @mintlify/scraping@latest openapi-file <openApiFilename> -o <folder-name>
```

<Tip>
  如果你以 `.md` 文件的形式迁移内容，请将它们转换为 `.mdx`，以支持 React 组件等交互功能。
</Tip>

### 资源迁移

1. 将资源复制到存储库的 `images/` 目录中。
2. 更新你在 Markdown 文件中的引用：
   ```mdx
 ![Alt text](/images/screenshot.png)
 ```
````

\## 迁移后检查清单

完成迁移（自动或手动）后，建议检查：

- 所有页面均能正常渲染
- 导航按预期运行
- 内部链接可正确跳转
- 图片与资源加载正常
- 代码块语法高亮显示正常
- 搜索可用
- 部署用分支是否正确