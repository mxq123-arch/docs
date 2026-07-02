# Source: https://github.com/mintlify/docs/blob/main/quickstart.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# quickstart.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/quickstart.mdx)

History

169 lines (132 loc) · 6.46 KB

## FilesExpand file tree

 main

/

# quickstart.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

169 lines (132 loc) · 6.46 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/quickstart.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Quickstart</td></tr><tr><th>description</th><td>Get started with Mintlify by deploying your documentation site in minutes and making your first content change with the web editor or Git.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">quickstart</div></th><th><div dir="auto">deploy</div></th><th><div dir="auto">get started</div></th><th><div dir="auto">first steps</div></th><th><div dir="auto">tutorial</div></th><th><div dir="auto">setup</div></th><th><div dir="auto">onboarding</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

import SkillMcpPrompt from "/snippets/skill-mcp-prompt.mdx";

After you complete this guide, you'll have a live documentation site ready to customize and update.

## Before you begin

Mintlify uses a docs-as-code approach to manage your documentation. Every page on your site has a corresponding file stored in your documentation repository.

When you connect your documentation repository to your project, you can work on your documentation locally or in the web editor and sync any changes to your remote repository.

Using an AI coding tool?

Copy the following prompt to add the Mintlify [skill](https://github.com/mintlify/docs/blob/main/ai/skillmd) and [MCP server](https://github.com/mintlify/docs/blob/main/ai/model-context-protocol) for better results when updating your documentation.

## Deploy your documentation site

Go to [mintlify.com/start](https://mintlify.com/start) and complete the onboarding process. During onboarding, you'll connect your GitHub account, create or select a repository for your documentation, and install the GitHub App to enable automatic deployments.

After onboarding, your documentation site deploys and is accessible at your `.mintlify.site` URL.

If you want to get started quickly without connecting your own repository, you can skip the Git provider connection during onboarding. Mintlify creates a private repository in a private organization and automatically configures the GitHub App for you.

```
This lets you use the web editor immediately. If you want to use your own repository later, go to [Git Settings](https://app.mintlify.com/settings/deployment/git-settings) in your dashboard to migrate your content using the Git setup wizard. See [Clone to your own repository](/deploy/github#clone-to-your-own-repository) for details.
```

## View your deployed site

Your documentation site is now deployed at `https://<your-project-name>.mintlify.site`.

Find your exact URL on the **Overview** page of your [dashboard](https://app.mintlify.com/).

[![Overview page of the Mintlify dashboard.](https://github.com/mintlify/docs/raw/main/images/quickstart/mintlify-domain-light.png)](https://github.com/mintlify/docs/blob/main/images/quickstart/mintlify-domain-light.png)

[![Overview page of the Mintlify dashboard.](https://github.com/mintlify/docs/raw/main/images/quickstart/mintlify-domain-dark.png)](https://github.com/mintlify/docs/blob/main/images/quickstart/mintlify-domain-dark.png)

Your site is ready to view immediately. Use this URL for testing and sharing with your team. Before sharing with your users, you may want to add a \[custom domain\](/customize/custom-domain).

## Make your first change

The CLI requires \[Node.js\]([https://nodejs.org/en](https://nodejs.org/en)) v20.17.0 or higher. Use an LTS version for stability.

```
    <CodeGroup>

    ```bash npm
 npm i -g mint
 ```

    ```bash pnpm
 pnpm add -g mint
 ```

    </CodeGroup>

    See [Install the CLI](/cli/install) for full details and troubleshooting.
  </Step>
  <Step title="Clone your repository">
    If you haven't already cloned your repository locally, clone it using Git:

    ```bash
 git clone <your-repository-url>
 ```

    If your repository is in Mintlify's private organization, see [Clone to your own repository](/deploy/github#clone-to-your-own-repository) to move it to your account first.
  </Step>
  <Step title="Edit a page">
    Open `index.mdx` in your preferred editor and update the description in the frontmatter:

    ```mdx
 ---
 title: "Introduction"
 description: "Your custom description here"
 ---
 ```
  </Step>
  <Step title="Preview locally">
    Run the following command from your documentation directory:

    ```bash
 mint dev
 ```

    View your preview at `http://localhost:3000`.
  </Step>
  <Step title="Push your changes">
    Commit and push your changes to trigger a deployment:

    ```bash
 git add .
 git commit -m "Update description"
 git push
 ```

    Mintlify automatically deploys your changes. View your deployment status on the [Overview](https://app.mintlify.com/) page of your dashboard.
  </Step>
</Steps>
```

Navigate to the \[web editor\]([https://app.mintlify.com/editor](https://app.mintlify.com/editor)) in your dashboard. Open the \*\*Introduction\*\* page and update the description.

```
    <Frame>
      <img
        alt="Introduction page open in the web editor with the description edited to say Hello world!."
        className="block dark:hidden"
        src="/images/quickstart/hello-world-light.png"
      />
      <img
        alt="Introduction page open in the web editor with the description edited to say Hello world!."
        className="hidden dark:block"
        src="/images/quickstart/hello-world-dark.png"
      />
    </Frame>
  </Step>
  <Step title="Publish">
    Click **Publish** in the top-right of the web editor toolbar.
  </Step>
  <Step title="View live">
    On the [Overview](https://app.mintlify.com/) page of your dashboard, you can see your site's deployment status. When it finishes deploying, refresh your documentation site to see your changes live.
  </Step>
</Steps>
```

## Next steps

Edit documentation in your browser and preview how your pages look when published. Find broken links, check accessibility, validate OpenAPI specs, and more. Use your own domain for your documentation site.