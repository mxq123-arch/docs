# Source: https://github.com/mintlify/docs/blob/main/deploy/vercel.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# vercel.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/vercel.mdx)

History

63 lines (46 loc) · 3.32 KB

 main

/

# vercel.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

63 lines (46 loc) · 3.32 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/vercel.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Vercel</td></tr><tr><th>description</th><td>Configure Vercel rewrites to serve your Mintlify documentation at a subpath on your main domain with step-by-step vercel.json setup.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">vercel.json</div></th><th><div dir="auto">Vercel deployment</div></th><th><div dir="auto">rewrites configuration</div></th><th><div dir="auto">subpath routing</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

import { VercelJsonGenerator } from "/snippets/vercel-json-generator.mdx";

Configure your `vercel.json` file to proxy requests from your main domain to your documentation at a subpath.

## vercel.json file

The `vercel.json` file configures how your project builds and deploys. It sits in your project's root directory and controls various aspects of your deployment, including routing, redirects, headers, and build settings.

Mintlify uses the `rewrites` configuration in your `vercel.json` file to proxy requests from your main domain to your documentation.

Rewrites map incoming requests to different destinations without changing the URL in the browser. When someone visits `yoursite.com/docs`, Vercel internally fetches content from `your-subdomain.mintlify.site/docs`, but the user still sees `yoursite.com/docs` in their browser. This is different from redirects, which send users to another URL entirely.

## Configuration

### Host at `/docs` subpath

1. Navigate to [Custom domain setup](https://app.mintlify.com/settings/deployment/custom-domain) in your dashboard.
 
2. Set the **Host at `/docs`** toggle to on.
 
 [![Screenshot of the Custom domain setup page. The Host at `/docs` toggle is on and highlighted by an orange rectangle.](https://github.com/mintlify/docs/raw/main/images/subpath/toggle-light.png)](https://github.com/mintlify/docs/blob/main/images/subpath/toggle-light.png) [![Screenshot of the Custom domain setup page. The Host at `/docs` toggle is on and highlighted by an orange rectangle.](https://github.com/mintlify/docs/raw/main/images/subpath/toggle-dark.png)](https://github.com/mintlify/docs/blob/main/images/subpath/toggle-dark.png)
3. Enter your domain.
 
4. Click **Add domain**.
 
5. Add the following rewrites to your `vercel.json` file. Replace `[subdomain]` with your subdomain, which appears at the end of your dashboard URL. For example, `app.mintlify.com/your-organization/your-subdomain` has a domain identifier of `your-subdomain`.
 
 ```json
    {
      "rewrites": [
        {
          "source": "/docs",
          "destination": "https://[subdomain].mintlify.site/docs"
        },
        {
          "source": "/docs/:match*",
          "destination": "https://[subdomain].mintlify.site/docs/:match*"
        }
      ]
    }
    ```
 

The `rewrites` configuration maps the `/docs` subpath on your domain to the `/docs` subpath on your documentation.

- **`source`**: The path pattern on your domain that triggers the rewrite.
- **`destination`**: Where the request should be proxied to.
- **`:match*`**: A wildcard that captures any path segments after your subpath.

For more information, see [Configuring projects with vercel.json: Rewrites](https://vercel.com/docs/projects/project-configuration#rewrites) in the Vercel documentation.

### Host at custom subpath

To use a custom subpath (any path other than `/docs`), you must organize your documentation files within your repository to match your subpath structure. For example, if you host your documentation at `yoursite.com/help`, your documentation files must be in a `help/` directory.

Use the generator below to create your rewrites configuration. Add the rewrites to your `vercel.json` file.