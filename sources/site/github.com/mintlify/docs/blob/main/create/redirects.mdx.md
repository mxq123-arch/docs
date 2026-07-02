# Source: https://github.com/mintlify/docs/blob/main/create/redirects.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# redirects.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/create/redirects.mdx)

History

124 lines (92 loc) · 3.75 KB

## FilesExpand file tree

 main

/

# redirects.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

124 lines (92 loc) · 3.75 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/create/redirects.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Redirects</td></tr><tr><th>description</th><td>Configure URL redirects in docs.json for moved, renamed, or deleted documentation pages to preserve SEO rankings and prevent broken links.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">redirects</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

When you change the path of a file in your docs folder, it also changes the URL path to that page. This may happen when restructuring your docs or changing the sidebar title.

## Redirects

Redirect \*\*sources\*\* cannot include URL anchors like \`path#anchor\` or query parameters like \`path?query=value\`. Destinations may include anchors (e.g. \`/destination/path#section\`).

Add the `redirects` field to the top level of your `docs.json` file to set up redirects.

```json
{
  "name": "My docs",
  "redirects": [
    {
      "source": "/source/path",
      "destination": "/destination/path"
    }
  ]
}
```

This redirects `/source/path` to `/destination/path`.

By default, redirects are permanent (308). To use a temporary redirect (307), set `permanent` to `false`.

```json
"redirects": [
  {
    "source": "/source/path",
    "destination": "/destination/path",
    "permanent": false
  }
]
```

Both 307 and 308 preserve the HTTP method of the original request (unlike 301 and 302), making them suitable for redirecting POST requests.

Use a permanent (308) redirect when a page has moved permanently. For renamed slugs, restructured navigation, or removed pages that map to a replacement. Search engines transfer SEO ranking to the destination and browsers cache the redirect.

Use a temporary (307) redirect for short-term rerouting, such as maintenance pages, A/B tests, or campaign links you plan to reuse. Search engines keep the source URL in their index and don't transfer ranking.

### Redirect limits

There is no hard cap on the number of redirects you can define in `docs.json`. Very large redirect arrays (thousands of entries) can slow deploys and make the file harder to review, so consolidate with [wildcard redirects](https://github.com/#wildcard-redirects) where possible.

### Wildcard redirects

To match a wildcard path, use `*` after a parameter. In this example, `/beta/:slug*` matches `/beta/introduction` and redirects it to `/v2/introduction`.

```json
"redirects": [
  {
    "source": "/beta/:slug*",
    "destination": "/v2/:slug*"
  }
]
```

### Partial wildcard redirects

Use partial wildcards to match URL segments that start with a specific prefix.

```json
"redirects": [
  {
    "source": "/articles/concepts-*",
    "destination": "/collections/overview"
  }
]
```

This matches any URLs with the `/articles/concepts-` path, such as `/articles/concepts-getting-started` and `/articles/concepts-overview`, and redirects them all to `/collections/overview`.

You can also substitute the captured wildcard value in the destination.

```json
"redirects": [
  {
    "source": "/old/article-*",
    "destination": "/new/article-*"
  }
]
```

This redirects `/old/article-123` to `/new/article-123`, preserving the captured value after the prefix.

### Avoid infinite redirects

To avoid infinite loops, do not create circular redirects where paths redirect back to each other.

```json
"redirects": [
  {
    "source": "/docs/:slug*",
    "destination": "/help/:slug*"
  },
  {
    "source": "/help/:slug*",
    "destination": "/docs/:slug*"
  }
]
```

## When redirects take effect

Redirects in `docs.json` apply at request time on Mintlify's hosting layer, so they go live as soon as your changes are deployed. Preview deployments apply redirects too, which lets you verify behavior before merging to your production branch.

To test redirects locally, run `mint dev` and visit the source path in your browser. The local dev server applies the redirects defined in your `docs.json`.

## Check for broken links

Find broken links with the [CLI](https://github.com/mintlify/docs/blob/main/cli).

```shell
mint broken-links
```