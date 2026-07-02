# Source: https://github.com/mintlify/docs/blob/main/deploy/authentication-setup.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# authentication-setup.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/authentication-setup.mdx)

History

477 lines (380 loc) · 19.3 KB

 main

/

# authentication-setup.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

477 lines (380 loc) · 19.3 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/authentication-setup.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Authentication setup</td></tr><tr><th>description</th><td>Configure user authentication for your site with OAuth, JWT, password, or Mintlify Auth to control access to pages and API references.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">authentication</div></th><th><div dir="auto">auth</div></th><th><div dir="auto">OAuth</div></th><th><div dir="auto">JWT</div></th><th><div dir="auto">password</div></th></tr></tbody></table></td></tr></tbody></table>

Authentication with Mintlify Auth is available on all plans.

Password, OAuth, and JWT authentication require an [Enterprise plan](https://mintlify.com/pricing?ref=authentication).

Authentication requires users to log in before accessing your content.

You can configure full authentication for all pages or partial authentication where some pages are public and others are protected.

Authentication is only available for sites hosted on a custom domain or Mintlify subdomain. For example, `docs.example.com` or `example.mintlify.site`. Authentication is **not supported** for sites with a [custom subpath](https://github.com/mintlify/docs/blob/main/deploy/docs-subpath). For example, `example.com/docs`.

## Configure authentication

Select the handshake method that you want to configure.

Password authentication provides access control only and does \*\*not\*\* support user-specific features like group-based access control or API playground pre-filling.

### Password prerequisites

- Your security requirements allow sharing passwords among users.

### Password setup

1\. In your dashboard, go to \[Authentication\]([https://app.mintlify.com/products/authentication](https://app.mintlify.com/products/authentication)). 2. In the \*\*Authentication method\*\* section, set site visibility to \*\*Private\*\*. 3. Click \*\*Password\*\*. 4. Enter a secure password. 5. Click \*\*Save changes\*\*.

```
After you save, your site redeploys. When it finishes deploying, anyone who visits your site must enter the password to access your content.
```

Securely share the password and documentation URL with authorized users.

### Password example

You host your documentation at `docs.foo.com` and you need basic access control without tracking individual users. You want to prevent public access while keeping setup simple.

**Create a strong password** in your dashboard. **Share credentials** with authorized users.

### Mintlify Auth prerequisites

- Everyone who needs to access your documentation must be a member of your Mintlify organization.

### Mintlify Auth setup

1\. In your dashboard, go to \[Authentication\]([https://app.mintlify.com/products/authentication](https://app.mintlify.com/products/authentication)). 2. In the \*\*Authentication method\*\* section, set site visibility to \*\*Private\*\*. 3. Click \*\*Authenticated\*\*. 4. Click \*\*Save changes\*\*.

```
After you save, your site redeploys. When it finishes deploying, anyone who visits your site must log in to your Mintlify organization to access your content.
```

1\. In your dashboard, go to \[Members\]([https://app.mintlify.com/settings/organization/members](https://app.mintlify.com/settings/organization/members)). 2. Add each person who should have access to your documentation. 3. Assign appropriate roles based on their editing permissions.

### Mintlify Auth example

You host your documentation at `docs.foo.com` and your entire team has access to your dashboard. You want to restrict access to team members only.

**Enable Mintlify authentication** in your dashboard settings.

**Verify team access** by checking that all team members are active in your organization.

### OAuth 2.0 prerequisites

- An OAuth or OIDC server that supports the Authorization Code Flow.
- Ability to create an API endpoint accessible by OAuth access tokens (optional, to enable group-based access control).

### OAuth 2.0 setup

1\. In your dashboard, go to \[Authentication\]([https://app.mintlify.com/products/authentication](https://app.mintlify.com/products/authentication)). 2. In the \*\*Authentication method\*\* section, set site visibility to \*\*Private\*\*. 3. Click \*\*Custom\*\*. 4. Click \*\*OAuth\*\*. 5. Configure these fields: \* \*\*Authorization URL\*\*: Your OAuth endpoint. \* \*\*Client ID\*\*: Your OAuth 2.0 client identifier. \* \*\*Client Secret\*\*: Your OAuth 2.0 client secret. \* \*\*Scopes\*\* (optional): Permissions to request. Copy the \*\*entire\*\* scope string (for example, for a scope like \`provider.users.docs\`, copy the complete \`provider.users.docs\`). Use multiple scopes if you need different access levels. \* \*\*Additional authorization parameters\*\* (optional): Additional query parameters to add to the initial authorization request. \* \*\*Token URL\*\*: Your OAuth token exchange endpoint. \* \*\*Info API URL\*\* (optional): Endpoint on your server that Mintlify calls to retrieve user info. Required for group-based access control. If omitted, the OAuth flow only verifies identity. \* \*\*Logout URL\*\* (optional): The native logout URL for your OAuth provider. When users log out, Mintlify validates the logout redirect against this configured URL for security. The redirect only succeeds if it exactly matches the configured \`logoutUrl\`. If you do not configure a logout URL, users redirect to \`/login\`. Mintlify redirects users with a \`GET\` request and does not append query parameters, so include any parameters (for example, \`returnTo\`) directly in the URL. \* \*\*Redirect URL\*\* (optional): The URL to redirect users to after authentication. 6. Click \*\*Save changes\*\*.

```
After you configure your OAuth settings, your site redeploys. When it finishes deploying, anyone who visits your site must log in to your OAuth provider to access your content.
```

1\. Copy the \*\*Redirect URL\*\* from your \[authentication settings\]([https://app.mintlify.com/products/authentication](https://app.mintlify.com/products/authentication)). 2. Add the redirect URL as an authorized redirect URL for your OAuth server. To enable group-based access control, create an API endpoint that: \* Responds to \`GET\` requests. \* Accepts an \`Authorization: Bearer \` header for authentication. \* Returns user data in the \`User\` format. See \[User data format\](#user-data-format) for more information.

```
Mintlify calls this endpoint with the OAuth access token to retrieve user information. No additional query parameters are sent.

Add this endpoint URL to the **Info API URL** field in your [authentication settings](https://app.mintlify.com/products/authentication).
```

### OAuth 2.0 example

You host your documentation at `docs.foo.com` and you have an existing OAuth server at `auth.foo.com` that supports the Authorization Code Flow.

**Configure your OAuth server details** in your dashboard:

- **Authorization URL**: `https://auth.foo.com/authorization`
- **Client ID**: `ydybo4SD8PR73vzWWd6S0ObH`
- **Scopes**: `['provider.users.docs']`
- **Token URL**: `https://auth.foo.com/exchange`
- **Info API URL**: `https://api.foo.com/docs/user-info`
- **Logout URL**: `https://auth.foo.com/logout?returnTo=https%3A%2F%2Fdocs.foo.com`

**Create a user info endpoint** at `api.foo.com/docs/user-info`, which requires an OAuth access token with the `provider.users.docs` scope, and returns:

```json
{
  "groups": ["engineering", "admin"],
  "expiresAt": 1735689600,
  "apiPlaygroundInputs": {
    "header": {
      "Authorization": "Bearer user_abc123"
    }
  }
}
```

Control session length with the \`expiresAt\` field in your user info response. This is a Unix timestamp (seconds since epoch) indicating when the session should expire. See \[User data format\](#user-data-format) for more details.

**Configure your OAuth server to allow redirects** to your callback URL.

### JWT prerequisites

- An authentication system that can generate and sign JWTs.
- A backend service that can create redirect URLs.

### JWT setup

1\. In your dashboard, go to \[Authentication\]([https://app.mintlify.com/products/authentication](https://app.mintlify.com/products/authentication)). 2. In the \*\*Authentication method\*\* section, set site visibility to \*\*Private\*\*. 3. Click \*\*Custom\*\*. 4. Click \*\*JWT\*\*. 5. Enter the URL of your existing login flow. 6. Click \*\*Save changes\*\*. 7. Click \*\*Generate new key\*\*. 8. Store your key securely where it can be accessed by your backend.

```
After you generate a private key, your site redeploys. When it finishes deploying, anyone who visits your site must log in to your JWT authentication system to access your content.
```

Modify your existing login flow to include these steps after user authentication:

```
* Create a JWT containing the authenticated user's info in the `User` format. See [User data format](#user-data-format) for more information.
* Sign the JWT with your secret key, using the EdDSA algorithm.
* Create a redirect URL back to the `/login/jwt-callback` path of your docs, including the JWT as the hash.
```

### JWT example

You host your documentation at `docs.foo.com` with an existing authentication system at `foo.com`. You want to extend your login flow to grant access to the docs while keeping your docs separate from your dashboard (or you don't have a dashboard).

Create a login endpoint at `https://foo.com/docs-login` that extends your existing authentication.

After verifying user credentials:

- Generate a JWT with user data in Mintlify's format.
- Sign the JWT and redirect to `https://docs.foo.com/login/jwt-callback#{SIGNED_JWT}`.

\`\`\`ts TypeScript import \* as jose from 'jose'; import { Request, Response } from 'express';

const TWO\_WEEKS\_IN\_MS = 1000 \* 60 \* 60 \* 24 \* 7 \* 2; const DOCS\_HOST = 'docs.example.com';

const signingKey = await jose.importPKCS8(process.env.MINTLIFY\_PRIVATE\_KEY, 'EdDSA');

export async function handleRequest(req: Request, res: Response) { const user = { host: DOCS\_HOST, // Must match your docs URL expiresAt: Math.floor((Date.now() + TWO\_WEEKS\_IN\_MS) / 1000), // 2 week session expiration groups: res.locals.user.groups, apiPlaygroundInputs: { header: { "Authorization": `Bearer ${res.locals.user.apiKey}`, }, }, };

const jwt = await new jose.SignJWT(user) .setProtectedHeader({ alg: 'EdDSA' }) .setExpirationTime('10 s') // 10 second JWT expiration .sign(signingKey);

return res.redirect(`https://${DOCS_HOST}/login/jwt-callback#${jwt}`); }

````

```python Python
import jwt # pyjwt
import os

from datetime import datetime, timedelta
from fastapi.responses import RedirectResponse

private_key = os.getenv(MINTLIFY_JWT_PEM_SECRET_NAME, '')
DOCS_HOST = 'docs.example.com'

@router.get('/auth')
async def return_mintlify_auth_status(current_user):
 jwt_token = jwt.encode(
 payload={
 'host': DOCS_HOST, # Must match your docs URL
 'exp': int((datetime.now() + timedelta(seconds=10)).timestamp()), # 10 second JWT expiration
 'expiresAt': int((datetime.now() + timedelta(weeks=2)).timestamp()), # 2 week session expiration
 'groups': ['admin'] if current_user.is_admin else [],
 'apiPlaygroundInputs': {
 'header': {
 'Authorization': f'Bearer {current_user.api_key}',
 },
 },
 },
 key=private_key,
 algorithm='EdDSA'
 )

 return RedirectResponse(url=f'https://{DOCS_HOST}/login/jwt-callback#{jwt_token}', status_code=302)
````

### Redirect unauthenticated users

When an unauthenticated user tries to access a protected page, the redirect to your login URL preserves the user's intended destination.

1.  User attempts to visit a protected page: `https://docs.foo.com/quickstart`.
2.  Redirect to your login URL with a redirect query parameter: `https://foo.com/docs-login?redirect=%2Fquickstart`.
3.  After authentication, redirect to `https://docs.foo.com/login/jwt-callback?redirect=%2Fquickstart#{SIGNED_JWT}`.
4.  User lands in their original destination.

## Make pages public

When using authentication, all pages require authentication to access by default. You can make specific pages viewable without authentication at the page or group level with the `public` property.

### Individual pages

To make a page public, add `public: true` to the page's frontmatter.

```mdx
---
title: "Public page"
public: true
---
```

### Groups of pages

To make all pages in a group public, add `"public": true` beneath the group's name in the `navigation` object of your `docs.json`.

```json
{
 "navigation": {
 "groups": [
 {
 "group": "Public group",
 "public": true,
 "icon": "play",
 "pages": [
 "quickstart",
 "installation",
 "settings"
 ]
 },
 {
 "group": "Private group",
 "icon": "pause",
 "pages": [
 "private-information",
 "secret-settings"
 ]
 }
 ]
 }
}
```

## Control access with groups

When you use OAuth or JWT authentication, you can restrict specific pages to certain user groups. This is useful when you want different users to see different content based on their role or attributes.

Manage groups through user data passed during authentication. See [User data format](https://github.com/#user-data-format) for details.

```json
{
 "groups": ["admin", "beta-users"],
 "expiresAt": 1735689600
}
```

Specify which groups can access specific pages using the `groups` property in frontmatter.

```mdx
---
title: "Admin dashboard"
groups: ["admin"]
---
```

Users must belong to at least one of the listed groups to access the page. If a user tries to access a page without the required group, they'll receive a 404 error.

### How groups interact with public pages

-   All pages require authentication by default.
-   Pages with a `groups` property are only accessible to authenticated users in those groups.
-   Pages without a `groups` property are accessible to all authenticated users.
-   Pages with `public: true` and no `groups` property are accessible to everyone.

```mdx
---
title: "Public guide"
public: true
---
```

```mdx
---
title: "API reference"
---
```

```mdx
---
title: "Advanced configurations"
groups: ["pro", "enterprise"]
---
```

## User data format

When using OAuth or JWT authentication, your system returns user data that controls session length, group membership, and [content personalization](https://github.com/mintlify/docs/blob/main/create/personalization).

\`\`\`tsx Format type User = { host?: string; expiresAt?: number; groups?: string\[\]; content?: Record; apiPlaygroundInputs?: { server?: Record; header?: Record; query?: Record; cookie?: Record; path?: Record; }; }; \`\`\`

```json
{
 "host": "docs.example.com",
 "expiresAt": 1735689600,
 "groups": ["admin", "beta-users"],
 "content": {
 "firstName": "Jane",
 "company": "Acme Corp"
 },
 "apiPlaygroundInputs": {
 "header": {
 "Authorization": "Bearer user_abc123"
 },
 "server": {
 "baseUrl": "https://api.foo.com"
 }
 }
}
```

\*\*Required for JWT authentication.\*\* The hostname of your documentation site. The string must exactly match the domain where you deploy your documentation. Mintlify validates that the JWT's host matches the requesting host to prevent token reuse across different sites. Session expiration time in seconds since epoch. When the current time passes this value, the user must re-authenticate.

**For JWT:** This differs from the JWT's `exp` claim, which determines when a JWT is considered invalid. Set the JWT `exp` claim to a short duration (10 seconds or less) for security. Use `expiresAt` for the actual session length (hours to weeks).

List of groups the user belongs to. Pages with matching \`groups\` in their frontmatter are accessible to this user.

**Example**: A user with `groups: ["admin", "engineering"]` can access pages tagged with either the `admin` or `engineering` groups.

Custom data accessible in MDX pages via the \`user\` variable for \[personalized content\](/create/personalization#dynamic-mdx-content). Pre-fills API playground fields with user-specific values. When a user authenticates, these values populate the corresponding input fields in the API playground. Users can override pre-filled values, and their overrides persist in local storage.

Only values that match the current endpoint's security scheme are applied.

Header values to pre-fill, keyed by header name. Query parameter values to pre-fill, keyed by parameter name. Cookie values to pre-fill, keyed by cookie name. Server variable values to pre-fill, keyed by variable name. Path parameter values to pre-fill, keyed by parameter name.

## Feature availability

Some features behave differently or are unavailable when you enable authentication.

| Feature | Public | Fully authenticated (all pages protected) | Partially authenticated (some public pages) |
| :-- | :-- | :-- | :-- |
| [llms.txt and llms-full.txt](https://github.com/mintlify/docs/blob/main/ai/llmstxt) | Full support | Available behind authentication, so AI tools may not be able to access the files | Publicly accessible, reflecting public pages only |
| [MCP server](https://github.com/mintlify/docs/blob/main/ai/model-context-protocol) | Full support | Requires authentication to connect | Available without authentication for public pages and with authentication for protected pages |
| [Markdown export](https://github.com/mintlify/docs/blob/main/ai/markdown-export) | Full support | Full support, respects user groups | Full support, respects user groups |
| [PDF export](https://github.com/mintlify/docs/blob/main/optimize/pdf-exports) | Full support | Full support, respects user groups. Authenticated pages export with images and assets included. | Full support, respects user groups. Authenticated pages export with images and assets included. |
| [Search](https://github.com/mintlify/docs/blob/main/assistant/index) | Full support | Full support, respects user groups | Full support, respects user groups |
| [Assistant](https://github.com/mintlify/docs/blob/main/assistant/index) | Full support | Full support, respects user groups | Full support, respects user groups |
| [skill.md](https://github.com/mintlify/docs/blob/main/ai/skillmd) | Full support | Not supported | Not supported |
| [Sitemap](https://github.com/mintlify/docs/blob/main/optimize/seo#sitemaps-and-robotstxt-files) | Full support | Available behind authentication, but excludes pages in groups | Available behind authentication, but excludes pages in groups |
| [robots.txt](https://github.com/mintlify/docs/blob/main/optimize/seo#sitemaps-and-robotstxt-files) | Full support | Available behind authentication | Available behind authentication |