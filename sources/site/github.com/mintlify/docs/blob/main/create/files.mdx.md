# Source: https://github.com/mintlify/docs/blob/main/create/files.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# files.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

![mintlify[bot]](https://avatars.githubusercontent.com/in/222410?v=4&size=40)![ethanpalm](https://avatars.githubusercontent.com/u/56270045?v=4&size=40)

[mintlify\[bot\]](https://github.com/mintlify/docs/commits?author=mintlify%5Bbot%5D)

and

[ethanpalm](https://github.com/mintlify/docs/commits?author=ethanpalm)

[Fix Vale style warnings from PRs merged in the last week (](https://github.com/mintlify/docs/commit/693dbc361f1434a26c867bb63f1d23ed93f9b20f) [#5690](https://github.com/mintlify/docs/pull/5690) [)](https://github.com/mintlify/docs/commit/693dbc361f1434a26c867bb63f1d23ed93f9b20f)

Open commit detailssuccess

May 7, 2026

[693dbc3](https://github.com/mintlify/docs/commit/693dbc361f1434a26c867bb63f1d23ed93f9b20f) · May 7, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/create/files.mdx)

Open commit details

History

52 lines (39 loc) · 1.77 KB

## FilesExpand file tree

 main

/

# files.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

52 lines (39 loc) · 1.77 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/create/files.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Files</td></tr><tr><th>description</th><td>Serve static assets like images, videos, PDFs, and data files from your documentation repository with automatic optimization and CDN delivery.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">static assets</div></th><th><div dir="auto">supported file types</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

Mintlify automatically serves static assets from your documentation repository at the appropriate path on your domain. For example, if you have `/images/my-logo.png` in your repo, the image file is available at `https://docs.your-project.com/images/my-logo.png`.

You can make any supported file type available to your users, including OpenAPI specifications, images, videos, and more.

Files must be less than 20 MB.

File serving is not supported for documentation sites with authentication enabled. If your site requires authentication, static files are not accessible at their direct URLs.

## Supported file types

Supported file types for all plans:

- **Images**: `.png`, `.jpg`, `.jpeg`, `.gif`, `.webp`, `.svg`, `.ico`
- **Video**: `.mp4`, `.webm`
- **Audio**: `.mp3`, `.wav`
- **Data**: `.json`, `.yaml`
- **Stylesheet**: `.css`
- **Scripts**: `.js`
- **Fonts**: `.woff`, `.woff2`, `.ttf`, `.eot`

Supported file types for Enterprise plans:

- **Documents**: `.pdf`, `.txt`
- **Data**: `.xml`, `.csv`
- **Archives**: `.zip`

## File organization

Organize your files using folders to keep your repository easy to navigate:

```
/your-project
  |- docs.json
  |- images/
    |- logo.png
    |- screenshots/
      |- dashboard.png
  |- assets/
    |- whitepaper.pdf
    |- demo-video.mp4
```

Files are served from the root of your domain, so the structure in your repository directly maps to the URL structure. From the previous example, `assets/whitepaper.pdf` would be available at `https://docs.your-project.com/assets/whitepaper.pdf`.