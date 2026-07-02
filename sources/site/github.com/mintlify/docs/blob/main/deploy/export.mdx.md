# Source: https://github.com/mintlify/docs/blob/main/deploy/export.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

## FilesExpand file tree

 main

/

# export.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/deploy/export.mdx)

History

85 lines (64 loc) · 3.51 KB

## FilesExpand file tree

 main

/

# export.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

85 lines (64 loc) · 3.51 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/deploy/export.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Offline export</td></tr><tr><th>description</th><td>Export your documentation site as a self-contained zip archive for offline viewing, internal distribution, or air-gapped environment hosting.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">export</div></th><th><div dir="auto">offline</div></th><th><div dir="auto">zip</div></th><th><div dir="auto">static site</div></th><th><div dir="auto">distribution</div></th><th><div dir="auto">mint export</div></th></tr></tbody></table></td></tr></tbody></table>

Use `mint export` to package your entire documentation site into a self-contained zip archive. Recipients can unzip and view the docs in their browser without an internet connection, a Mintlify account, or any build tools—they only need [Node.js](https://nodejs.org) installed.

This is useful when you need to distribute documentation to users who can't access your live site, such as for on-premise customers, air-gapped environments, or internal compliance reviews.

## Prerequisites

- The [CLI](https://github.com/mintlify/docs/blob/main/cli/install) installed and up to date
- [Node.js](https://nodejs.org) v20.17.0+ installed

## Export your site

Navigate to your documentation directory containing your `docs.json` file and run:

```shell
mint export
```

The CLI builds your site, crawls every page defined in your navigation, and packages the output into a zip file in your current directory.

### Options

| Flag | Description | Default |
| --- | --- | --- |
| `--output <path>` | Set the output zip file path. | `export.zip` |
| `--groups <group>` | Mock [user groups](https://github.com/mintlify/docs/blob/main/deploy/authentication-setup#control-access-with-groups) for the export. Useful when your docs use group-based access control and you want the archive to include restricted pages. | — |
| `--disable-openapi` | Skip OpenAPI file generation during the export. Use this if you have many OpenAPI specs and want faster builds. | — |

For example, to export your site to a custom filename with a specific user group:

```shell
mint export --output customer-docs.zip --groups enterprise
```

The export only includes pages listed in your navigation. \[Hidden pages\](/organize/hidden-pages) are not included in the archive.

## What's in the zip

The exported archive contains everything needed to view your docs offline:

| File | Purpose |
| --- | --- |
| HTML pages | Pre-rendered version of every page in your navigation |
| `_next/static/` | Bundled CSS, JavaScript, and other static assets |
| `serve.js` | Zero-dependency Node.js HTTP server that serves the site |
| `Start Docs.command` | macOS launcher—double-click to open the docs |
| `Start Docs.bat` | Windows launcher—double-click to open the docs |

## View the exported docs

Share the zip file with anyone who has Node.js installed. To view the docs:

1\. Unzip the archive. 2. Open a terminal in the unzipped directory. 3. Run \`node serve.js\`. 4. Open \`http://localhost:3000\` in your browser. 1. Unzip the archive. 2. Double-click \*\*Start Docs.command\*\*. 3. The docs open in your default browser at \`http://localhost:3000\`.

```
<Note>
  macOS may block the file because it was downloaded from the internet. If you see a security warning, go to **System Settings > Privacy & Security** and click **Open Anyway**. See [Apple's guide to overriding security settings](https://support.apple.com/guide/mac-help/mh40617/mac) for details.
</Note>
```

1\. Unzip the archive. 2. Double-click \*\*Start Docs.bat\*\*. 3. The docs open in your default browser at \`http://localhost:3000\`.

```
<Note>
  Windows may show a "Windows protected your PC" warning because the file was downloaded from the internet. Click **More info**, then click **Run anyway**.
</Note>
```