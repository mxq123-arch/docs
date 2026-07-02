# Source: https://github.com/mintlify/docs/blob/main/editor/pages.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# pages.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

[![mintlify[bot]](https://avatars.githubusercontent.com/in/222410?v=4&size=40)](https://github.com/apps/mintlify) [mintlify\[bot\]](https://github.com/mintlify/docs/commits?author=mintlify%5Bbot%5D)

[docs: fix Vale warnings from PRs merged in the last week (](https://github.com/mintlify/docs/commit/a6ec4be4349556bac939582251bf14d550385be2) [#6222](https://github.com/mintlify/docs/pull/6222) [)](https://github.com/mintlify/docs/commit/a6ec4be4349556bac939582251bf14d550385be2)

Open commit detailssuccess

Jun 18, 2026

[a6ec4be](https://github.com/mintlify/docs/commit/a6ec4be4349556bac939582251bf14d550385be2) · Jun 18, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/editor/pages.mdx)

Open commit details

History

130 lines (78 loc) · 8.06 KB

## FilesExpand file tree

 main

/

# pages.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

130 lines (78 loc) · 8.06 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/editor/pages.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Create and edit pages</td></tr><tr><th>description</th><td>Create pages, edit content, upload images and video, and manage files in the Mintlify web editor with rich-text editing and search across your content.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">editor</div></th><th><div dir="auto">content</div></th><th><div dir="auto">pages</div></th><th><div dir="auto">files</div></th><th><div dir="auto">create</div></th><th><div dir="auto">edit</div></th><th><div dir="auto">media</div></th><th><div dir="auto">images</div></th><th><div dir="auto">video</div></th></tr></tbody></table></td></tr></tbody></table>

## Navigate files

The left panel has two views: **Navigation** and **Files**.

**Navigation** shows your sidebar structure as visitors see it. Click a page to open it.

**Files** shows the full file tree of your repository, including files that aren't in your navigation. Click any file to open it.

To switch between views, click the file icon or press Cmd + Shift + F (macOS) or Ctrl + Shift + F (Windows). Click the search icon or press Cmd + K (macOS) or Ctrl + K (Windows) to search by filename or page content.

## Manage files and folders

Use the Files view to organize your content:

- **Create a folder**: Click the new folder button at the top of the file tree, or right-click an existing folder and select **New folder**.
- **Rename a file or folder**: Right-click the item and select **Rename**.
- **Open unlisted files**: Click any file in the tree to open it, even if it isn't included in your navigation.

Files that aren't in your navigation remain unlisted. They exist in your repository but won't appear in the published sidebar.

## Create new pages

### Add a page to navigation

1. Click the plus button in the navigation element where you want to add a page.
2. Click **Add a page**.
3. Enter a filename. The editor adds the `.mdx` extension automatically.

### Create an unlisted page

Unlisted pages exist in your repository but don't appear in navigation. They're useful for draft content, reusable snippets, or pages you plan to add to navigation later.

Right-click any folder in the Files view and select **New file**. Enter a filename and the editor creates the page without adding it to navigation. You can add it to navigation later from the **Navigation** tab.

## Edit content

Switch between visual and source mode using the mode toggle in the toolbar below the top bar. Click the eye icon or press Cmd + Shift + M (macOS) or Ctrl + Shift + M (Windows) to switch to visual mode. Click the code icon or press Cmd + Shift + M (macOS) or Ctrl + Shift + M (Windows) to switch to source mode.

**Visual mode** shows a real-time preview as you type. Press / to open the component menu and insert components, images, videos, and other content. You can also drag and drop media files directly onto the page from your computer or from the navigation tree. Other shortcuts:

- **Insert a link**: Select text and press Cmd + K (macOS) or Ctrl + K (Windows), or drag a page from the navigation tree into the editor to create a link with the page title.
- **Link to another page**: Right-click a page in the navigation tree, click **Copy link**, then paste the link into your content. The editor recognizes internal links to other pages and converts them.
- **Insert media from your project**: Drag an image or video from the navigation tree into the page to embed it inline. Supported formats include PNG, JPG, JPEG, GIF, WebP, SVG, MP4, and WebM.
- **Insert an emoji**: Type : followed by a keyword to open the emoji picker.
- **Edit a table**: When your cursor is inside a table, use the floating toolbar to add or remove rows and columns, or merge cells.

**Source mode** gives you direct access to the MDX source. Use it for precise control over component properties and frontmatter.

For a full list of components, see [Components](https://github.com/mintlify/docs/blob/main/components). For MDX syntax, see [Format text](https://github.com/mintlify/docs/blob/main/create/text) and [Format code](https://github.com/mintlify/docs/blob/main/create/code).

### Diff view

To compare your current page against the last published version, click the **View diff** button in the toolbar, or press Cmd + Shift + D (macOS) or Ctrl + Shift + D (Windows). In visual mode this shows a visual diff. In source mode it shows a text diff. Click **Exit diff** or press the shortcut again to return to editing.

You can also open a diff from the publish menu. Click **Publish** then click any changed file in the list.

### Block actions

In visual mode, hover over any block to reveal a drag handle on the left. Click the handle to open a context menu with actions for that block:

- **Turn into**: Convert the block to a different type: text, headings, blockquote, or list.
- **Duplicate**: Insert a copy of the block immediately after it.
- **Delete**: Remove the block.

[![The block actions menu in visual mode.](https://github.com/mintlify/docs/raw/main/images/editor/block-actions-light.png)](https://github.com/mintlify/docs/blob/main/images/editor/block-actions-light.png)

[![The block actions menu in visual mode.](https://github.com/mintlify/docs/raw/main/images/editor/block-actions-dark.png)](https://github.com/mintlify/docs/blob/main/images/editor/block-actions-dark.png)

### Table of contents

In visual mode, the editor shows a minimap on the right side of the page that reflects the heading structure of your document. Hover over the minimap to expand it into a full table of contents. Click any heading to scroll to that section.

### Code block options

When editing a code block in visual mode, you can:

- **Highlight or focus lines**: Select text within the code block, then use the toolbar that appears to mark lines as highlighted or focused. Highlighting visually emphasizes lines. Focusing lines dims everything else.
- **Mark diff lines**: Select lines and use the toolbar to mark them as additions (`+`) or removals (`-`).
- **Wrap**: Toggle line wrapping in the code block settings.
- **Expandable**: Make the code block collapsible so readers can expand it on demand.

## Manage pages

- **Move**: Drag and drop pages to reorder them in navigation.
- **Rename**: Right-click a page and select **Rename**.
- **Duplicate**: Right-click a page and select **Duplicate**.
- **Delete**: Right-click a page and select **Delete**. The editor removes the page from navigation automatically.

### Pages deleted via Git

If a teammate deletes a page through Git while you have it open, the editor enters read-only mode and shows a banner. The editor preserves your content so you can copy it before navigating away.

## Configure pages

Hover over a page and click the gear icon, or right-click and select **Settings**, to configure:

- **Title**, **Slug**, and **Sidebar title**: Control how the page appears in navigation and its URL.
- **Description** and **Keywords**: Improve search and SEO.
- **Layout**: Choose from standard, wide, centered, or custom.

For details on each setting, see [Pages](https://github.com/mintlify/docs/blob/main/organize/pages).

## Add media

### Images and videos

Type /image to upload a new image or select an existing one from your repository. Type /video to upload or select a video.

You can also drag and drop files from your computer directly onto a page. In visual mode, the file inserts inline. In source mode, the editor inserts the file path at your cursor position. Images save to your `images/` folder and videos to `videos/`.

To reuse media that already lives in your project, drag an image or video file from the navigation tree onto the page. The editor embeds the asset inline.

### Light and dark image variants

After inserting an image in visual mode, hover over it to reveal the image toolbar. Use **Light/dark variants** to upload separate images for light and dark mode.

### Embed external media

Type /embed and paste a YouTube, Loom, or Vimeo URL. The editor detects the provider and generates the iframe. Searching the slash menu for `youtube`, `yt`, `loom`, or `vimeo` also surfaces the **Embed** command.

For other embeds, type /embed and toggle **Manual embed** to write custom HTML.

For more on formatting images and using the Frame component, see [Images and embeds](https://github.com/mintlify/docs/blob/main/create/image-embeds).