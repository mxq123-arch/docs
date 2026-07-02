# Source: https://github.com/mintlify/docs/blob/main/create/changelogs.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# changelogs.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

[![mintlify[bot]](https://avatars.githubusercontent.com/in/222410?v=4&size=40)](https://github.com/apps/mintlify) [mintlify\[bot\]](https://github.com/mintlify/docs/commits?author=mintlify%5Bbot%5D)

[docs: fix Vale warnings from PRs merged in the last week (](https://github.com/mintlify/docs/commit/a6ec4be4349556bac939582251bf14d550385be2) [#6222](https://github.com/mintlify/docs/pull/6222) [)](https://github.com/mintlify/docs/commit/a6ec4be4349556bac939582251bf14d550385be2)

Open commit detailssuccess

Jun 18, 2026

[a6ec4be](https://github.com/mintlify/docs/commit/a6ec4be4349556bac939582251bf14d550385be2) · Jun 18, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/create/changelogs.mdx)

Open commit details

History

161 lines (127 loc) · 5.88 KB

## FilesExpand file tree

 main

/

# changelogs.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

161 lines (127 loc) · 5.88 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/create/changelogs.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Changelogs</td></tr><tr><th>description</th><td>Create product changelogs with date-based entries, RSS feed support, and subscriber notifications to keep users informed about updates.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">product updates</div></th><th><div dir="auto">release notes</div></th><th><div dir="auto">RSS</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

Create a changelog for your docs by adding [Update components](https://github.com/mintlify/docs/blob/main/components/update) to a page.

Check out the [Mintlify changelog](https://github.com/mintlify/docs/blob/main/changelog) as an example: you can include links, images, text, and demos of your new features in each update.

## Set up your changelog

1\. Create a new page in your docs such as \`changelog.mdx\` or \`updates.mdx\`. 2. Add your changelog page to your navigation scheme in your \`docs.json\`. Add an \`Update\` for each changelog entry.

```
Include relevant information like feature releases, bug fixes, or other announcements.
```

```mdx
---
title: "Changelog"
description: "Product updates and announcements"
---
<Update label="March 2025" description="v0.0.10">
  Added a new Wintergreen flavor.

  Released a new version of the Spearmint flavor, now with 10% more mint.
</Update>

<Update label="February 2025" description="v0.0.09">
  Released a new version of the Spearmint flavor.
</Update>
```

## Customize your changelog

Control how people navigate your changelog and stay up to date with your product information.

### Table of contents

Each `label` property for an `Update` automatically creates an entry in the right sidebar's table of contents. This is the default navigation for your changelog.

[![Changelog with table of contents displayed in light mode.](https://github.com/mintlify/docs/raw/main/images/changelog-toc-light.png)](https://github.com/mintlify/docs/blob/main/images/changelog-toc-light.png)

[![Changelog with table of contents displayed in dark mode.](https://github.com/mintlify/docs/raw/main/images/changelog-toc-dark.png)](https://github.com/mintlify/docs/blob/main/images/changelog-toc-dark.png)

### Tag filters

Add `tags` to your `Update` components to replace the table of contents with tag filters. Users can filter the changelog by selecting one or more tags.

When a user selects multiple tags, the changelog shows only updates that include every selected tag. The changelog hides updates without tags whenever a filter is active.

```mdx
<Update label="March 2025" description="v0.0.10" tags={["Wintergreen", "Spearmint"]}>
  Added a new Wintergreen flavor.

  Released a new version of the Spearmint flavor, now with 10% more mint.
</Update>

<Update label="February 2025" description="v0.0.09" tags={["Spearmint"]}>
  Released a new version of the Spearmint flavor.
</Update>

<Update label="January 2025" description="v0.0.08" tags={["Peppermint", "Spearmint"]}>
  Deprecated the Peppermint flavor.

  Released a new version of the Spearmint flavor.
</Update>
```

[![Changelog in light mode with the Peppermint tag filter selected.](https://github.com/mintlify/docs/raw/main/images/changelog-filters-light.png)](https://github.com/mintlify/docs/blob/main/images/changelog-filters-light.png)

[![Changelog in dark mode with the Peppermint tag filter selected.](https://github.com/mintlify/docs/raw/main/images/changelog-filters-dark.png)](https://github.com/mintlify/docs/blob/main/images/changelog-filters-dark.png)

Using \`custom\`, \`center\`, or \`wide\` page modes hides the table of contents and changelog filters. Learn more about \[page modes\](/organize/pages#page-mode).

### Subscribable changelogs

RSS feeds are only available on public documentation.

Use `Update` components to create a subscribable RSS feed at your page URL with `/rss.xml` appended. For example, `mintlify.com/docs/changelog/rss.xml`.

The RSS feed publishes entries when you add new `Update` components and when you modify headings inside of existing `Update` components.

RSS feed entries contain pure Markdown only. They exclude components, code, and HTML elements. Use the `rss` property to provide alternative text descriptions for RSS subscribers when your updates contain excluded content.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<rss xmlns:dc="http://purl.org/dc/elements/1.1/" xmlns:content="http://purl.org/rss/1.0/modules/content/" xmlns:atom="http://www.w3.org/2005/Atom" version="2.0">
  <channel>
    <title><![CDATA[Product updates]]></title>
    <description><![CDATA[New updates and improvements]]></description>
    <link>https://mintlify.com/docs</link>
    <generator>RSS for Node</generator>
    <lastBuildDate>Mon, 21 Jul 2025 21:21:47 GMT</lastBuildDate>
    <atom:link href="https://mintlify.com/docs/changelog/rss.xml" rel="self" type="application/rss+xml"/>
    <copyright><![CDATA[Mintlify]]></copyright>
    <docs>https://mintlify.com/docs</docs>
    <item>
      <title><![CDATA[June 2025]]></title>
      <link>https://mintlify.com/docs/changelog#june-2025</link>
      <guid isPermaLink="true">https://mintlify.com/docs/changelog#june-2025</guid>
      <pubDate>Mon, 23 Jun 2025 16:54:22 GMT</pubDate>
    </item>
  </channel>
</rss>
```

RSS feeds can integrate with Slack, email, or other subscription tools to notify users of product changes. Some options include:

- [Slack](https://slack.com/help/articles/218688467-Add-RSS-feeds-to-Slack)
- [Email](https://zapier.com/apps/email/integrations/rss/1441/send-new-rss-feed-entries-via-email) via Zapier
- Discord bots like [Readybot](https://readybot.io) or [RSS Feeds to Discord Bot](https://rss.app/en/bots/rssfeeds-discord-bot)

To make the RSS feed discoverable, you can display an RSS icon button that links to the feed at the top of the page. Add `rss: true` to the page frontmatter:

```mdx
---
rss: true
---
```

[![Changelog page in light mode with RSS feed button enabled.](https://github.com/mintlify/docs/raw/main/images/changelog-rss-button-light.png)](https://github.com/mintlify/docs/blob/main/images/changelog-rss-button-light.png)

[![Changelog page in dark mode with RSS feed button enabled.](https://github.com/mintlify/docs/raw/main/images/changelog-rss-button-dark.png)](https://github.com/mintlify/docs/blob/main/images/changelog-rss-button-dark.png)