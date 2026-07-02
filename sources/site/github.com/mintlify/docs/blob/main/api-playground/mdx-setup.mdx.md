# Source: https://github.com/mintlify/docs/blob/main/api-playground/mdx-setup.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# mdx-setup.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/api-playground/mdx-setup.mdx)

History

255 lines (205 loc) · 5.89 KB

## FilesExpand file tree

 main

/

# mdx-setup.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

255 lines (205 loc) · 5.89 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/api-playground/mdx-setup.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Create manual API pages</td></tr><tr><th>description</th><td>Create API reference pages manually with MDX files when you need full control over layout for small APIs, prototypes, or custom docs.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">API documentation</div></th><th><div dir="auto">endpoint documentation</div></th></tr></tbody></table></td></tr></tbody></table>

You can manually define API endpoints in individual MDX pages. This approach is useful for small APIs or prototyping.

## Setup

````
In your `docs.json` file, define your base URL and authentication method.

```json Example docs.json
"api": {
 "mdx": {
 "server": "https://api.acme.com/",
 "auth": {
 "method": "key",
 "name": "x-api-key"
 }
 }
}
```

If you want to hide the API playground, set the `display` field to `none`. You don't need to include an authentication method if you hide the playground.

```json
"api": {
 "playground": {
 "display": "none"
 }
}
```

Find a full list of API configurations in [Settings](/organize/settings-api).
````

Create an MDX file for each endpoint. Define the \`title\` and \`api\` in the frontmatter:

````
```mdx
---
title: 'Create new user'
api: 'POST /v1/users'
---
```

The `api` frontmatter field accepts either a full URL or a relative path:

- **Full URL** like `POST https://api.acme.com/v1/users`. The `server` field in `docs.json` is ignored for that endpoint.
- **Relative path** like `POST /v1/users`. Requires a `server` field in `docs.json`. The server URL is prepended to the path.

Specify path parameters by wrapping them in `{}`:

```bash
https://api.example.com/v1/endpoint/{userId}
```

To override the global playground display mode for a specific page, add `playground` to the frontmatter:

```mdx
---
title: 'Create new user'
api: 'POST https://api.mintlify.com/user'
playground: 'none'
---
```

Options:
- `playground: 'interactive'` - Display the interactive playground (default)
- `playground: 'simple'` - Display a copyable endpoint with no playground
- `playground: 'none'` - Hide the playground entirely
````

Use \[parameter and response fields\](/components/fields) to document your endpoint's parameters and return values.

````
```mdx
<ParamField path="userId" type="string" required>
 Unique identifier for the user
</ParamField>

<ParamField body="email" type="string" required>
 User's email address
</ParamField>

<ResponseField name="id" type="string" required>
 Unique identifier for the newly created user
</ResponseField>

<ResponseField name="email" type="string" required>
 User's email address
</ResponseField>
```
````

Add your endpoint pages to the navigation by updating the \`pages\` field in your \`docs.json\`:

````
```json docs.json
"navigation": {
 "tabs": [
 {
 "tab": "API Reference",
 "groups": [
 {
 "group": "Users",
 "pages": [
 "api-reference/users/create-user",
 "api-reference/users/get-user",
 "api-reference/users/update-user"
 ]
 },
 {
 "group": "Orders",
 "pages": [
 "api-reference/orders/create-order",
 "api-reference/orders/list-orders"
 ]
 }
 ]
 }
 ]
}
```

Each page path corresponds to an MDX file in your docs repository. For example, `api-reference/users/create-user.mdx`. Learn more about structuring your docs in [Navigation](/organize/navigation).

### Using OpenAPI endpoints in navigation

If you have an OpenAPI specification, you can reference endpoints directly in your navigation without creating individual MDX files. Reference specific endpoints by including the OpenAPI file path and the endpoint:

```json docs.json
"navigation": {
 "pages": [
 "introduction",
 "/path/to/users-openapi.json POST /users",
 "/path/to/orders-openapi.json GET /orders"
 ]
}
```

You can also set a default OpenAPI spec for a navigation group and reference endpoints by method and path:

```json docs.json
{
 "group": "API reference",
 "openapi": "/path/to/openapi-v1.json",
 "pages": [
 "overview",
 "authentication",
 "GET /users",
 "POST /users",
 {
 "group": "Orders",
 "openapi": "/path/to/openapi-v2.json",
 "pages": [
 "GET /orders",
 "POST /orders"
 ]
 }
 ]
}
```

For more details on OpenAPI integration, see [OpenAPI setup](/api-playground/openapi-setup).
````

## Enable authentication

You can set authentication globally in `docs.json` or override it on individual pages using the `authMethod` field in frontmatter. A page-specific method overrides the global setting.

### Bearer token

```json
"api": {
  "mdx": {
    "auth": {
      "method": "bearer"
    }
  }
}
```

```mdx
---
title: "Your page title"
authMethod: "bearer"
---
```

### Basic authentication

```json
"api": {
  "mdx": {
    "auth": {
      "method": "basic"
    }
  }
}
```

```mdx
---
title: "Your page title"
authMethod: "basic"
---
```

### API key

```json
"api": {
  "mdx": {
    "auth": {
      "method": "key",
      "name": "x-api-key"
    }
  }
}
```

```mdx
---
title: "Your page title"
authMethod: "key"
---
```

### None

To disable authentication on a specific page, set `authMethod` to `none`:

```mdx
---
title: "Your page title"
authMethod: "none"
---
```