# Source: https://github.com/mintlify/docs/blob/main/editor/navigation.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# navigation.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/editor/navigation.mdx)

History

44 lines (30 loc) · 2.5 KB

## FilesExpand file tree

 main

/

# navigation.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

44 lines (30 loc) · 2.5 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/editor/navigation.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Organize navigation</td></tr><tr><th>description</th><td>Reorder pages, add groups, and manage your documentation sidebar structure using drag-and-drop in the Mintlify web editor — no docs.json edits needed.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">editor</div></th><th><div dir="auto">navigation</div></th><th><div dir="auto">sidebar</div></th><th><div dir="auto">structure</div></th></tr></tbody></table></td></tr></tbody></table>

Use the navigation sidebar to organize your documentation. Changes you make in the editor sync to your repository when you publish—you don't need to edit `docs.json` manually.

## Add navigation elements

Click **Add new** at the bottom of the navigation tree to add a new element at the root level. To add an element nested inside another, click the plus button next to that element.

After creating an element, drag and drop it to reorder or nest it. Hover over an element and click the gear icon to configure its properties.

Right-click a **page** to open its settings or delete it.

Right-click a **navigation element** to open its settings, convert it to a different element type, duplicate it, add a page inside it, add a group inside it, ungroup it, or delete it.

Some elements cannot nest inside other elements. For example, tabs cannot nest inside groups. The editor prevents you from creating invalid combinations.

## Navigation elements

Choose the right structure for your content:

- **Pages** — Individual documentation files. The core building block of navigation.
- **Groups** — Collapsible sections that cluster related pages together. Can nest within other groups.
- **Tabs** — Top-level sections with horizontal navigation at the top of your site. Use tabs when you have distinct areas like API Reference and Guides.
- **Anchors** — Persistent items at the top of your sidebar. Useful for quick access to external resources or top-level sections. Can be global to appear on every page.
- **Dropdowns** — Expandable menus at the top of your sidebar. A lighter alternative to tabs for multiple related sections.
- **Menus** — Dropdown navigation items within a tab for direct links to specific pages.
- **Products** — A switcher for multiple distinct product documentation sets, each with its own navigation structure.
- **Versions** — A switcher for multiple simultaneous documentation versions.
- **Languages** — A switcher for documentation in multiple languages.

## Configure elements

Hover over any navigation element and click the gear icon to set:

- **Title**: The label shown in the sidebar.
- **Icon**: A visual marker next to the label.
- **Tag**: A badge like "NEW" or "BETA" to highlight the item.