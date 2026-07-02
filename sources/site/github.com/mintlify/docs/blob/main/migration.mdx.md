# Source: https://github.com/mintlify/docs/blob/main/migration.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# migration.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/migration.mdx)

History

204 lines (139 loc) · 25 KB

## FilesExpand file tree

 main

/

# migration.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

204 lines (139 loc) · 25 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/migration.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Migrate to Mintlify</td></tr><tr><th>description</th><td>Migrate your documentation to Mintlify from Docusaurus, ReadMe, GitBook, or another platform with step-by-step instructions and CLI tooling.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">migration</div></th><th><div dir="auto">Docusaurus</div></th><th><div dir="auto">ReadMe</div></th><th><div dir="auto">import</div></th></tr></tbody></table></td></tr></tbody></table>

This guide helps you move your existing documentation to Mintlify. Choose automated migration for supported platforms or manual migration for complete control over the process.

## Choose your migration path

- If you currently use Docusaurus or ReadMe -> **Automated migration**
- If you have a public GitHub repository -> **Auto-generated migration**
- If you are migrating from any other platform -> **Manual migration**

Migrate your documentation using the [@mintlify/scraping package](https://www.npmjs.com/package/@mintlify/scraping). The package scrapes your content and converts it to use Mintlify components.

### Supported platforms

} horizontal /> } horizontal />

If you host your documentation on another platform, see the manual migration steps.

### Install the scraper

Install the `@mintlify/scraping` package to get started.

```shell
npm install @mintlify/scraping@latest -g
```

### Scrape pages and sections

The migration tool automatically detects your documentation platform and converts your content. It saves prepared files locally in the `./docs` folder by default.

For large documentation sites, migrate smaller sections one at a time rather than the entire site at once.

**Migrate entire sections:**

```shell
mintlify-scrape section https://your-docs-site.com/docs
```

**Migrate single pages:**

```shell
mintlify-scrape page https://your-docs-site.com/docs/getting-started
```

**Filter specific paths:**

Use the `--filter` (or `-f`) option to scrape only URLs matching a specific path prefix.

```shell
mintlify-scrape section https://your-docs-site.com --filter=/docs
```

The filter matches the specified path and all nested paths. For example, `--filter=/docs` matches `/docs`, `/docs/getting-started`, `/docs/api/reference`, and so on.

**Migrate OpenAPI specifications:**

```shell
mintlify-scrape openapi-file [openApiFilename]
```

### Add prepared content to your Mintlify project

After scraping your existing documentation platform, you are ready to build your docs on Mintlify.

Confirm that you scraped all of your pages. Then add these files to the documentation repository that you created during the onboarding process. This is usually a GitHub repository.

Mintlify can generate a complete documentation site for any public GitHub repository, whether it already contains documentation or just code.

Replace `github.com` with `mintlify.com` in any public repository URL:

```
https://mintlify.com/github-owner/repository-name
```

Mintlify analyzes your repository and generates a complete documentation site that you can further customize.

Migrate your documentation from any platform with full control over the process.

### Content migration

To migrate your content to Mintlify, you need:

- A valid `docs.json` for your site settings and navigation. See [Global settings](https://github.com/mintlify/docs/blob/main/organize/settings) and [Navigation](https://github.com/mintlify/docs/blob/main/organize/navigation) for more information.
- A Markdown file (`.md` or `.mdx`) for each page of your documentation. MDX is the recommended format. See [Pages](https://github.com/mintlify/docs/blob/main/organize/pages) for more information.
- (Optional) An OpenAPI specification for your API endpoint pages. See [OpenAPI setup](https://github.com/mintlify/docs/blob/main/api-playground/openapi-setup) for more information.

1. If your content is already in Markdown format, copy the content to your Mintlify project. Otherwise, convert your content to MDX format.
2. Create your `docs.json` referencing the paths to your Markdown pages.
3. If you have OpenAPI specifications, add them to your `docs.json` and configure the API playground. You can also generate MDX pages from your spec using the [`@mintlify/scraping`](https://www.npmjs.com/package/@mintlify/scraping) package:

```shell
npx @mintlify/scraping@latest openapi-file <openApiFilename> -o <folder-name>
```

If you migrate your content as \`.md\` files, convert them to \`.mdx\` to support interactive features like React components.

### Asset migration

1. Copy assets to your repository's `images/` directory.
2. Update references in your Markdown files:
 
 ```mdx
    ![Alt text](/images/screenshot.png)
    ```
 

## Post-migration checklist

After completing your migration (automated or manual), check the following:

- All pages render
- Navigation works as intended
- Internal links resolve properly
- Images and assets load correctly
- Code blocks display with proper syntax highlighting
- Search works
- Correct deployment branch