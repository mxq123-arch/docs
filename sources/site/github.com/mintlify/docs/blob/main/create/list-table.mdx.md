# Source: https://github.com/mintlify/docs/blob/main/create/list-table.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# list-table.mdx

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

[Improve SEO descriptions across 177 pages (](https://github.com/mintlify/docs/commit/f8e015ff62970c6222a37c7b480981c300ed2712) [#4993](https://github.com/mintlify/docs/pull/4993) [)](https://github.com/mintlify/docs/commit/f8e015ff62970c6222a37c7b480981c300ed2712)

Open commit detailsfailure

Mar 31, 2026

[f8e015f](https://github.com/mintlify/docs/commit/f8e015ff62970c6222a37c7b480981c300ed2712) · Mar 31, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/create/list-table.mdx)

Open commit details

History

95 lines (72 loc) · 2.36 KB

## FilesExpand file tree

 main

/

# list-table.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

95 lines (72 loc) · 2.36 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/create/list-table.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Lists and tables</td></tr><tr><th>description</th><td>Format structured data in your documentation with Markdown tables, ordered and unordered lists, nested structures, and task list checkboxes.</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">ordered</div></th><th><div dir="auto">unordered</div></th><th><div dir="auto">Markdown tables</div></th><th><div dir="auto">table formatting</div></th></tr></tbody></table></td></tr></tbody></table>

## Lists

Lists follow the official [Markdown syntax](https://www.markdownguide.org/basic-syntax/#lists-1).

### Ordered list

To create an ordered list, add numbers followed by a period before list items.

1. First item
2. Second item
3. Third item
4. Fourth item

```mdx
1. First item
2. Second item
3. Third item
4. Fourth item
```

### Unordered list

To create an unordered list, add dashes (`-`), asterisks (`*`), or plus signs (`+`) before list items.

- First item
- Second item
- Third item
- Fourth item

```mdx
- First item
- Second item
- Third item
- Fourth item
```

### Nested list

Indent list items to nest them.

- First item
- Second item
 - Additional item
 - Additional item
- Third item

```mdx
- First item
- Second item
  - Additional item
  - Additional item
- Third item
```

## Tables

Tables follow the official [Markdown syntax](https://www.markdownguide.org/extended-syntax/#tables).

To add a table, use three or more hyphens (`---`) to create each column's header, and use pipes (`|`) to separate each column. For compatibility, you should also add a pipe on either end of the row.

| Property | Description |
| --- | --- |
| Name | Full name of user |
| Age | Reported age |
| Joined | Whether the user joined the community |

```mdx
| Property | Description                           |
| -------- | ------------------------------------- |
| Name     | Full name of user                     |
| Age      | Reported age                          |
| Joined   | Whether the user joined the community |
```

### Column alignment

Use colons in the separator row to align column content:

| Left aligned | Center aligned | Right aligned |
| :-- | :-: | --: |
| Left | Center | Right |
| Text | Text | Text |

```mdx
| Left aligned | Center aligned | Right aligned |
| :----------- | :------------: | ------------: |
| Left         | Center         | Right         |
| Text         | Text           | Text          |
```