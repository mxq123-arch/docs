# Source: https://github.com/mintlify/docs/blob/main/what-is-mintlify.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# what-is-mintlify.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/what-is-mintlify.mdx)

History

48 lines (31 loc) · 2.45 KB

 main

/

# what-is-mintlify.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

48 lines (31 loc) · 2.45 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/what-is-mintlify.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>What is Mintlify?</td></tr><tr><th>description</th><td>Mintlify is a documentation platform designed for developers and AI, with smart search, interactive API playgrounds, and built-in analytics.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">overview</div></th><th><div dir="auto">how it works</div></th><th><div dir="auto">architecture</div></th></tr></tbody></table></td></tr></tbody></table>

Mintlify hosts your content as a website. Your content lives in a Git repository as MDX files, and Mintlify builds and deploys your site automatically when you push a change.

## The three parts of a Mintlify project

**Your repository** is the source of truth for your documentation. It contains an MDX file for every page and a `docs.json` file that configures your site's navigation, theme, and settings. You can use your own GitHub or GitLab repository, or let Mintlify create one for you during onboarding.

**The Mintlify dashboard** connects to your repository and lets you manage your site. Use it to monitor deployments, configure settings, manage your team, and edit content directly in the browser.

**Your site**, powered by Mintlify. Mintlify builds your site from your repository and deploys it at a `.mintlify.site` URL by default. When you're ready, you can point a custom domain to your site.

Loading

flowchart LR
 WE\["Web editor"\] --> Repo\[("Git repository")\]
 Local\["Local editor"\] --> Repo
 Repo -- "Webhook" --> Build\["Mintlify build"\]
 Build --> Site\["Live site"\]

## Editing content

There are two ways to edit your content, and you can switch between them freely.

- **Web editor**: Edit and publish pages in your browser. The editor commits changes back to your Git repository automatically.
- **CLI and local editor**: Clone your repository, run `mint dev` to preview your site locally, then push changes to deploy.

Multiple team members can work in either workflow at the same time, using Git branches to manage parallel changes. Anyone who can push to your repository can update your content.

## AI features

Built-in AI features help people and AI find and understand your content, and help you maintain your content.

The **assistant** lets your users ask questions and get cited answers from your content.

The **agent** helps your team create and maintain content by generating updates from scheduled automations, pull requests merging in your feature repository, or Slack threads.

See [AI-native documentation](https://github.com/mintlify/docs/blob/main/ai-native) for an overview of all AI features.

## Next steps

Deploy your first documentation site in minutes.