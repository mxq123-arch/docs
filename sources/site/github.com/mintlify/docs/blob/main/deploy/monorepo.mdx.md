# Source: https://github.com/mintlify/docs/blob/main/deploy/monorepo.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# monorepo.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/monorepo.mdx)

History

58 lines (48 loc) · 1.95 KB

 main

/

# monorepo.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

58 lines (48 loc) · 1.95 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/monorepo.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Monorepo setup</td></tr><tr><th>description</th><td>Configure the documentation path and content directory in a monorepo project so Mintlify deploys only from your designated docs folder.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">monorepo</div></th><th><div dir="auto">content directory</div></th><th><div dir="auto">multi-project repository</div></th></tr></tbody></table></td></tr></tbody></table>

Configure Mintlify to deploy documentation from a specific directory within a monorepo. This setup lets you maintain documentation alongside your code in repositories that contain multiple projects or services.

A typical monorepo structure might look like this:

```
your-repo/
├── apps/
│   ├── web/
│   └── api/
├── docs/
│   ├── docs.json
│   └── quickstart.mdx
└── package.json
```

In this example, you'd set your documentation path to `/docs`.

## Prerequisites

- Admin access to your Mintlify project.
- Documentation files organized in a dedicated directory within your monorepo.
- A valid `docs.json` in your documentation directory.

## Configure monorepo deployment

Navigate to \[Git Settings\]([https://app.mintlify.com/settings/deployment/git-settings](https://app.mintlify.com/settings/deployment/git-settings)) in your dashboard.

[![The project settings panel in the Git Settings menu. The Set up as monorepo toggle button is enabled and a path to the /docs directory is specified.](https://github.com/mintlify/docs/raw/main/images/monorepo-light.png)](https://github.com/mintlify/docs/blob/main/images/monorepo-light.png)

[![The project settings panel in the Git Settings menu. The Set up as monorepo toggle button is enabled and a path to the /docs directory is specified.](https://github.com/mintlify/docs/raw/main/images/monorepo-dark.png)](https://github.com/mintlify/docs/blob/main/images/monorepo-dark.png)

1\. Click the \*\*Set up as monorepo\*\* toggle. 2. Enter the relative path to your docs directory. For example, if your docs are in the \`docs\` directory, enter \`/docs\`. Do not include a trailing slash in the path. 3. Click \*\*Save changes\*\*.