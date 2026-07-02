# Source: https://github.com/mintlify/docs/blob/main/cli/preview.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# preview.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

[![mintlify[bot]](https://avatars.githubusercontent.com/in/222410?v=4&size=40)](https://github.com/apps/mintlify) [mintlify\[bot\]](https://github.com/mintlify/docs/commits?author=mintlify%5Bbot%5D)

[docs: add prerequisites to local preview guide (](https://github.com/mintlify/docs/commit/0060ad8d1c79ef68e01b86215cce184d4711a9cd) [#6253](https://github.com/mintlify/docs/pull/6253) [)](https://github.com/mintlify/docs/commit/0060ad8d1c79ef68e01b86215cce184d4711a9cd)

Open commit detailssuccess

Jun 24, 2026

[0060ad8](https://github.com/mintlify/docs/commit/0060ad8d1c79ef68e01b86215cce184d4711a9cd) · Jun 24, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/cli/preview.mdx)

Open commit details

History

84 lines (54 loc) · 2.31 KB

## FilesExpand file tree

 main

/

# preview.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

84 lines (54 loc) · 2.31 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/cli/preview.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Preview locally</td></tr><tr><th>description</th><td>Run a local preview of your Mintlify documentation site with live reload, full-text search, and AI assistant support using mint dev.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">mint dev</div></th><th><div dir="auto">local preview</div></th><th><div dir="auto">localhost</div></th><th><div dir="auto">mint login</div></th><th><div dir="auto">search</div></th><th><div dir="auto">assistant</div></th></tr></tbody></table></td></tr></tbody></table>

## Prerequisites

- The [Mintlify CLI](https://github.com/mintlify/docs/blob/main/cli/install) installed globally, or run commands with `npx mint`.
- A documentation directory with a valid `docs.json` file.

## Start the local preview

Navigate to your documentation directory containing your `docs.json` file and run:

```shell
mint dev
```

The local preview starts at `http://localhost:3000`. As you edit, changes appear in real time.

By default, the preview opens automatically in your browser. To prevent the browser from opening, use the `--no-open` flag:

```shell
mint dev --no-open
```

To generate a preview without installing the CLI globally, run:

```shell
npx mint dev
```

## Log in for search and assistant

You must authenticate the CLI with your Mintlify account to enable search and the [assistant](https://github.com/mintlify/docs/blob/main/assistant/index).

```shell
mint login
```

After you authenticate with the `mint login` command, the CLI stores your credentials in `~/.config/mintlify/config.json` so you stay logged in across sessions. The CLI also prompts you to select a default project, which commands like `mint automations` use.

Once logged in, run `mint dev` to start the local preview with search and the assistant enabled. The assistant uses the same indexed content as your deployed documentation site.

To check your authentication status, run:

```shell
mint status
```

To log out, run:

```shell
mint logout
```

## Custom ports

By default, the CLI uses port 3000. To use a different port, use the `--port` flag:

```shell
mint dev --port 3333
```

If the port is already in use, the CLI automatically tries the next available port.

## Skip OpenAPI processing

If you have many OpenAPI files, skip OpenAPI processing during local development to improve performance with the `--disable-openapi` flag:

```shell
mint dev --disable-openapi
```

## Preview as a specific group

If you use group-based access control, preview as a specific authentication group with the `--groups` flag:

```shell
mint dev --groups admin
```

See [Authentication setup](https://github.com/mintlify/docs/blob/main/deploy/authentication-setup#control-access-with-groups) for more information on groups.