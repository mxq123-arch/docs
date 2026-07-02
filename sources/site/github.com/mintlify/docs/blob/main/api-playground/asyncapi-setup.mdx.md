# Source: https://github.com/mintlify/docs/blob/main/api-playground/asyncapi-setup.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# asyncapi-setup.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/api-playground/asyncapi-setup.mdx)

History

142 lines (114 loc) · 3.54 KB

 main

/

# asyncapi-setup.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

142 lines (114 loc) · 3.54 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/api-playground/asyncapi-setup.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>AsyncAPI setup</td></tr><tr><th>description</th><td>Set up real-time WebSocket documentation using AsyncAPI specification files to generate interactive channel and message reference pages.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">asyncapi</div></th><th><div dir="auto">websocket</div></th></tr></tbody></table></td></tr></tbody></table>

## Demo

See the [WebSocket playground](https://github.com/mintlify/docs/blob/main/api-playground/websocket-playground) for an example of the AsyncAPI playground.

## Add an AsyncAPI specification file

To create pages for your WebSocket channels, you must have a valid AsyncAPI schema document in either JSON or YAML format that follows the [AsyncAPI specification 3.0](https://www.asyncapi.com/docs/reference/specification/v3.0.0).

Use the \[AsyncAPI Studio\]([https://studio.asyncapi.com/](https://studio.asyncapi.com/)) to validate your AsyncAPI schema.

```json
/your-project
  |- docs.json
  |- asyncapi.json
```

## Auto-populate WebSocket pages

To automatically generate pages for all channels in your AsyncAPI schema, add an `asyncapi` property to any navigation element. The `asyncapi` property accepts a path to an AsyncAPI schema document in your documentation repo, a URL to a hosted AsyncAPI document, or an array of links to AsyncAPI schema documents.

### Examples with tabs

```json
"navigation": {
  "tabs": [
    {
        "tab": "API Reference",
        "asyncapi": "/path/to/asyncapi.json"
    }
  ]
}

```

```json
"navigation": {
  "tabs": [
    {
        "tab": "API Reference",
        "asyncapi": "https://github.com/asyncapi/spec/blob/master/examples/simple-asyncapi.yml"
    }
  ]
}
```

```json
"navigation": {
  "tabs": [
    {
      "tab": "API Reference",
      "asyncapi": [
        "/path/to/events.json",
        "/path/to/webhooks.json"
      ]
    }
  ]
}
```

When you specify multiple AsyncAPI files, each file generates its own set of channel pages.

### Examples with groups

```json
"navigation": {
  "tabs": [
    {
      "tab": "AsyncAPI",
      "groups": [
        {
          "group": "Websockets",
          "asyncapi": {
            "source": "/path/to/asyncapi.json",
            "directory": "websockets"
          }
        }
      ]
    }
  ]
}
```

The \`directory\` field is optional. If not specified, Mintlify adds the files to the \*\*api-reference\*\* folder of the docs repository.

### Examples with nested groups

The `asyncapi` property supports nested groups. Mintlify generates the channel pages and adds them to the nested group, alongside any existing pages.

This is useful when you want to organize WebSocket channels as a subsection of a broader API group, or when you need to combine multiple AsyncAPI specifications under a shared parent group.

```json
"navigation": {
  "tabs": [
    {
      "tab": "API Reference",
      "groups": [
        {
          "group": "Voice API",
          "pages": [
            "voice/overview",
            {
              "group": "Voice API Commands",
              "asyncapi": "/path/to/voice-asyncapi.json"
            }
          ]
        }
      ]
    }
  ]
}
```

## Schema rendering

Array schemas and combinatorial schemas (`oneOf`, `anyOf`, `allOf`) expand to show their child attributes inline in the generated channel pages. Readers can open the expandable section for an array item schema or select a tab for each `oneOf`/`anyOf` option to see all nested fields.

## Channel page

If you want more control over how you order your channels or if you want to reference only specific channels, create an MDX file with the `asyncapi` property in the frontmatter.

```mdx
---
title: "Websocket Channel"
asyncapi: "/path/to/asyncapi.json channelName"
---
```