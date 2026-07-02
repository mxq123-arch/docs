# Source: https://github.com/mintlify/docs/blob/main/cli/install.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

## FilesExpand file tree

 main

/

# install.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

![ethanpalm](https://avatars.githubusercontent.com/u/56270045?v=4&size=40)![claude](https://avatars.githubusercontent.com/u/81847?v=4&size=40)

[ethanpalm](https://github.com/mintlify/docs/commits?author=ethanpalm)

and

[claude](https://github.com/mintlify/docs/commits?author=claude)

[Codex MCP guide (](https://github.com/mintlify/docs/commit/4cffd85891c86485cfa41fedd0a4271fd1597e46) [#6271](https://github.com/mintlify/docs/pull/6271) [)](https://github.com/mintlify/docs/commit/4cffd85891c86485cfa41fedd0a4271fd1597e46)

Open commit detailssuccess

Jun 25, 2026

[4cffd85](https://github.com/mintlify/docs/commit/4cffd85891c86485cfa41fedd0a4271fd1597e46) · Jun 25, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/cli/install.mdx)

Open commit details

History

138 lines (102 loc) · 5.05 KB

## FilesExpand file tree

 main

/

# install.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

138 lines (102 loc) · 5.05 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/cli/install.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Install the CLI</td></tr><tr><th>description</th><td>Install the Mintlify CLI to preview documentation locally, test changes in real time, and catch build errors before deploying to production.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">CLI</div></th><th><div dir="auto">npm</div></th><th><div dir="auto">install</div></th><th><div dir="auto">Node.js</div></th><th><div dir="auto">pnpm</div></th><th><div dir="auto">mint</div></th></tr></tbody></table></td></tr></tbody></table>

## Prerequisites

- [Node.js](https://nodejs.org/en) v20.17.0+ (LTS versions recommended)

## Install the CLI

\`\`\`bash npm npm i -g mint \`\`\`

```shell
pnpm add -g mint
```

## Create a new project

To create a new documentation project from the Mintlify starter template, run the following command:

```shell
mint new [directory]
```

If you do not specify a directory, the CLI prompts you to create a new subdirectory or overwrite the current directory.

Overwriting the current directory deletes any existing files.

| Flag | Description |
| --- | --- |
| `--name` | Project name. The CLI prompts for this if not provided. |
| `--theme` | Project [theme](https://github.com/mintlify/docs/blob/main/customize/themes). The CLI prompts for this if not provided. |
| `--template` | Pre-defined template. The CLI prompts for this if not provided. |
| `--force` | Overwrite the current directory without prompting. |

In interactive mode, the CLI asks whether you want to pick a theme or clone a template. To skip the prompt, pass the `--template` flag directly:

```shell
mint new my-docs --template <template-name>
```

You can combine `--template` with `--theme` to override the template's default theme:

```shell
mint new my-docs --template <template-name> --theme <theme>
```

See available templates in the [mintlify/templates](https://github.com/mintlify/templates) repository on GitHub. In interactive mode, the CLI fetches and displays available templates automatically.

In non-interactive environments such as CI/CD pipelines or AI coding agents, you must provide either `--name` and `--theme` flags, or the `--template` flag.

## Update

If your local preview is out of sync with your deployed documentation, update the CLI to the latest version:

```shell
mint update
```

If `mint update` is not available on your version, reinstall the CLI with the latest version:

\`\`\`bash npm npm i -g mint@latest \`\`\`

```shell
pnpm add -g mint@latest
```

## Formatting

For syntax highlighting and code formatting in MDX files, use the following extensions:

- **Cursor, Devin Desktop, VS Code**: [MDX VS Code extension](https://marketplace.visualstudio.com/items?itemName=unifiedjs.vscode-mdx) and [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- **JetBrains**: [MDX IntelliJ IDEA plugin](https://plugins.jetbrains.com/plugin/14944-mdx) and [Prettier](https://prettier.io/docs/webstorm)

## Troubleshooting

This may be due to an outdated version of Node.js. Try the following:

```
1. Remove the currently installed version of the mint CLI: `npm uninstall -g mint`
2. Upgrade to Node.js v20.17.0+.
3. Reinstall the mint CLI: `npm install -g mint`
```

\*\*Solution\*\*: Go to the root of your device and delete the \`~/.mintlify\` folder. Afterwards, run \`mint dev\` again. This is due to not having the required permissions to globally install node packages.

```
**Solution**: Try running `sudo npm i -g mint`. When prompted, enter the password that you use to unlock your computer.
```

This is likely due to an outdated version of the CLI.

```
**Solution**: Run `mint update` to get the latest changes.
```

If you have any problems with the CLI package, first run \`npm ls -g\` to see what packages are globally installed. If you don't use npm, try \`which mint\` to locate the installation.

````
If you have both a `mint` and a `mintlify` package installed, uninstall `mintlify`:

```bash
npm uninstall -g mintlify
npm cache clean --force
npm i -g mint
```
````

If you run \`mint version\` and the client version displays as \`none\`, the CLI may be unable to download the client application due to a corporate firewall or VPN.

```
**Solution**: Ask your IT administrator to add `releases.mintlify.com` to your network allowlist.
```

In versions before \`4.0.1125\`, running \`npx mint dev\` or other commands from a docs repository could cause the CLI to incorrectly detect itself as a local development build. This made the CLI point to \`localhost\` URLs instead of the Mintlify production API, resulting in connection errors or unexpected behavior.

````
**Solution**: Update to the latest CLI version:

```bash
npm i -g mint@latest
```
````