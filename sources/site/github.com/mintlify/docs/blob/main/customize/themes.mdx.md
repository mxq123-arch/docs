# Source: https://github.com/mintlify/docs/blob/main/customize/themes.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# themes.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/customize/themes.mdx)

History

63 lines (48 loc) · 3.72 KB

 main

/

# themes.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

63 lines (48 loc) · 3.72 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/customize/themes.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Themes</td></tr><tr><th>description</th><td>Choose and configure a theme to customize your documentation site's colors, dark mode behavior, layout style, and overall visual appearance.</td></tr><tr><th>mode</th><td>frame</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">theme selection</div></th><th><div dir="auto">Mint</div></th><th><div dir="auto">Maple</div></th><th><div dir="auto">Palm</div></th><th><div dir="auto">Willow</div></th><th><div dir="auto">Linden</div></th><th><div dir="auto">Almond</div></th><th><div dir="auto">Aspen</div></th><th><div dir="auto">Sequoia</div></th><th><div dir="auto">customize appearance</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

export const ThemeCard = ({ title, value, description, href }) => { return (

<img className="mt-0 rounded-2xl group-hover:scale-105 transition-all block" src={`https://raw.githubusercontent.com/mintlify/docs/refs/heads/main/images/themes/${value}.png`} alt={title} noZoom />

#### {title}

"{value}"

{description}

See preview

); };

Core Concepts

# Themes

Customize the appearance of your documentation 
 
Configure \[theme\](/organize/settings-appearance#theme) in docs.json using one of the following themes.