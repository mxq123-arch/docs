# Source: https://github.com/mintlify/docs/blob/main/zh/index.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

## FilesExpand file tree

 main

/

# index.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/zh/index.mdx)

History

54 lines (45 loc) · 2.52 KB

 main

/

# index.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

54 lines (45 loc) · 2.52 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/zh/index.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>简介</td></tr><tr><th>description</th><td>邂逅新一代文档体验：AI 原生、开箱即用且美观，为开发者打造。</td></tr><tr><th>mode</th><td>frame</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">概览</div></th><th><div dir="auto">平台</div></th><th><div dir="auto">快速开始</div></th><th><div dir="auto">功能</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

export const HeroCard = ({ filename, title, description, href }) => { return ( [<img src={`https://raw.githubusercontent.com/mintlify/docs/refs/heads/main/images/hero/${filename}.png`} className="block dark:hidden pointer-events-none group-hover:scale-105 transition-all duration-100" /> <img src={`https://raw.githubusercontent.com/mintlify/docs/refs/heads/main/images/hero/${filename}-dark.png`} className="pointer-events-none group-hover:scale-105 transition-all duration-100 hidden dark:block" />](https://github.com/mintlify/docs/blob/main/zh/{href})

### {title}

{description} ); };

[![装饰性背景图像。](https://github.com/mintlify/docs/raw/main/images/hero/background-light.svg)](https://github.com/mintlify/docs/blob/main/images/hero/background-light.svg)

```
<img src="/images/hero/background-dark.svg" className="hidden dark:block pointer-events-none w-full h-auto" alt="装饰性背景图像。" />
```

# 文档

```
<div className="max-w-xl mx-auto px-4 mt-4 text-lg text-center text-gray-500 dark:text-zinc-500">
  迎接新一代文档体验。AI 原生，开箱即用且精美，为开发者和团队打造。
</div>

<div className="px-6 lg:px-0 mt-12 lg:mt-24 grid sm:grid-cols-2 gap-x-6 gap-y-4">
  <HeroCard filename="rocket" title="快速开始" description="通过我们的分步指南，在几分钟内部署你的第一个文档站点" href="/zh/quickstart" />

  <HeroCard filename="cli" title="CLI 安装" description="安装命令行界面（CLI），在本地预览和开发文档" href="/zh/cli" />

  <HeroCard filename="editor" title="网页编辑器" description="使用基于浏览器的编辑器快速更新和管理内容" href="/zh/editor/index" />

  <HeroCard filename="components" title="组件" description="使用我们开箱即用的组件构建丰富、互动性强的文档" href="/zh/components/accordions" />
</div>
```