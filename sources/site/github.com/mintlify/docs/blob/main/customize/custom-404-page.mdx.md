# Source: https://github.com/mintlify/docs/blob/main/customize/custom-404-page.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# custom-404-page.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/customize/custom-404-page.mdx)

History

41 lines (30 loc) · 1.42 KB

## FilesExpand file tree

 main

/

# custom-404-page.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

41 lines (30 loc) · 1.42 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/customize/custom-404-page.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Custom 404 page</td></tr><tr><th>description</th><td>Customize the title, description, and appearance of your documentation site's 404 error page to match your brand and guide visitors.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">404 error page</div></th><th><div dir="auto">custom error pages</div></th></tr></tbody></table></td></tr></tbody></table>

All 404 pages automatically suggest relevant pages based on the requested URL. If users land on a 404 page, an agent analyzes the path and retrieves semantically related pages from your documentation to help them find what they're looking for.

You can customize the title and description of the 404 error page. Use the description to add helpful links or guidance.

## Configuration

Configure your 404 page in the `errors.404` section of your `docs.json` file:

```json
"errors": {
  "404": {
    "redirect": false,
    "title": "I can't be found",
    "description": "What ever **happened** to this _page_?"
  }
}
```

## Parameters

Whether to automatically redirect to the home page when a page is not found.

Set to `true` to redirect to the home page.

Set to `false` to show the custom 404 page.

Custom title for the 404 error page. This replaces the default "Page not found" heading. Custom description for the 404 error page. Supports MDX formatting including links, bold, italic text, and custom components.