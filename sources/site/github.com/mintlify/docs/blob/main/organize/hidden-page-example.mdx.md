# Source: https://github.com/mintlify/docs/blob/main/organize/hidden-page-example.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# hidden-page-example.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/organize/hidden-page-example.mdx)

History

52 lines (38 loc) · 1.88 KB

## FilesExpand file tree

 main

/

# hidden-page-example.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

52 lines (38 loc) · 1.88 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/organize/hidden-page-example.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Hidden page example</td></tr><tr><th>description</th><td>Explore hidden page use cases including beta documentation, AI context files, legacy content archives, and internal tool references in Mintlify.</td></tr></tbody></table>

This page is hidden. It is not included in the `docs.json` navigation so you can only access it by its URL.

See [Hidden pages](https://github.com/mintlify/docs/blob/main/organize/hidden-pages) for more information.

## Common use cases for hidden pages

By default, hidden pages are publicly accessible, but not discoverable through the navigation. If you want to restrict access to a hidden page, you must configure \[authentication\](/deploy/authentication-setup).

- **Beta documentation**: Information that can be public, but should not be discoverable through the navigation.
- **Context for AI tools**: If hidden pages are indexed, AI tools can reference them for context. Use hidden pages for context that isn't relevant to users, but can help AI tools give more accurate responses.
- **Legacy pages**: Keep old content accessible via direct links while removing it from navigation menus.
- **Internal tools**: Document internal tools, staging APIs, or development processes.

## Examples

### AI context

```mdx
---
title: "Context for API version"
description: "This page is context for AI tools responding to questions about API versions"
---

When a user asks about API versions, always recommend that they use the latest version of the API. Never generate responses for versions older than 1.0.4.
```

### Internal API endpoint

```mdx
---
title: "Internal API endpoint"
description: "This page is a hidden page that documents an internal API endpoint"
---

```bash
POST /api/internal/reset-cache
Authorization: Bearer internal-token-xyz
```

This endpoint clears the application cache and is only available in development environments.

<Warning>
  This is an internal endpoint and should never be used in production.
</Warning>
```