# Source: https://github.com/mintlify/docs/blob/main/zh/credits.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# credits.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/zh/credits.mdx)

History

85 lines (61 loc) · 3.68 KB

## FilesExpand file tree

 main

/

# credits.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

85 lines (61 loc) · 3.68 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/zh/credits.mdx)

Copy raw file

Download raw file

Edit and raw actions

<table><tbody><tr><th>title</th><td>积分定价</td></tr><tr><th>description</th><td>了解 Mintlify 积分如何用于助手消息、代理运行和自动化，包括我们如何对积分套餐、超额使用和结转进行计费。</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">积分</div></th><th><div dir="auto">计费</div></th><th><div dir="auto">定价</div></th><th><div dir="auto">AI 聊天</div></th><th><div dir="auto">消息</div></th><th><div dir="auto">套餐</div></th><th><div dir="auto">用量</div></th></tr></tbody></table></td></tr></tbody></table>

部分 Mintlify 功能会消耗积分。

- 助手回复
- 编辑器或 Slack 中的代理运行
- 自动化运行

如需查看最新的定价信息，请参阅 [Pricing 页面](https://mintlify.com/pricing)，或在你的控制台中查看 [Usage](https://app.mintlify.com/settings/organization/usage) 页面。

\## 定价等级

| 每月积分 | 每月费用 | 结转上限 |
| :-- | :-- | :-- |
| 0 | $0 | 0 |
| 10,250 | $100 | 15,375 |
| 26,000 | $250 | 39,000 |
| 52,500 | $500 | 78,750 |
| 80,000 | $750 | 120,000 |
| 108,500 | $1,000 | 162,750 |

如果你每月需要超过 108,500 个积分，请[联系销售](https://www.mintlify.com/contact/sales)以讨论定制方案。

**超额使用**每个积分额外收费 $0.01，而不会自动触发套餐升级。你可以设置用量提醒，在用量达到所在套餐限额的某一百分比时收到邮件通知。根据你的使用模式，允许超额使用可能比升级到更高套餐更划算。

超额使用默认关闭。你必须在控制台的 \[Usage\]([https://app.mintlify.com/settings/organization/usage](https://app.mintlify.com/settings/organization/usage)) 页面启用。

**结转**最多可将未使用积分的 50% 结转到下个月，因此任何月份的最大可用积分为月度限额的 1.5 倍。更改套餐时结转会重置。

更高的套餐每积分的实际成本更低。如果你的用量持续达到当前套餐的上限，升级套餐会比持续支付超额费用更经济。

升级和降级会立即生效，相关费用将按当前计费周期按比例结算。

如需大批量使用或定制积分套餐，请[联系销售](mailto:sales@mintlify.com)。定制积分套餐仅在企业方案下提供。

\## 积分如何使用

不同功能在每次交互中消耗的积分数量不同：

| 功能 | 每次交互平均积分 |
| :-- | :-- |
| 助手回复 | 23 |
| 编辑器代理运行 | 115 |
| Slack 代理运行 | 110 |

自动化运行时也会消耗积分：

| 自动化 | 每次运行平均积分 |
| :-- | :-- |
| 根据代码变更更新 | 180 |
| 根据助手对话更新 | 212 |
| 失效链接检测 | 285 |
| Changelog | 223 |
| SEO 审计 | 422 |
| 翻译 | 913 |
| 拼写检查 | 330 |
| 写作风格 | 235 |

\## 估算你的用量

使用[积分如何使用](https://github.com/#how-credits-work)部分中的平均值估算每月所需的积分量。

例如，如果你的文档站点每月处理 500 个助手回复，那大约是 11,500 个积分 (500 × 23)。再添加每周一次的失效链接检测自动化，每月大约会增加 1,140 个积分 (4 × 285)。

在使用积分驱动的功能一个月后，回顾你的使用模式，看看是否需要调整套餐。

\## 成本优化

**安排自动化定时运行，而不是在每次推送时触发。** SEO 审计、写作风格检查和失效链接检测等自动化无需在每次代码变更时运行。按每日或每周的 cron 计划运行这些自动化，而不是在每次推送时运行，可以显著减少积分消耗，对内容质量并不会有实质性影响。

**监控你的用量模式。** 控制台中的 [Usage](https://app.mintlify.com/settings/organization/usage) 页面按功能类别展示用量明细。如果某个自动化消耗的积分超出预期，请检查其触发条件或自定义指令。