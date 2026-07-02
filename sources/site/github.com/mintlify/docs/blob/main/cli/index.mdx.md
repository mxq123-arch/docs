# Source: https://github.com/mintlify/docs/blob/main/cli/index.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# index.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/cli/index.mdx)

History

48 lines (35 loc) · 2.22 KB

## FilesExpand file tree

 main

/

# index.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

48 lines (35 loc) · 2.22 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/cli/index.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Mintlify CLI</td></tr><tr><th>description</th><td>Use the Mintlify CLI to preview docs locally, test changes in real time, and run accessibility, link, and validation checks before deploying.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">CLI</div></th><th><div dir="auto">mint</div></th><th><div dir="auto">local development</div></th><th><div dir="auto">preview</div></th></tr></tbody></table></td></tr></tbody></table>

import SkillMcpPrompt from "/snippets/skill-mcp-prompt.mdx";

[![Decorative graphic representing the CLI.](https://github.com/mintlify/docs/raw/main/images/installation/local-development-light.png)](https://github.com/mintlify/docs/blob/main/images/installation/local-development-light.png) [![Decorative graphic representing the CLI.](https://github.com/mintlify/docs/raw/main/images/installation/local-development-dark.png)](https://github.com/mintlify/docs/blob/main/images/installation/local-development-dark.png)

## About the CLI

Use the [CLI](https://www.npmjs.com/package/mint) to preview your documentation locally, test changes in real time, and run quality checks before deploying to production.

The CLI runs on your machine and connects to your Mintlify deployment when you need live data.

### Preview locally

Run `mint dev` to preview your documentation at `localhost:3000`. As you write and update your content, changes appear in real time without deploying. Log in to enable search and the AI assistant in your local preview.

### Run quality checks

Run `mint broken-links` to find broken links, `mint a11y` to check accessibility, and `mint validate` to validate your documentation build before it reaches production.

### Check agent readiness

Run `mint score` to evaluate how well agents can navigate a documentation site. With no arguments, the command scores your configured subdomain. Pass a URL to score any other site. The command displays an overall readiness score and individual check results.

### Manage configuration

Run `mint config` to set persistent defaults like your documentation subdomain.

Working on your docs locally with an AI coding tool? Install the Mintlify \[skill\](/ai/skillmd) and \[MCP server\](/ai/model-context-protocol) so your editor has the context it needs to write Mintlify-aware content.

## Next steps

- [Install the CLI](https://github.com/mintlify/docs/blob/main/cli/install): Get the CLI installed and ready to use.
- [Preview locally](https://github.com/mintlify/docs/blob/main/cli/preview): Run a local development server with search and assistant support.
- [Commands](https://github.com/mintlify/docs/blob/main/cli/commands): Complete reference for all commands and flags.