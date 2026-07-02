# Source: https://github.com/mintlify/docs/blob/main/credits.mdx

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

[![ethanpalm](https://avatars.githubusercontent.com/u/56270045?v=4&size=40)](https://github.com/ethanpalm) [ethanpalm](https://github.com/mintlify/docs/commits?author=ethanpalm)

[add export info (](https://github.com/mintlify/docs/commit/bf399dbaa9f590d9f2f7cfef1572bf17fec59977) [#6348](https://github.com/mintlify/docs/pull/6348) [)](https://github.com/mintlify/docs/commit/bf399dbaa9f590d9f2f7cfef1572bf17fec59977)

success

Jul 1, 2026

[bf399db](https://github.com/mintlify/docs/commit/bf399dbaa9f590d9f2f7cfef1572bf17fec59977) · Jul 1, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/credits.mdx)

Open commit details

History

88 lines (60 loc) · 4.33 KB

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
 

88 lines (60 loc) · 4.33 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/credits.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Credit pricing</td></tr><tr><th>description</th><td>Understand how Mintlify credits work for assistant messages, agent runs, and automations, including how we bill credit tiers, overages, and rollovers.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">credits</div></th><th><div dir="auto">billing</div></th><th><div dir="auto">pricing</div></th><th><div dir="auto">AI chat</div></th><th><div dir="auto">messages</div></th><th><div dir="auto">tiers</div></th><th><div dir="auto">usage</div></th><th><div dir="auto">export</div></th><th><div dir="auto">CSV</div></th><th><div dir="auto">activity log</div></th></tr></tbody></table></td></tr></tbody></table>

Some Mintlify features consume credits.

- Assistant responses
- Agent runs in the editor or on Slack
- Automation runs

For the most current pricing information, see the [Pricing page](https://mintlify.com/pricing) or view the [Usage](https://app.mintlify.com/settings/organization/usage) page in your dashboard.

## Pricing tiers

| Monthly credits | Monthly cost | Rollover cap |
| :-- | :-- | :-- |
| 0 | $0 | 0 |
| 10,250 | $100 | 15,375 |
| 26,000 | $250 | 39,000 |
| 52,500 | $500 | 78,750 |
| 80,000 | $750 | 120,000 |
| 108,500 | $1,000 | 162,750 |

If you need more than 108,500 credits per month, [contact sales](https://www.mintlify.com/contact/sales) to discuss a custom plan.

**Overages** cost an additional $0.01 per credit rather than triggering an automatic tier upgrade. You can set usage alerts to receive an email when you reach a certain percentage of your tier limit. Allowing overages can be cheaper than moving up a tier depending on your usage patterns.

Overages default to off. You must enable them on the \[Usage\]([https://app.mintlify.com/settings/organization/usage](https://app.mintlify.com/settings/organization/usage)) page of your dashboard.

**Rollovers** carry forward up to 50% of unused credits to the next month, so the maximum credits available in any month is 1.5 times your monthly limit. Rollovers reset if you change tiers.

Higher tiers offer a lower effective cost per credit. If your usage consistently reaches the top of your current tier, upgrading is more economical than paying ongoing overage charges.

Upgrades and downgrades take effect immediately, and we prorate the charges to the current billing cycle.

For high-volume usage or custom credit packages, [contact sales](mailto:sales@mintlify.com). Custom credit packages are available on enterprise plans only.

## How credits work

Different features consume different amounts of credits per interaction:

| Feature | Average credits per interaction |
| :-- | :-- |
| Assistant response | 23 |
| Editor agent run | 115 |
| Slack agent run | 110 |

Automations also consume credits when they run:

| Automation | Average credits per run |
| :-- | :-- |
| Update from code changes | 180 |
| Update from assistant conversations | 212 |
| Broken link detection | 285 |
| Changelog | 223 |
| SEO audit | 422 |
| Translations | 913 |
| Typo check | 330 |
| Writing style | 235 |

## Estimating your usage

Use the averages in the [How credits work](https://github.com/#how-credits-work) section to estimate your monthly credit needs.

For example, if your docs site handles 500 assistant responses per month, that's roughly 11,500 credits (500 × 23). Adding a weekly broken link detection automation adds about 1,140 credits per month (4 × 285).

After using credit-powered features for a month, review your usage patterns to see if you should adjust your tier.

## Export usage activity

Export your usage activity log to CSV for deeper analysis, reporting, or record-keeping.

1. Navigate to the [Usage](https://app.mintlify.com/settings/organization/usage) page in your dashboard.
2. Optionally, adjust the date range in the toolbar to change the period the export covers.
3. In the **Activity log** section, click **Export to CSV**.
4. Mintlify emails you a download link when the export is ready. The link expires after 72 hours.

The exported CSV includes the date, product, and credits consumed for each event in the selected range.

## Cost optimization

**Schedule automations instead of triggering on every push.** Automations like SEO audits, writing style checks, and broken link detection don't need to run on every code change. Running these on a daily or weekly cron schedule rather than on every push significantly reduces credit consumption without meaningful impact on content quality.

**Monitor your usage patterns.** The [Usage](https://app.mintlify.com/settings/organization/usage) page in your dashboard shows a breakdown by feature category. If a particular automation is consuming more credits than expected, review its trigger or any custom instructions.