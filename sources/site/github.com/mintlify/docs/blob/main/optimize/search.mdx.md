# Source: https://github.com/mintlify/docs/blob/main/optimize/search.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# search.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/optimize/search.mdx)

History

117 lines (86 loc) · 4.91 KB

## FilesExpand file tree

 main

/

# search.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

117 lines (86 loc) · 4.91 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/optimize/search.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Search</td></tr><tr><th>description</th><td>Configure the in-product search bar on your Mintlify documentation site, including ranking boosts and the number of results returned per query.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">search</div></th><th><div dir="auto">search ranking</div></th><th><div dir="auto">search boost</div></th><th><div dir="auto">boost</div></th><th><div dir="auto">search prioritization</div></th><th><div dir="auto">maximum search results</div></th><th><div dir="auto">max results</div></th><th><div dir="auto">searchable</div></th><th><div dir="auto">exclude from search</div></th></tr></tbody></table></td></tr></tbody></table>

Configure how the search bar on your Mintlify-hosted documentation site behaves. These settings only affect in-product search. They do not change how external search engines index your pages.

## Boost search ranking

Use `boost` to bias the in-product search ranking of specific pages or sections. The value is a numeric multiplier applied to each chunk's relevance score: `boost: 3` makes a chunk three times as relevant as it would be without a boost.

### Boost a single page

Set `boost` in a page's [frontmatter](https://github.com/mintlify/docs/blob/main/organize/pages) to multiply its search ranking.

```mdx
---
title: "Custom domain"
description: "Connect your custom domain to your Mintlify documentation."
boost: 3
---
```

### Boost a navigation group

Set `boost` on a group in your `docs.json` navigation to apply the multiplier to every page under it.

```json
{
  "navigation": {
    "groups": [
      {
        "group": "Get started",
        "boost": 5,
        "pages": [
          "quickstart",
          "concepts"
        ]
      }
    ]
  }
}
```

A page inherits the boost factor from its nearest ancestor that sets one. A child page or nested group can override the inherited boost by setting its own `boost` value. A page's frontmatter `boost` always wins over a value inherited from the navigation.

### De-prioritize content

Use a value below `1` to push pages further down in search results. For example, `boost: 0.5` halves a page's relevance score relative to other pages. A `boost` of `1` is equivalent to no boost.

```mdx
---
title: "Deprecated API"
description: "Documentation for the deprecated v1 API."
boost: 0.25
---
```

Boost factors compose with the existing relevance score. Use them sparingly. Large multipliers can cause less-relevant pages to dominate search results and degrade overall search quality.

### Recommended boost range

`boost` accepts any positive number. In practice, keep values between `0.1` and `10`:

- `0.1`–`0.9`: de-prioritize legacy, deprecated, or supporting content.
- `1`: no change (equivalent to omitting `boost`).
- `2`–`5`: prioritize a key landing page, quickstart, or heavily used reference.
- `5`–`10`: reserve for a handful of top-level pages that should almost always appear first.

Avoid values greater than `10`. Very large multipliers overwhelm the underlying relevance score and cause boosted pages to appear in search results even when they don't match the query well.

## Exclude a page from search

Pages are searchable by default. The `searchable` field is optional and defaults to `true`. Set `searchable: false` in a page's [frontmatter](https://github.com/mintlify/docs/blob/main/organize/pages) to exclude it from your documentation site's search results. `searchable` is a page-level field only. To exclude every page under a navigation tab or group, hide the tab or group instead. See [Hidden pages](https://github.com/mintlify/docs/blob/main/organize/hidden-pages) for tab- and group-level controls.

```mdx
---
title: "Internal notes"
description: "Reference material we don't want surfacing in search."
searchable: false
---
```

Unlike `noindex`, `searchable: false` doesn't affect external SEO. The page is still:

- Crawlable by external search engines
- Listed in your `sitemap.xml`

It's removed from your documentation site's search results and the AI assistant context.

Use `searchable: false` for pages that should stay reachable through direct links or external search engines but shouldn't surface when users search inside your docs. Examples include deep reference pages, legacy content, and supporting material that would otherwise crowd out more relevant results.

To exclude a page from both in-product search and external indexing, use [`noindex: true`](https://github.com/mintlify/docs/blob/main/optimize/seo#disable-indexing) instead.

## Maximum search results

Control how many results the search bar returns per query from your dashboard. The default is `6` results. You can set any value between `1` and `100`.

In your dashboard, navigate to **Settings** > **Deployment** > **Search**, set **Maximum search results** to the value you want, and select **Save changes**.

[![The Search settings page in the dashboard with the Maximum search results stepper set to 6.](https://github.com/mintlify/docs/raw/main/images/search-settings-light.png)](https://github.com/mintlify/docs/blob/main/images/search-settings-light.png)

[![The Search settings page in the dashboard with the Maximum search results stepper set to 6.](https://github.com/mintlify/docs/raw/main/images/search-settings-dark.png)](https://github.com/mintlify/docs/blob/main/images/search-settings-dark.png)

Higher values surface more matches per query, which is useful for sites with broad topic coverage where users expect to scan many candidates. Lower values keep the results panel compact and push users toward the top-ranked match.