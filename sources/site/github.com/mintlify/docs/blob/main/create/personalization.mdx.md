# Source: https://github.com/mintlify/docs/blob/main/create/personalization.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# personalization.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

![mintlify[bot]](https://avatars.githubusercontent.com/in/222410?v=4&size=40)![ethanpalm](https://avatars.githubusercontent.com/u/56270045?v=4&size=40)

[mintlify\[bot\]](https://github.com/mintlify/docs/commits?author=mintlify%5Bbot%5D)

and

[ethanpalm](https://github.com/mintlify/docs/commits?author=ethanpalm)

[Improve SEO descriptions across 177 pages (](https://github.com/mintlify/docs/commit/f8e015ff62970c6222a37c7b480981c300ed2712) [#4993](https://github.com/mintlify/docs/pull/4993) [)](https://github.com/mintlify/docs/commit/f8e015ff62970c6222a37c7b480981c300ed2712)

Open commit detailsfailure

Mar 31, 2026

[f8e015f](https://github.com/mintlify/docs/commit/f8e015ff62970c6222a37c7b480981c300ed2712) · Mar 31, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/create/personalization.mdx)

Open commit details

History

216 lines (173 loc) · 6.13 KB

## FilesExpand file tree

 main

/

# personalization.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

216 lines (173 loc) · 6.13 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/create/personalization.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Personalized content</td></tr><tr><th>description</th><td>Show personalized content based on user authentication data, group memberships, and custom variables to tailor documentation per audience.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">content personalization</div></th><th><div dir="auto">personalization</div></th><th><div dir="auto">user data</div></th><th><div dir="auto">groups</div></th><th><div dir="auto">dynamic</div></th><th><div dir="auto">prefill</div></th></tr></tbody></table></td></tr></tbody></table>

Personalization requires \[authentication\](/deploy/authentication-setup) configured with OAuth or JWT.

Customize content for your users when they log in to your documentation site. You can prefill API keys, show content specific to a user's plan or role, and filter API reference content based on group membership.

## API key prefilling

Automatically populate API playground fields with user-specific values by returning matching field names in your user data. Include the values in the `apiPlaygroundInputs` field of your [user data](https://github.com/mintlify/docs/blob/main/deploy/authentication-setup#user-data-format).

```json
{
  "apiPlaygroundInputs": {
    "header": { "X-API-Key": "user_api_key_123" },
    "server": { "subdomain": "acme" }
  }
}
```

The field names must match the names defined in your OpenAPI specification. Only values that match the current endpoint's security scheme are applied.

## Dynamic MDX content

Display content based on user information like name, plan, or organization with the `user` variable in your MDX pages. Include custom data in the `content` field of your [user data](https://github.com/mintlify/docs/blob/main/deploy/authentication-setup#user-data-format).

```json
{
  "content": {
    "firstName": "Jane",
    "company": "Acme Corp",
    "plan": "Enterprise"
  }
}
```

Reference these values in your MDX.

```mdx
Welcome back, {user.firstName}! Your {user.plan} plan includes 100 seats for members in your {user.company} organization.
```

For conditional rendering based on user data, use the `user` variable in JSX components.

```js
{
  user.plan === 'enterprise'
    ? <>Contact your admin to enable this feature.</>
    : <>See <a href="https://yoursite.com/pricing">pricing</a> for information about upgrading.</>
}
```

The \`user\` variable is an empty object for logged-out users. Use optional chaining on all \`user\` fields to prevent errors. For example, \`{user.org?.plan}\` instead of \`{user.org.plan}\`.

## Page visibility

Restrict pages to specific user groups by adding `groups` to page frontmatter. Users must belong to at least one listed group to access the page.

```mdx
---
title: "Admin settings"
groups: ["admin"]
---
```

For more details on how groups interact with public pages, see [Control access with groups](https://github.com/mintlify/docs/blob/main/deploy/authentication-setup#control-access-with-groups).

## OpenAPI content filtering

Filter API reference content based on user groups with the `x-mint` extension in your OpenAPI specification. You can filter entire endpoints, individual schema properties, `oneOf` variants, and enum values.

### Filter endpoints

Add `x-mint.groups` to an operation or path to restrict the endpoint page to specific user groups. Users not in the listed groups won't see the endpoint in navigation or be able to access its page.

```json
{
  "paths": {
    "/billing": {
      "get": {
        "summary": "Get billing details",
        "x-mint": {
          "groups": ["admin", "billing"]
        },
        "responses": {
          "200": {
            "description": "Billing details"
          }
        }
      }
    }
  }
}
```

```json
{
  "paths": {
    "x-mint": {
      "groups": ["admin", "billing"]
    },
    "/billing": {
      "get": {
        "summary": "Get billing details",
      }
    },
    "/users": {
      "get": {
        "summary": "Get user details",
      }
    }
  }
}
```

### Filter schema properties

Add `x-mint.groups` to individual properties within request bodies, parameters, or responses. Properties without `x-mint.groups` remain visible to all users.

```json
{
  "components": {
    "schemas": {
      "User": {
        "type": "object",
        "properties": {
          "name": {
            "type": "string"
          },
          "internal_id": {
            "type": "string",
            "x-mint": {
              "groups": ["admin"]
            }
          }
        }
      }
    }
  }
}
```

In this example, all users see the `name` property. Only users in the `admin` group see the `internal_id` property.

### Filter oneOf variants

Add `x-mint.groups` to individual `oneOf` options to restrict which schema variants a user can see.

```json
{
  "schema": {
    "oneOf": [
      {
        "title": "Enterprise config",
        "type": "object",
        "x-mint": {
          "groups": ["enterprise"]
        },
        "properties": {
          "sso_enabled": { "type": "boolean" }
        }
      },
      {
        "title": "Standard config",
        "type": "object",
        "properties": {
          "notifications": { "type": "boolean" }
        }
      }
    ]
  }
}
```

### Filter enum values

Use the `x-mint-enum` extension to restrict individual enum values by group. List each restricted value as a key, with its allowed groups as the value. Enum values not listed in `x-mint-enum` are visible to all users.

```json
{
  "type": "string",
  "enum": ["free", "pro", "enterprise"],
  "x-mint-enum": {
    "pro": ["pro", "enterprise"],
    "enterprise": ["enterprise"]
  }
}
```

In this example, all users see `free`. Users in the `pro` or `enterprise` groups see `pro`. Only users in the `enterprise` group see `enterprise`.

\`x-mint-enum\` is a separate top-level extension on the schema object, not nested under \`x-mint\`.

## User data format

Your authentication system returns user data that controls personalization. The `groups`, `content`, and `apiPlaygroundInputs` fields described on this page are all part of the user data object.

For the full user data format and field reference, see [User data format](https://github.com/mintlify/docs/blob/main/deploy/authentication-setup#user-data-format).

## Logout behavior

Logout occurs on the client side. When users click the logout button, Mintlify clears their stored session data in the browser.

To limit how long personalization data persists, set the `expiresAt` field in your user data.